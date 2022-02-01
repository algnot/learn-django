# LECTURE 1 - INTRODUCTION

## Start djanjo

``` cmd
    pipenv install django
    pipenv shell
    mkdir src
    cd src 
    django-admin startproject try_django .
    python manage.py runserver
    **or you can use python manage.py runserver <port>**
```
the server will run at http://127.0.0.1:8000/

### Note
* if do not have **pipenv** you can install use **pip --user pipenv** or **brew install pipenv**
* when use command **pipenv install django** 
pip will create **Pipfile** like package.json in node
* **pipenv shell** will activate your ptoject

## Setup Admin
``` cmd
    python manage.py migrate
    python manage.py createsuperuser 
```
python will ask you for setting password of admin 
you can look admin page at http://127.0.0.1:8000/admin/
