![brand image](../img/gp-logo.png)
# Genius Plaza and the adventure of Python
## Table of Contents

1. [Introduction](#introduction)
2. [Working with Python](#python)
3. [Rendering templated using Python](#render)
4. [Inheriting parent templates](#inherit)
5. [spining up a python project](#startupPython)

<a name="introduction"></a>
## Introduction
Welcome to the Python version of this Portfolio piece. Python python python, I love python. Such a graceful language to learn. The thing about python is, if you dont write clean code, it wont work! Its that simple. I worked at this place called Genius Plaza, and there is where I learned most of Python (Django Framework) to be more precise, knowledge in the language. In this section I will be talking about my personal experience with working with the language and how I got a better understanding of the Framework.

<a name="python"></a>
## Working with Python 
When working with Python of the things that really stood out to me was the face on how the language wouldnt run correctly if it wasnt in order. Meaning, you can write chicken scratch code all you want in other languages BUT in Python, that doesn't fly. Things are a lot cleaner with this language than others which is one of the resons why I love it. This language is also relatable to other languages as well. This is a simple "Hello World" in Javascript 
```
Javascript

alert( 'Hello, world!' );
```
Heres the same "Hello World" in PHP
```
PHP

<?php echo '<p>Hello World!</p>'; ?> 
```
And here we have the same "Hello World" in Python
```
Python

print("Hello world!")
```

As you can see most languages can do most things, everyone of them are better suited for their specifics needs of course,  you can cut a chicken with a spoon but wouldnt a knife be better? same thing when it comes to different languages. Just to further my point here are "IF" Statements with time being the deciding factor written in all three languages.
```
Javascript

var time = new Date().getHours();
    var greeting;
    if (time < 20) {
        greeting = "Good day";
    } else {
        greeting = "Good evening";
    }
```
Now here is PHP
```
PHP

$time = time()
if ($time < 20) {
    echo "Good Day";
} elseif {
    echo "Good Evening";
}

```
And here we have it in Python
```
Python

import datetime
now = datetime.datetime.now()

if now.hour == 17:
    print ("Good Day")
else :
    print ("Good Evening")
```
See how in Python I had to import a module but in the other ones i didn't. Every language works differently but at the same time they all are relatable to eachother.

<a name="render"></a>
## Rendering templated using Python(Django)
So, lets say you wanted to render a template using the Django framework. Well this is going to take some time to set up but lets say your set up and ready to go. *Step 1* You would go to your urls.py file and put in 
```
Python

url(r^aboutpage, views.aboutPage, name='about_page')
```
the r^aboutpage is what your going to call the route when it displays on the URL
the views.aboutPage is the controller it is calling to render your template
and the name='about_page' is just how to reference this.
*Step 2*
In the views.py file your going to want to make a new controller like so
```
Python

#Name of the controller your calling 
def aboutPage(request):
    
    #Setting the title of the page
    data = {'Title' : 'About Page'}
    
    #letting the template know that you are expecting to recieve these two arguments
    addGlobalData(request,data)
    
    #returning the template with the right information
    return render(request, 'about.html' data)
```
And thats it, just like that you have your templates up and rendering on your page as long as you go that route it should be up. Hope this helps!

<a name="inherit"></a>
## Inheriting parent templates
Lets say you made a Template already that has most of your styling in there. You wouldnt want to re create that again just for a new template so what do we do? we inherit from the parent template.
```
Python
#on top of your template all you will need to do is load in the parent template

{% load parentTemplate %} #Honestly you can call this what you would like in the parent element
#from here you can add your code of what you want and anything from the parent element that you just loaded in will also take place in this template
```
Just like that you can have the parent template included into your template. Kind of how the includes work for PHP.

<a name="startupPython"></a>
## Spining up a python project
So, you want to start up a Python project. Lets be clear, Python is used more many things but if you would like to use it for making website you will need to use a framework that supports that. [Django](https://realpython.com/learn/start-django/) is one of those Frameworks. 
I will do a quick run through on how to spin up a project but i strongly recommend seeing more of the details on [realpython.com](https://realpython.com/learn/start-django/) to see everything and anything you need.
First things first you will need to run a few scripts in order to get your project in place. Go to the links i provided above and it will show what scripts to run. 
Second thing you would want to do is make sure your file structure looks similar to this:
```
File Structure

djangoProjectName
    manage.py
    siteName
        settings.py
        urls.py
        wsgi.py
        __init__.py
```

Manage.py is the file that will help you run and manage your project. ```settings.py``` contains the configuration of your site, all the things you want installed and basic settings.
Next you will want to set up a database for the project, If you ran the scripts then this will already be inside your ```settings.py``` file. Just make sure you put in the right information so it properly configures to your database. Now its time to Make Migrations. In your ```manage.py``` file your going to run a command called "makemigrations", soon after thats done your going to run another one called "migrate" what this does is it configures your project depending on your ```settings.py``` file and other things as well. After that you will run "runserver" on your command line and WALA! Django should be up and running and you can start creating the things you need. Have fun! If you want to learn how to spin up a Django project in more detail check out [realpython.com](https://realpython.com/learn/start-django/) they have a great resource on how to get up and running on with Django. Hope this helps!
