# Final-Venenoisom
Analyze the possible threat of Poisonous animals or plants and find out about  treatment
flaskSaas
License
Original project https://github.com/CivitasMax/MachineLearning/tree/master/Week5/flaskSaaS-master
A fork of Max Halford's flask-boilerplate. I've noticed SaaS bootstraps/boilerplates being sold upwards of $1,000 per year and I think that's fucking ridiculous. This project will be my attempt to make a great starting point for your next big business as easy and efficent as possible.

Features
 User account sign up, sign in, password reset, all through asynchronous email confirmation.
 Form generation.
 Error handling.
 HTML macros and layout file.
 "Functional" file structure.
 Python 3.x compliant.
 Asynchronous AJAX calls.
 Administration panel.
 Logging.
 Stripe subscriptions. (WIP)
 RESTful API for payments.
 Simple RESTful API to communicate with your app.
Libraries
Backend
Flask, obviously.
Flask-Login for the user accounts.
Flask-SQLAlchemy interacting with the database.
Flask-WTF and WTForms for the form handling.
Flask-Mail for sending mails.
itsdangerous for generating random tokens for the confirmation emails.
Flask-Bcrypt for generating secret user passwords.
Flask-Admin for building an administration interface.
Flask-Script for managing the app.
structlog for logging.
Flask-DebugToolBar for adding a performance toolbar in development.
gunicorn for acting as a reverse-proxy for Nginx.
Flask-Stripe for subscription billing.
Frontend
Semantic UI for the global style. Very similar to Bootstrap.
Leaflet JS for the map. I only added it for the sake of the example.
Structure
I did what most people recommend for the application's structure. Basically, everything is contained in the app/ folder.

There you have the classic static/ and templates/ folders. The templates/ folder contains macros, error views and a common layout.
I added a views/ folder to separate the user and the website logic, which could be extended to the the admin views.
The same goes for the forms/ folder, as the project grows it will be useful to split the WTForms code into separate files.
The models.py script contains the SQLAlchemy code, for the while it only contains the logic for a users table.
The toolbox/ folder is a personal choice, in it I keep all the other code the application will need.
Management commands should be included in manage.py. Enter python manage.py -? to get a list of existing commands.
I added a Makefile for setup tasks, it can be quite useful once a project grows.
Setup
Vanilla
Install the requirements and setup the development environment.

make install && make dev

Create the database.

python manage.py initdb

Run the application.

python manage.py runserver

Navigate to localhost:5000.

Configuration
The goal is to keep most of the application's configuration in a single file called config.py. I added a config_dev.py and a config_prod.py who inherit from config_common.py. The trick is to symlink either of these to config.py. This is done in by running make dev or make prod.

I have included a working Gmail account to confirm user email addresses and reset user passwords, although in production you should't include the file if you push to GitHub because people can see it. The same goes for API keys, you should keep them secret. You can read more about secret configuration files here.

Read this for information on the possible configuration options.

License
The MIT License (MIT). Please see the license file for more information.
