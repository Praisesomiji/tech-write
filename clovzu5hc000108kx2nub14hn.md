---
title: "How to Set Up a Django Development Environment"
seoTitle: "Step-by-Step Guide to Setting Up a Django Development Environment"
seoDescription: "Learn how to install Python, set up a virtual environment, install Django, and run the development server. Start building your next Django project!"
datePublished: Sun Nov 12 2023 21:34:26 GMT+0000 (Coordinated Universal Time)
cuid: clovzu5hc000108kx2nub14hn
slug: how-to-set-up-a-django-development-environment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699819193476/3b31405a-ae06-4b70-b95f-f5ce5e40aaea.png
tags: python, django, python3, development-environments

---

### Introduction

Django is a popular web framework written in Python. It enables the rapid development of secure and scalable websites. The first step to working with Django is setting up a Django development environment. This involves downloading and configuring the software and tools needed to create and test Django projects.

### Prerequisite

* Basic understanding of Python or Any Programming Language
    
* Understanding of How Websites Work
    

### Install Python

Django is a Python-based framework. Therefore, to use Django, you need to have Python installed on your computer. To install Python:

![Python logo](https://lh7-us.googleusercontent.com/XCrLredztU_yn5x_Z3TalG3NAcFitCWCcAWnAgvrBbAq_ZNwzlMGA3V3gRm4T7GwIRMubNXxQC9sa8HDPemm69_86-IHcXUq3FbIgTcvPEEpCEUVdhk4Vc-bQ6yagsSvR8K7Hh_V8qzIPrtymIeBU9g align="left")

* Go to: [https://www.python.org](https://www.python.org)
    
* Hover over ‘Downloads’ on the navigation bar 
    

![Python Official Website: Focused on Download dropdown](https://lh7-us.googleusercontent.com/CUq_sQ6KYjz48WAtkk1kVYzlK1BKlkJqAETYROJ2ommeebVC9yNR9cXQdVpkxn3O6k_pgrWiFMhta6j5qSfbpxp_skgCw-Izieeix1TzABzSRRXd-thu4YWKttHMCgWYQ9K3wxEvIO5XVuvYfYxAEeQ align="left")

* Select the right OS - for Linux/Unix OS, select ‘source code’
    
* Download the latest stable release
    

![Python Release Page for macOS: Focused on Latest Stable Release](https://lh7-us.googleusercontent.com/4n0KEBejgcJC_3jbFEFgqRljKim306RIc-d8JHTR8BR_7oZoCZ_ejaPTammY0yOCHGIy7PTQhGzo8ZK-ED3D-jx__6rhsTpRPkQ3iXcBSWGp7a4udKWuiXgN2HJ3yeuR5oscHWD26Bo0ouYP3dVKMrk align="left")

* Open the downloaded package
    
* Follow installation instructions
    

![Python Installation Start Page](https://lh7-us.googleusercontent.com/j7GZbxjD4ZUUNNkoAuuNSxB-BjoIw8cYbN6mCy0oWVGAWwgWX_yCDIq4BDKvUIn23MT19Q93Ob0k7qMOO8lnf1_nBdF43We6EUoqhFUEmTmxf8YAgW2cYUMDJHmEUMKxUtY4B6IbNPWb86Sy7XVuskc align="left")

![Setup Success Page](https://cdn.hashnode.com/res/hashnode/image/upload/v1699819687454/4c63d8dc-78e0-420e-84a0-bf5c894cf0da.jpeg align="left")

* Close setup window.
    

### Create a Virtual Environment

Isolating a project’s environment is good practice. 

For instance, imagine having to work on 2 projects that require different versions of Django and other dependencies. Installing every required package globally on your computer would be a bad idea because, then, you would have to deal with the conflicts. Instead, you should isolate each project in a virtual environment, and download their dependencies in their respective environments. 

So to create a virtual environment for this project, go to your command line and do the following:

* Create a directory for this project *(call it* `my_python_project` *or anything you like)*.
    
    ```bash
    mkdir my_python_project
    ```
    
* Change your current directory to the project you just created.
    
    ```bash
    cd my_python_project
    ```
    
* Create a virtual environment named `env` in the current directory.
    
    ```bash
    # macOS / Linux
    python3 -m venv env
    ```
    
    ```powershell
    # Windows
    python -m venv env
    ```
    
* Activate the virtual environment.
    
    ```bash
    # macOS / Linux
    source env/bin/activate
    ```
    
    ```powershell
    # Windows
    env\Scripts\activate
    ```
    

### Install Django

Having created and activated a virtual environment, the next step is to install Django right there in your project folder (which is now an active virtual environment). To install Django, you will need `pip` — *a tool for managing and installing Python packages*. Don’t worry, `pip` is automatically installed in Python virtual environments. 

![](https://lh7-us.googleusercontent.com/lgXDInt5XW8y4I13HoffDqLPbxuJKcCD18NpyW-O24l0TgmONz-_BPGASHRuzoWVhW80HvY7InDTCuzfkzQyts1ikIUVAg8kWLwN96vUfmm8f0KhUtZFTKHvQXgDzFBaCvJrfrfRX82XTViTDQbqesY align="left")

* Install the latest version of Django
    
    ```bash
    pip  install django
    ```
    

### Start a Django Project

The next step is to begin a Django project. This is a folder that houses all applications and configurations that make a Django website. Simply put, it is your Django development environment.

* Start a Django Project (*call it* `my_project` *or anything you like*).
    
    ```bash
    django-admin startproject my_project
    ```
    

* Change your current directory to your new Django project.
    
    ```bash
    cd my_project
    ```
    

### Run the Development Server

Django comes with a lightweight web server that allows you to simulate serving your project and applications. This works with a file named `manage.py`. You should find it in your current directory.

* Optional: Check for a `manage.py` file  in your django project folder.
    
    ```bash
    # macOS / Linux
    ls | grep manage.py
    ```
    
    ```powershell
    # Windows
    dir | Search-String manage.py
    ```
    

* Run the development server
    
    ```bash
    python manage.py runserver
    ```
    

In your browser, go to: [http://127.0.0.1:8000/](http://127.0.0.1:8000/). You should see something like this:

![Django Development Server: On Initial Launch](https://lh7-us.googleusercontent.com/JJrWC6R9y4PD5reymrUwGEVkrTiDFYnoYrnu3DRejRdFG06UgJhHRIpMj-eWWZbfcviqohmiwCa_9vX_tdWMqngB22E-r6dQIcDRaUn6fx3olGR3h2kNXX6yiZKXQzTiyjfrDkeMEFOqO9-8jgzTX_M align="left")

Voila! Your Django development server is now primed and ready to soar to new heights.  

### Conclusion

Setting up a Django development environment is where every Django project begins. First, you have to ensure that Python is installed on your computer. Then, you want to create a virtual environment to enjoy the benefits of isolated development. In that environment, you create a Django project which is where you’ve got everything you need to start building your next (or first) website with Django. 

You could create applications, make configurations, and serve your project with the Django development server. Best of code luck🧩!  

### References

1. [Python.org](http://Python.org). (2023). Download Python | [Python.org](http://Python.org). Python Software Foundation. Retrieved from [](https://www.python.org/downloads/)[Python.org](http://Python.org).
    
2. [Python.org](http://Python.org). (2023). PEP 405 – Python Virtual Environments. Python Software Foundation. Retrieved from [PEP 405](https://peps.python.org/pep-0405/).
    
3. Dataquest. (2023). A Complete Guide to Python Virtual Environments. Dataquest Labs, Inc. Retrieved from [Dataquest Blog](https://www.dataquest.io/blog/a-complete-guide-to-python-virtual-environments/#why-are-python-environments-important).
    
4. Django. (2023). The web framework for perfectionists with deadlines. Django Software Foundation. Retrieved from [Django](https://www.djangoproject.com/).
    

1. Mozilla Developer Network. (2023). Django Web Framework (Python). Mozilla. Retrieved from [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction).