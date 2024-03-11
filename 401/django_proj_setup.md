# Demos: Intro to Django

99% of the time Django apps start the same way.

Today's demo should methodically go through those common steps.

Give lots of time for each step

## If creating a Custom User Model

- see [learn django](https://learndjango.com/tutorials/django-custom-user-model) for a custom user model tutorial
- Tip sheet needs one correction due to changes with Django 5. In the home.html template, replace:

```python
<p><a href="{% url 'logout' %}">Log Out</a></p>
```

with

```python
<form action="{% url 'logout' %}" method="post">
  {% csrf_token %}
  <button type="submit">Log Out</button>
</form>
```

- try [Django Widget Tweaks](https://prettyprinted.com/tutorials/django-widget-tweaks/) for styling the forms

## Typical Steps to Start Django Project

- create project
- define app
  - add app to project
  - add views
  - add urlpatterns
  - add templates
  - add tests

### Create Project

- > $ mkdir django-things
- > $ cd django-things
- Create virtual environment
- Activate virtual environment
- > $ pip install django
- > $ django-admin startproject django_things_project .
  - **NOTE:** the dot at end
- > $ tree
- > $ python manage.py runserver
  - note the unapplied migrations
  - when ready, address the unapplied migrations warning.
  - note how the output gives the commmand to apply the migration.
  - *do not apply migrations before creating a custom user model! See top of this tipsheet for link to custom user model tipsheet*
  - if not creating a custom model:
   > $ python manage.py migrate
- restart dev server and note that warning is gone

### Create App

- Stop dev server
- > $ python manage.py startapp things
- > $ tree
- note that even though the app has been created it has not been integrated into the project as a whole

### Install App

There's a multi-step process that takes place whenever an App is added.
The key components are **views**, **urls**, **templates**.

See other setup guide for **models**, **migrations** and **admin** .

Edit `settings.py`

```python
'things' # add to INSTALLED_APPS list at bottom of list; recommend including comment 'my apps' to distinguish from pre-installed django apps
```

Optionally mention briefly using `things.apps.thingsConfig` instead

Edit `things/views.py`

```python
from django.views.generic import TemplateView

class HomePageView(TemplateView):
    template_name='home.html'
```

Discuss the use of TemplateView and how it is not required but is a common best practice.

Note that *home.html* doesn't exist yet, but will soon. You have to start somewhere.

Create App urls

> $ touch things/urls.py

Note that you pretty much always create urls.py for your app and it's a little odd that Django doesn't do that for you.

Edit `things/urls.py`

```python
from django.urls import path

from .views import HomePageView

urlpatterns=[
    path('', HomePageView.as_view(), name='home'),
]
```

- Note that *HomePageView* is the class we just defined in *views.py*
- Note use of relative import
- Note the use use of *as_view()*
- Note the path *name* key word argument
- Note the case of *urlpatterns*

### Add the App urls to the Project urls

- Edit `django_things_project/urls.py`
- Note that the included comments give an example for us

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('things.urls')),
]
```

### Create Templates

```console
> $ mkdir templates
> $ touch templates/base.html
> $ touch templates/home.html
```

- Note that *base.html* isn't required but is a common practice
- Note that *base.html* is an ancestor template and holds common/reusable markup
- Edit `base.html`
- Generate an html document using emmet abbreviation ! in VS Code
- Add `header`,`main` and `footer` tags within `body`
- Add markup below within the main tag

```django
{% block content %}
<!-- child template content goes here -->
{% endblock content %}
```

**Note** the bracket and percentage sign syntax that is part of [Django template language](https://docs.djangoproject.com/en/4.1/ref/templates/language/)

Edit `home.html`

```django
{% extends 'base.html' %}

{% block content %}
<h1>Home Page</h1>
{% endblock content %}
```

### Add the templates folder

- Note that we need to tell project where to find the templates
- There is a default location for templates but many prefer a templates folder in root of project
  - That is the convention we will be using in class
  - This is example of Django's "opinions" not being perfect fit for our needs.
  - Not a big deal to change when needed.
- Edit `settings.py`
  - Find **TEMPLATES[{...'DIRS': [],...}]** section
  - Add to 'DIRS' list...

```python
BASE_DIR /'templates'
```

### See the page in browser

- Run dev server
  - > $ python manage.py runserver

### Add tests

- Edit `things/tests.py`
- Note that we use `SimpleTestCase` vs. `TestCase`
  - `TestCase` will be used when Models are introduced.
- Django has own testing framework that is similar to PyTest but more Django focused.
- Create and run tests one at a time.

```python
from django.test import SimpleTestCase
from django.urls import reverse

