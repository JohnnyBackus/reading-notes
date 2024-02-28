# Setting up Admin

After setting up the Django Project and installing Tailwinds (and possibly Flowbite).

## Common Steps

- If not already done, configure the compressor inside the settings.py file (recommend at bottom of file):

```python
COMPRESS_ROOT = BASE_DIR / 'static'

COMPRESS_ENABLED = True

STATICFILES_FINDERS = ('compressor.finders.CompressorFinder',)
```

*To restore default Admin functionality, change STATICFILES_FINDERS to:*

```python
STATICFILES_FINDERS = ('django.contrib.staticfiles.finders.AppDirectoriesFinder', 'compressor.finders.CompressorFinder',)
```

- > $ python manage.py createsuperuser
- consider keeping usernames and passwords in .env file
- in admin.py:

```python
from django.contrib import admin
from .models import Thing

admin.site.register(Thing)
```

- > $ python manage.py makemigrations things
*this command will create migrations folder inside things app with default Migration class*

- > $ python manage.py migrate
*applies migrations to database*

- to display database items by name, add to models.py class Thing:

```python
def __str__(self):
        return self.name
```
 