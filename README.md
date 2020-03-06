# django_harry2
## create app
> app = plugable web application
>> python manage.py startapp app_name
* create two app
  1. python manage.py startapp shop
  2. python manage.py startapp blog

### create urls.py file in shop & blog folder
> add views in views.py file

### create templates/blog(or shop)  dir in blog and shop folder 
> blog->templates->blog

>shop->templates->shop

### add blog and shop in list (INSTALLED_APPS=[])
> In setting this list present 

### add html file in template/blog(or shop) folder

## Add static folder 
> create static/blog(or shop) dir in blog/shop folder
>> ex. blog/static/blog 

> add static file in that folder
> ex. mystatic.txt
>>when access static file then add these lines

>>     {% load static %}  
>>     {%static add_link_at_here %}

### ex.                                     

     <a href="{%static 'blog/mystatic.txt' %}">click me</a>

> Then Restart the server 

## create model 
> In app folder(blog,shop) there is migrations folder created and models.py file also created automatics when you create App
>>  python manage.py migrate

### migrations
    change in model are occured that store in the migration .
    (jo change model m kiya h like. table ka nam change kr liya so this change only store in migration but not store in the database 'but when you apply migration that time that changes in databases applyed .(jab tk apply nhi kronge migration ko tb tk koi databases m change nhi hoga, only migration m store ho jayega wo changes.)
    
## update
> change in installed_app[] list(present in project1) 
  
    add this 'shop.apps.ShopConfig',
    and remove 'shop

## create model
 > create model with name 'Product'(class name)
 in shop/models.py file

## make migration 
     python manager.py makemigrations 
## apply migration 
      python manage.py migrate

## make super Admin
     python manage.py createsuperuser
> set user name ,pass,etc..

> goto 127.0.0.1:8000/admin
>> data is not showing because we can't register our model so first register our model

>go to shop/admin.py file
  >> add these lines

     from .models import model_name
     admin.site.register(model_name)
     ex.
     from .models import Product
     admin.site.register(Product)

> got to admin page(127.0.0.1:8000/admin)
>> now product(model) is showing

>restart server then add product if error occur 
      
      reason 1. not do migrate process
      reason 2. not restart the server

>> NOTE - if any change in model than definitlty you have to do 'migration '     
 
 
