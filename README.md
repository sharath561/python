
Install Django: First, you need to install Django. You can do this by running the command pip install 
django in your terminal.
pip install django
Create a new Django project: Next, create a new Django project by running the command django-admin 
startproject HelloWorldProject.
django-admin startproject HelloWorldProject
Create a new Django app: Inside your Django project, create a new Django app by running the command 
python manage.py startapp HelloWorldApp.
cd HelloWorldProject
python manage.py startapp HelloWorldApp
Create a view: In your app directory, open the views.py file and create a view that returns a JSON 
response with the message 'Hello World'. The code should look like this: 
from django.http import JsonResponse
def hello_world(request):
 
return JsonResponse({'Message': 'Hello World!'})
Define URL Route: In HelloWorldApp/urls.py, map the URL to the function you just created:
from django.urls import path
from . import views
urlpatterns = [
 path('hello/', views.hello_world, name='hello_world'),
]
Update Project URLs: Include the app's URLs in the project's urls.py:
from django.contrib import admin
from django.urls import include, path
urlpatterns = [
 path('admin/', admin.site.urls),
 path('', include('HelloWorldApp.urls')),
]
Run the Server: Start the development server:
python manage.py runserver
Access Hello World JSON Response:
In a browser, navigate to http://127.0.0.1:8000/hello/ to see the JSON response: {"Message": "Hello 
World!"}

https://github.com/sharath561/python

Git Setup and Push to GitHub:
1. Initialize a Git repository:
$git init
2. Add your files:
$git add .
3. Commit the changes:
$git commit -m "Initial commit: Added Django Hello World app"
4.Create a repository on GitHub.
5.Link your local repository to the GitHub repository:
$git remote add origin <your-github-repo-url>
6.Push your code to GitHub:
$git push -u origin master
Push to GitHub:Finally, create a new GitHub repository and push your Django project to it. Don't forget 
to include a README file with instructions on how to run your app and access the 'Hello World' JSON 
response
