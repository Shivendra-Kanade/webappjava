# Weather Forecast (Plain Colors)

A simple Java Spring Boot web app that shows a 5‑day forecast using plain colors (no background images).

## Features
- Search by city (optional country code).
- Metric (°C) or Imperial (°F) units.
- Minimal UI with plain colors.
- Falls back to demo forecast if no API key is configured.

## Prerequisites
- Java 17+
- Maven 3.8+
- (Optional) An OpenWeather API key: https://openweathermap.org/api

## Run locally
```bash
# clone/download this folder
mvn spring-boot:run
# or build a jar
mvn -q -DskipTests package
java -jar target/weather-plain-1.0.0.jar
```

By default it runs on http://localhost:8080

## Configure API key
Set your key as an env var or in `src/main/resources/application.properties`:

```bash
export OPENWEATHER_API_KEY=YOUR_KEY
# Windows (PowerShell):
# $env:OPENWEATHER_API_KEY="YOUR_KEY"
```

If no key is provided, the app displays demo data so you can still see the UI.

## Project layout
```
.
├── pom.xml
├── src
│   ├── main
│   │   ├── java/com/example/weather
│   │   │   ├── WeatherPlainApplication.java
│   │   │   ├── controller/WeatherController.java
│   │   │   ├── model/{Forecast,Location}.java
│   │   │   └── service/WeatherService.java
│   │   └── resources
│   │       ├── application.properties
│   │       ├── static/css/styles.css
│   │       └── templates/{index,forecast}.html
│   └── test
│       └── java/com/example/weather/WeatherServiceTest.java
```

## Notes
- No images are used anywhere. The UI sticks to solid colors.
- Replace OpenWeather with any provider you prefer by editing `WeatherService`.
