# Lab26_CarsStorApi

##  How to use the APP

- run the server `python3 manage.py runserver`


## How to deploy our Django app using Render?
- install `dj-database-url` library.
- install `dj-database-url` library.
- install `psycopg2-binary` library.
- install `gunicorn` library.

- go to the settings.py and overwrite the defalut database with the follwoing: 

`DATABASES['default'] = dj_database_url.parse(database_url)`

- `database_url` is the **External Database URL** that you get when you create your database on render, using **External Database URL** is to connect our database to the Django App as a first step, next we will use the **Internal Database URL** when deploy our Django App.

## Environment Variables 

Environment variables are used to manage and configure application settings that can change based on the environment in which the application is running (e.g., development, testing, production). they provide :
- **Separation of Configuration from Code** 
- **Security** : ensitive information like API keys, database credentials, and other secrets can be stored in environment variables rather than hard-coding them in the source code. This reduces the risk of exposing sensitive information, especially when sharing or versioning your code.
- **Flexibility** : You can easily change the behavior of your application by adjusting the environment variables without needing to modify the code. For example, you might switch between development and production databases or enable/disable debugging.

## Django App Environment Variables

- `SECRET_KEY = os.environ.get("SECRET_KEY")`

- `DEBUG = os.environ.get('DEBUG','False').lower() == 'true'`

- `ALLOWED_HOSTS = os.environ.get('ALLOWED_HOSTS').split(" ")`


SECRET_KEY, DEBUG, ALLOWED_HOSTS all of them can be setted in the Render platfrom during deployment