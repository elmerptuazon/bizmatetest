## Tools
- php 8.1
- node 22.3.0
- npm 10.8.1
- composer 2.7.2
- laravel 9x

## Setup
- Clone your project
- Go to the folder application using cd command on your cmd or terminal
- Run composer install on your cmd or terminal
- Copy .env.example file to .env on the root folder. You can type copy .env.example .env if using command prompt Windows or cp .env.example .env if using terminal, Ubuntu
- Add your own GEOAPIFY_API_KEY and OPEN_WEATHER_API_KEY in the .env
- Open your .env file and change the database name (DB_DATABASE) to whatever you have, username (DB_USERNAME) and password (DB_PASSWORD) field correspond to your configuration.
- Run php artisan key:generate
- Run php artisan migrate
- npm install
- npm run build
- Run php artisan serve
- Go to http://localhost:8000/

## Usage

| Web | API |
| ------ | ------ |
| http://127.0.0.1:8000/?location={city} | http://127.0.0.1:8000/api/weather-update with body json {"location": "city"} |


## UI Explanantion
- Used simple bootstrap card template design
- Used vite for builtin laravel bundles frontend including blade

## Code Implementation
- Using custom service container WeatherAppServiceProvider binding interface and class to implement abstraction. So that in /Services directory you can see interface and service class being used then called in controller.
- In custom service provider using single instance of OpenWeatherApiServiceFactoryInterface and OpenWeatherApiServiceFactory to inherit WeatherUpdateService and WeatherForecastService
- Use single controller invocation for WeatherUpdateApiController
- Using API resource for in the event of needing to transform a data before sent back to user as response;
- By using config like geoapify in services.api. Create a mapping in order to generate query parameter for geocode/search for geoapify