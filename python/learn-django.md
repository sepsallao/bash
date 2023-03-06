# Django

## Start a project
`$ django-admin startproject hardin_ni_dionisio`

##

## Start an app

##


## Migrate
###### When Does migrations is needaed
1. Adding a Model
2. Adding a Field
3. Removing a Field
4. Changing a Field

###### Make Migrations
- Generates migration files for later use
- Uses current model fields and current databases tables
- Creates numbered files in <appname>/migrations/

`$ python3 manage.py makemigrations`

###### Show Migrations
`$ python3 manage.py showmigrations`

###### Migrate
- Runs all migrations in the project to the current state (To update the state)
- Can also run only migrations in a specific app to a specific number using:
`$ python3 manage.py migrate <appname> <number>`
e.g.
`$ python3 manage.py migrate adoptions 1`

- To migrate all
`$ manage.py migrate`

##

## From Linked In Learning: Learning Django Adoption Web App

###### To run the import CSV
This is came from my_site/main/management/commands/load_pet_data.py
`$ python3 manage.py load_pet_data`

###### To Create a Admin Super User:
`$  python3 manage.py createsupersuser`
You can skip the email portion

###### To test the query using django orm
`$ python3 manage.py shell`
```
>>> from main.models import Pet
* To query all:
>>> Pet.object.all() 
>>> pets = Pet.object.all()
>>> pet = pets[0]
>>> pet.name
'Pepe'
>>> pet.age
0
>>> pet.description
'<description something>'
>>> pet.sex
'M'
>>> pet.id
1
```
To clear the python shell:
Ctrl + l

###### for the vaccination part
```
>>> pet.vaccination.all()
<QuerySet []> 
* You won't get anything here, so:

>>> pet = Pet.objects.get(id=7)
>>> pet.vaccinations.all()
* Then you will get all the vaccination that the pet has
```

##


## Some some

`$ python3 -m venv server/env/`
`$ source server/env/bin/activate`
`$ which python3`
`$ python -V`
`$ which pip3`
`$ pip3 -V`
`$ pip3`
`$ pip3 install -U pip`
`$ pip3 install django`
`$ cd server/`
`$ django-admin startproject app .`

while in server directory you can now runserver command
`$ python3 manage.py runserver`

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.

Then there's a startapp command to start an app, gotte need to get deep my men

`$ python3 manage.py startapp the_garden` or `app`

I name our app into "the_garden", because it will provide all the data inside the inventory.

add the name of the app to the first settings.py from the one you use runserver

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    '<name of the app>'  # "the_garden?"
]
```









