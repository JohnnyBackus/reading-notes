# Setting up Gunicorn

Gunicorn docs can be found [here](https://gunicorn.org/)

## Common Steps

- `docker compose up --build` not already in Docker.

- `docker compose exec web pip install gunicorn`

- update `services: web: command` in docker-compose.yml to state `gunicorn books_api_project.wsgi:application --bind 0.0.0.0:8000 --workers 4`

- workers is optional, but may increase performance

*gunicorn negatively affects default styling. This can be restored with whitenoise...*

- `docker compose exec web pip install whitenoise`

- in settings.py, add `'whitenoise.middleware.WhiteNoiseMiddleware'` to MIDDLEWARE after `'django.middleware.security.SecurityMiddleware'` and before any other middleware.

- also in settings.py, add `STATIC_ROOT = BASE_DIR / "staticfiles"` underneath STATIC_URL = "static/"

- >`docker compose exec web python manage.py collectstatic`

- compose down and then compose up --build to view applied css changes.
