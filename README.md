callisto-sample-app
======

Welcome! This app is meant to be an accessible way to show how callisto-core can be incorporated into a bare-bones Django app, empowering others to explore new applications of callisto-core. It is built on callisto-core, [django-wizard-builder](https://github.com/SexualHealthInnovations/django-wizard-builder), and [Django admin sites](https://docs.djangoproject.com/en/1.10/ref/contrib/admin/). Read about the Callisto project [here](https://github.com/SexualHealthInnovations/callisto-core).

callisto-core supports Django 1.8 and Django 1.9, running on Python 3.3, 3.4, or 3.5. Python 2.7 is provisionally supported, pending further testing.

callisto-core is built on top of django-wizard-builder, another open source Django package maintained by Sexual Health Innovations. If you're interested in contributing to Callisto, please check out that repo as well.

## Mac OS Setup:
1. Fork and clone this repo.  

2. If needed, install pip. [Read more](https://pip.pypa.io/en/stable/installing/) about installation and use of this handy tool.  

3. **Virtualenv:** You'll need virtualenv to help with versioning and dependency management. Known working version: 15.0.3
 * Check Virtualenv version:  15.0.3
  ```$ virtualenv --version ```
 * If needed, use pip to get it:  
  ```$ pip install virtualenv ```
 * Once installed, create a new virtualenv:  
  ```$ mkvirtualenv --python=python3 callisto-sample-app ```  

4. In .bash_profile, add:  
 ```python 
 # Setting PATH for Python 3.5
 # The original version is saved in .bash_profile.pysave
 PATH="/usr/local/bin:${PATH}"
 export PATH

 export WORKON_HOME=$HOME/.virtualenvs
 source /usr/local/bin/virtualenvwrapper.sh
 alias python=python3
 ```
 
5. **Python:** callisto-core supports Python 3.3, 3.4, or 3.5. This app is built on 3.5.2.
 * Check your Python version:  
  ```$ python -V ```
 * If you don't have Python or have an old version, [download/install/update](https://www.python.org/downloads/).  

6. **Django:** callisto-core supports Django 1.8 and Django 1.9. This app is built on 1.9.
 * Check Django version:   
  ```$ django-admin --version ```
 * If you don't have Django or have an old version, use pip to get 1.9:  
  ```$ pip install django==1.9```  

7. **PostgreSQL:** follow [this guide](https://gist.github.com/panuta/1852087#install-postgresql) to install Postgresql and Psycopg.

8. Install the other dependencies:  
  ```$ pip install requirements/base.txt ```
  * If you like, you can view the current installed dependencies with the command ```$ pip freeze```

9. Make the initial migration:  
  ```$ python manage.py migrate ```  

10. Django-wizard-builder requires instances of two models before an admin can use the UI to create and edit form pages and questions. 
  * Open the python shell:  
    ```$ python manage.py shell ```
  * Run the following commands:  
    ```$ from wizard_builder.models import * ```
    ```$ QuestionPage.objects.create() ```
    ```$ FormQuestion.objects.create(page = QuestionPage.objects.first()) ```

11. Make a superuser to be able to use Django admin:  
  ```$ python manage.py createsuperuser ```

12. Run the server:  
  ```$ python manage.py runserver ```

13. Load the site at the port specified in your terminal, with the extension '/admin'. Django loads its admin dashboard from the models we provide it, so you should see something similar to this Admin dashboard screenshot.

![Image of Django admin screenshot](Admin dashboard.png?raw=true "Admin dashboard")




