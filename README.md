# [Boilerplate Django Dashboard](https://appseed.us/boilerplate-code/django-dashboard/)

Reference codebase used by `AppSeed` in all Django [Dashboard](https://appseed.us/admin-dashboards/django/) starters - the product uses an amazing design crafted by `Creative-Tim`.

- 👉 [Boilerplate Django Dashboard](https://appseed.us/boilerplate-code/django-dashboard/) - `Product page`
- 👉 [Boilerplate Django Dashboard](https://django-soft-dash.onrender.com/) - `LIVE Demo`
- 👉 Free [Support](https://appseed.us/support/) via `Email` & `Discord`

<br />

> Features: 

- ✅ `Up-to-date Dependencies`
- ✅ Theme: [Django Admin Soft](https://github.com/app-generator/django-admin-soft-dashboard), designed by [Creative-Tim](https://www.creative-tim.com/product/soft-ui-dashboard?AFFILIATE=128200)
  - `can be used in any Django project` (new or legacy)
- ✅ **Authentication**: `Django.contrib.AUTH`, Registration
- 🚀 `Deployment` 
  - `CI/CD` flow via `Render`
  - [Django Soft - Go LIVE](https://www.youtube.com/watch?v=1QVdQVSkUCI) - `video presentation`

<br />

![Django Admin Soft - Template project for Django provided by AppSeed.](https://user-images.githubusercontent.com/51070104/215729207-5cce250e-54da-4712-89a9-c1fd6b0a149e.png)

<br />

## Start with `Docker`

> 👉 **Step 1** - Download the code from the GH repository (using `GIT`) 

```bash
$ git clone https://github.com/app-generator/boilerplate-code-django-dashboard.git
$ cd boilerplate-code-django-dashboard
```

<br />

> 👉 **Step 2** - Start the APP in `Docker`

```bash
$ docker-compose up --build 
```

Visit `http://localhost:5085` in your browser. The app should be up & running.

<br />

## Manual Build 

> 👉 Download the code  

```bash
$ git clone https://github.com/app-generator/boilerplate-code-django-dashboard.git
$ cd boilerplate-code-django-dashboard
```

<br />

> 👉 Install modules via `VENV`  

```bash
$ virtualenv env
$ source env/bin/activate
$ pip install -r requirements.txt
```

<br />

> 👉 Set Up Database

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

<br />

> 👉 Create the Superuser

```bash
$ python manage.py createsuperuser
```

<br />

> 👉 Start the app

```bash
$ python manage.py runserver
```

At this point, the app runs at `http://127.0.0.1:8000/`. 

<br />

## Codebase structure

The project is coded using a simple and intuitive structure presented below:

```bash
< PROJECT ROOT >
   |
   |-- core/                            
   |    |-- settings.py                  # Project Configuration  
   |    |-- urls.py                      # Project Routing
   |
   |-- home/
   |    |-- views.py                     # APP Views 
   |    |-- urls.py                      # APP Routing
   |    |-- models.py                    # APP Models 
   |    |-- tests.py                     # Tests  
   |    |-- templates/                   # Theme Customisation 
   |         |-- includes                # 
   |              |-- custom-footer.py   # Custom Footer      
   |     
   |-- requirements.txt                  # Project Dependencies
   |
   |-- env.sample                        # ENV Configuration (default values)
   |-- manage.py                         # Start the app - Django default start script
   |
   |-- ************************************************************************
```

<br />

## How to Customize 

When a template file is loaded in the controller, `Django` scans all template directories starting from the ones defined by the user, and returns the first match or an error in case the template is not found. 
The theme used to style this starter provides the following files: 

```bash
# This exists in ENV: LIB/admin_soft
< UI_LIBRARY_ROOT >                      
   |
   |-- templates/                     # Root Templates Folder 
   |    |          
   |    |-- accounts/       
   |    |    |-- login.html           # Sign IN Page
   |    |    |-- register.html        # Sign UP Page
   |    |
   |    |-- includes/       
   |    |    |-- footer.html          # Footer component
   |    |    |-- sidebar.html         # Sidebar component
   |    |    |-- navigation.html      # Navigation Bar
   |    |    |-- scripts.html         # Scripts Component
   |    |
   |    |-- layouts/       
   |    |    |-- base.html            # Masterpage
   |    |    |-- base-fullscreen.html # Masterpage for Auth Pages
   |    |
   |    |-- pages/       
   |         |-- index.html           # Dashboard page
   |         |-- profile.html         # Settings  Page
   |         |-- *.html               # All other pages
   |    
   |-- ************************************************************************
```

When the project requires customization, we need to copy the original file that needs an update (from the virtual environment) and place it in the template folder using the same path. 

> For instance, if we want to **customize the footer.html** these are the steps:

- ✅ `Step 1`: create the `templates` DIRECTORY inside the `home` app
- ✅ `Step 2`: configure the project to use this new template directory
  - `core/settings.py` TEMPLATES section
- ✅ `Step 3`: copy the `footer.html` from the original location (inside your ENV) and save it to the `home/templates` DIR
  - Source PATH: `<YOUR_ENV>/LIB/admin_soft/includes/footer.html`
  - Destination PATH: `<PROJECT_ROOT>home/templates/includes/footer.html`

> To speed up all these steps, the **codebase is already configured** (`Steps 1, and 2`) and a `custom footer` can be found at this location:

`home/templates/includes/custom_footer.html` 

By default, this file is unused because the `theme` expects `footer.html` (without the `custom-` prefix). 

In order to use it, simply rename it to `footer.html`. Like this, the default version shipped in the library is ignored by Django. 

In a similar way, all other files and components can be customized easily.

<br />

## Deploy on [Render](https://render.com/)

- Create a Blueprint instance
  - Go to https://dashboard.render.com/blueprints this link.
- Click `New Blueprint Instance` button.
- Connect your `repo` which you want to deploy.
- Fill the `Service Group Name` and click on `Update Existing Resources` button.
- After that your deployment will start automatically.

At this point, the product should be LIVE.

<br />

---
 [Django Boilerplate](https://appseed.us/boilerplate-code/django-dashboard/) - **Django** starter provided by **[AppSeed](https://appseed.us/)**
