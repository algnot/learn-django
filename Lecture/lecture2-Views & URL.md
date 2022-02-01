# LECTURE 2 - Views & URL

## Step to create Model View Template (MVT)

### Create View
* Create **viwe.py** at **/try_django**
``` python
from django.http import HttpResponse

def home_page(request):
    return HttpResponse("<h1>Hello world</h1>")
``` 

### Create URLs
* In **urls.py** file you will see 
``` python
from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('admin/', admin.site.urls),
]
```
* you can change path by change path in urlpatterns value 
* you can import view using
``` python
#   from <file_name> import <function_name>
    from .views import home_page
```
* now you can add path using
``` python
    from django.contrib import admin
    from django.urls import path
    #add it
    from .view import home_page

    urlpatterns = [
        #add it
        path('', home_page),
        path('admin/', admin.site.urls),
    ]
```
* you can see Hello world at /
* you can import multiple page using
``` python
#   from <file_name> import <function_name>
    from .views import (
        home_page,
        about_page
    )
```

## path vs re_path
* We will use **path** if url is static like **path('home',home_page)** it mean only **/home**
* But you can use re_path for regular expression path
* First we will import re_part from django.urls 
``` python
    from django.urls import path , re_path
```
* now change **path('', home_page)** to **re_path(r'^home/$', home_page)**
```python
    re_path(r'^home?/$', home_page)
```
* it mean **/home** or **/hom**
