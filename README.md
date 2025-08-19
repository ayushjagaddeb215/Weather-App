Django Weather Forecasting App
A simple Django web app that displays weather information for a given city. Uses a clean Django structure with app-level templates and separate project/app URL routing.

Features
City-name input to fetch and display weather details

Minimal, beginner-friendly Django setup

Separate app and project URL routing

Ready to integrate any weather API provider

Directory Structure
This layout follows your steps: a project folder, a Django project called weatherproject, an app called weatherapp, and an index.html template inside the app.

weather-forecasting-app/                 # Your top-level project folder (name as desired)
├─ venv/                                  # Python virtual environment (created locally)
├─ manage.py
├─ weatherproject/                        # Django project (global settings and URLs)
│  ├─ __init__.py
│  ├─ settings.py
│  ├─ urls.py                             # Project-level routing: includes weatherapp URLs
│  ├─ asgi.py
│  └─ wsgi.py
└─ weatherapp/                            # Django app
   ├─ __init__.py
   ├─ admin.py
   ├─ apps.py
   ├─ migrations/
   │  └─ __init__.py
   ├─ models.py
   ├─ tests.py
   ├─ urls.py                             # App-level routing: routes like "/", "/about/"
   ├─ views.py                            # Renders templates (e.g., index.html)
   └─ templates/
      └─ weatherapp/
         └─ index.html                    # Main page with city input

Installation
Follow these steps exactly as outlined by your setup approach.

Create a project folder

Create a folder on your system, e.g., weather-forecasting-app

Create a virtual environment

Using built-in venv:

python -m venv venv

Or using virtualenv (if installed):

virtualenv venv

Activate the virtual environment

macOS/Linux:

source venv/bin/activate

Windows (PowerShell):

.\venv\Scripts\Activate.ps1

Install Django (and other dependencies if you have a requirements.txt)

If starting fresh:

pip install Django

If you already have a requirements.txt:

pip install -r requirements.txt

Create the Django project and app (if not already present)

Create the project in the current folder:

django-admin startproject weatherproject .

Create the app:

python manage.py startapp weatherapp

Register the app in settings

Open weatherproject/settings.py and add "weatherapp" to INSTALLED_APPS.

Ensure the TEMPLATES setting has APP_DIRS=True (default) so app templates are discovered.

Create URL routing files

Project-level: weatherproject/urls.py should include the app’s URLconf:

from django.contrib import admin

from django.urls import path, include

urlpatterns = [
path('admin/', admin.site.urls),
path('', include('weatherapp.urls')),
]

App-level: create weatherapp/urls.py with your routes, e.g.:

from django.urls import path

from . import views

urlpatterns = [
path('', views.index, name='home'),

path('about/', views.about, name='about'),
]

Create views

In weatherapp/views.py:

from django.shortcuts import render

def index(request):
return render(request, 'weatherapp/index.html')

Create templates

Inside weatherapp, create:

templates/weatherapp/index.html

Add a basic form for city input; later, wire it to your weather-fetching logic.

Apply database migrations

python manage.py migrate

Run the development server

python manage.py runserver

Open http://127.0.0.1:8000/ to access the app

Usage
Open the home page, enter a city name, and submit to view weather info.

Extend the view to call your chosen weather API and render results in index.html.
