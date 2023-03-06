# DJANGO MOTHERFUCKER in simplier way

## Create Virtual Environment
`$ python3 -m venv path/to/new/directory`

##

## Start using the environment
`$ source path/to/the/venv/dir/bin/activate`

##

## Create Django app
###### Creating the project directory
`$ django-admin startproject <name_of_the_project>`

###### Creating an app inside the project
`$ cd path/to/project/dir/`

```
$ python3 manage.py startapp <name_of_the_app>

example:

$ python3 manage.py startapp main
```

##

## To run a server
```
$ cd path/to/project/dir/
$ python3 manage.py runserver

or you can indicate a port:
$ python3 manage.py runserver 5000

```

##