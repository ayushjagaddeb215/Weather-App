# Weather-App
Simple Django weather app that shows current conditions and forecast by city name. Features geolocation fallback, error handling, and responsive UI. Built with Django and a weather API (OpenWeatherMap). Includes environment-based config, caching, and tests.

Django Weather App
A simple, responsive weather web app built with Django. Enter a city name to see current conditions and a short forecast. Designed for clarity, reliability, and easy deployment.

Features
City-based search with friendly validation and error messages

Current weather: temperature, feels-like, condition, humidity, wind

Forecast preview (configurable: hourly or 5–7 day)

Optional geolocation (“Use my location”) with graceful fallback

Caching of the last successful result for quick reloads

Mobile-first, accessible UI with loading and error states

Tech Stack
Django (views, templates, static files)

Requests/HTTPX for API calls (server-side)

Vanilla JS for interactivity (geolocation, unit toggle)

Weather API provider (e.g., OpenWeatherMap or WeatherAPI)

Optional: Redis/locmem cache for API response caching

Getting Started

Prerequisites

Python 3.10+

pip or pipx