class ThingsTests(SimpleTestCase):
    def test_home_page_status_code(self):
        url = reverse('home')
        response = self.client.get(url)
        self.assertEqual(response.status_code, 200)

    def test_home_page_templete(self):
        url = reverse('home')
        response = self.client.get(url)
        self.assertTemplateUsed(response, 'home.html')
        self.assertTemplateUsed(response, 'base.html')
```

- Run the tests
- > $ python manage.py test

### Adding context

The view can supply data to be used in the template via the `context` object. Usually this data would live in a database, which we'll learn about in the next class.

For now, let's hard code some placeholder data:

```python
def get_context_data(self, **kwargs):
        context = super().get_context_data(**kwargs)
        context["things"] = [
            {
                "image_url": "https://upload.wikimedia.org/wikipedia/commons/b/b3/SoilRake.jpg",
                "title": "Rake",
                "description": "Better than a shovel or a broom for leaves. Like a pitch fork but less pokey.",
                "reference_url": "https://en.wikipedia.org/wiki/Rake_(tool)"
            }, {
                "image_url": "https://upload.wikimedia.org/wikipedia/commons/9/92/Soup_Spoon.jpg",
                "title": "Spoon",
                "description": "An eating utensil. Better for soup and cereal than a fork.",
                "reference_url": "https://en.wikipedia.org/wiki/Spoon"
            }, {
                "image_url": "https://upload.wikimedia.org/wikipedia/commons/thumb/7/71/Spoon_Piknik_i_Parken_2017_%28175930%29.jpg/600px-Spoon_Piknik_i_Parken_2017_%28175930%29.jpg",
                "title": "Spoon",
                "description": "Spoon is also an American rock band from Austin, Texas.",
                "reference_url": "https://en.wikipedia.org/wiki/Spoon_(band)"
            },
        ]

        return context
```

### Using context in template

The `Django template language` gives access context data by using `variables` and `tags`.

#### Variables

Variables look like this: `{{ variable }}`.

When the template engine encounters a variable, it evaluates that variable and replaces it with the result.

#### Tags

Tags look like this: `{% tag %}`.

Tags are more complex than variables: Some create text in the output, some control flow by performing loops or logic, and some load external information into the template to be used by later variables.

Some tags require beginning and ending tags (i.e. `{% tag %} ... tag contents ... {% endtag %}`).

```django
{% for thing in things %}
  <h2>Name: {{ thing.name }}</h2>
  <p>Description: {{ thing.description }}
{% endfor %}
```

Run the dev server. If you're seeing names and descriptions then that's good enough for now.

### Add another page

- Create about.html template
- > $  touch templates/about.html

```django
{% extends 'base.html' %}

{% block content %}
<h1>About Page</h1>
{% endblock content %}
```

- Add a nav
- Edit *base.html*
- Note the url django template keyword
- Note the use of 'home' and 'about' and what they must match

```django
<nav>
    <a href="{% url 'home' %}">Home</a>
    <a href="{% url 'about' %}">About</a>
</nav>
{% block content %}
<!-- child template content goes here -->
{% endblock content %}
{% endraw %}
```

**Note** the use of `url` for the `href`

- Edit *things/urls.py*
  - import AboutView
  - add `path('about', AboutView.as_view(), name='about'),`
- Edit *things/views.py* to add...

```python
class AboutView(TemplateView):
    template_name = 'about.html'
```

- Note that we do not need to update project urls because it's already wired up with the app
- Note that we added templates, views and urls in different order this time - and that's fine.
- Re/Start the server and navigate between the pages

## Add new tests

- Edit *things/tests.py* and add ...

```python
def test_about_page_status_code(self):
    url = reverse('about')
    response = self.client.get(url)
    self.assertEqual(response.status_code, 200)

def test_about_page_templete(self):
    url = reverse('about')
    response = self.client.get(url)
    self.assertTemplateUsed(response, 'about.html')
    self.assertTemplateUsed(response, 'base.html')
```

- > python manage.py test
- DONE!
