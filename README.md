# django-tutorial
This repository helps me to practice with creating a Django project.

Based on the official django [documentation](https://docs.djangoproject.com/en/3.1/intro/).

# How to get this django project up and running

Follow these steps to run this django project.

**IMPORTANT!** this assumes that you have Python (>= 2.7.9 or >= 3.4) installed from [python.org](https://www.python.org/).

## Check that system is set up correctly

We recommend using a virtual environment.
This is the place where your django app lives and will make sure that dependencies are satisfied.

Make sure pip is installed: `python -m pip --version`

The output should look something like this:

`pip 20.1.1 from /home/janclod/anaconda3/lib/python3.8/site-packages/pip (python 3.8)`

If pip is not installed, you will get a message saying something like this: `No module named pip`

**NOTE**: make sure you are running Python >= 2.7.9 or >= 3.4 (run `python -v` to get the Python version).

## Clone Github repository

### Option 1
Download the .zip file of this repository [here](https://github.com/janclod/django-tutorial/archive/master.zip) and unzip.

### Option 2
Run: `git clone https://github.com/janclod/django-tutorial.git`

## Set up virtual Python environment

Move into the project folder:

On Linux: `cd ./django-tutorial`

Create a virtual environment in the project folder (i.e., ./django-tutorial)

`python -m venv ./venv`

Don't forget to activate the virtual env:

On Linux:

`source ./venv/bin/activate`

## Install requirements and local environment

### Requirements

Install project requirements: `python -m pip install -r requirements.txt`

This should end up with a success message, looking somethgin like this:

`Successfully installed asgiref-3.3.1 django-3.1.5 django-environ-0.4.5 pytz-2020.5 sqlparse-0.4.1`

### Environment variables

Rename the `./.env.example` file to `./.env`.

On Linux: `mv .env.example .env`

Add here your secret key and the debug mode.

#### Secret key

You can generate your secret key following these simple steps.

1. Launch python: `python`

2.  Run the following code:
    ```
    from django.core.management import utils
    utils.get_random_secret_key()
    ```
    You will get something like this as output:
    `g4u2i$ftp27%p)%^c&j$0vwcc0o+jfx_ii_)*sn(na($(m71#s`
3. Paste the random key into the `.env` file

#### Debug mode

Set this to `on`, when working in developing mode.

Make sure you change the debug mode to `off`, when in production.

## Set up database

The easiest choice is SQLite.
SQLite is included in Python,
so you won’t need to install anything else to support your database. 

Run: `python manage.py migrate`

## Launch django app

Finally, you can launch your django app: `python ./manage.py runserver`

Go to your browser:
* http://127.0.0.1:8000/polls/

There you go, this is your app running!

Take a moment to celebrate!
