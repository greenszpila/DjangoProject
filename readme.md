# **Django project**

### **Creating virtual env with pipenv**

* create Folder, cd to it,  
* pip3 install pipenv 
* pipenv shell - to activate it inside the Project folder
* exit or Ctrl D to deactivate

### **Installing Django**

* pipenv install django - make sure you are in the project folder
* django-admin startproject DjangoProject .
* ls to see if the django files have been created, go to: 127.0.0.1:8000  

### **Configuring Django** 

* python manage.py runserver - to start Django server
* control C to quit
* python manage.py startapp hello - start Django app within the project
* settings.py - add hello app to INSTALLED_APPS list
* view.py - create view for target URL - def view as a function 
* urls.py - add path to urlpaterns list

### **Create todo app with Django**

* python manage.py startapp todo 
* add app in the settings.py
* create a func in todo\views.py (import HttpResponse) 
* add path in urlpatters for the view 
* create templates folder and .html file in there
* add it to views
* add [os.path.join(BASE_DIR,'templates')], to TEMPLATES/DIRS in settings.py 
* create TodoItem class in models.py 
* migrate class to the database:
    * python manage.py makemigrations - creates migration file
    * python manage.py migrate - changing config of our db - adding todo model 
    * python manage.py shell - storing objects in the database: 
        from todo.models import TodoItem
        a = TodoItem(content='todo item AA')
        a.save()
        b = TodoItem(content='todo item B')
        c = TodoItem(content='todo item C')
        b.save()
        c.save()
        all_todo_items = TodoItem.objects.all()
        all_todo_items[1].content
    * edit views.py import TodoItem from .models , retriev all todo items from the db, add third argument to the render func - add all_todo_items to todo.html template - assign name all_items to it
    * edit todo.html add for loop to loop through all_items 
    * add input form to the todo.html 
    * create a new todo item in views.py 
    * add a path in the urls.py
    * Add delete button in the todo.html - inside the for loop (for each item)


