# Setting up Docker

DockerHub has a [quick reference](https://hub.docker.com/_/python)

## Common Steps

- At root level of repo:

>`touch Dockerfile`
>`touch docker-compose.yml`
>`touch .dockerignore`

- in Dockerfile, include desired actions by Docker. For example:

```python
FROM python:3.11.5-slim-bullseye

# Set environment variables
ENV PIP_DISABLE_PIP_VERSION_CHECK 1
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set work directory
WORKDIR /code

# Install dependencies
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# Copy project
COPY . .
```

- in docker-compose.yml, add:

```python
services:
    web:
        build: .
        ports:
            - "8000:8000"
        command: python manage.py runserver 0.0.0.0:8000
        volumes:
            - .:/code
```

- update ALLOWED_HOSTS in settings.py:

```python
ALLOWED_HOSTS = [
  '127.0.0.1',
  'locahost',
  '0.0.0.0',
]
```

>`docker compose build`
>`docker compose up`

- if restricting API access to authorized users, add to the bottom of settings.py:

```python
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ],
}
```

- to create custom permissions, create a permissions.py file.
- see [Django-REST-framework-permissions](https://www.django-rest-framework.org/api-guide/permissions/#custom-permissions) for more info.
- this is one example:

```python
from rest_framework import permissions


class IsOwnerOrReadOnly(permissions.BasePermission):
    def has_object_permission(self, request, view, obj):
        if request.method in permissions.SAFE_METHODS:
            return True
        
        # uncomment two lines below if I want to allow any authenticated user to update/delete ownerless books
        # if obj.owner == None:
        #     return True
        
        return obj.owner == request.user
```

- in views.py, import custom permission class, i.e. `from .permissions import IsOwnerOrReadOnly`

- also in views.py, add permission_classes to appropriate class. For example:

```python
class BookDetail(RetrieveUpdateDestroyAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
    permission_classes = [IsOwnerOrReadOnly,]
```

- when using permissions, uopdate docker-compose.yml:

```python
services:
    web:
        build: .
        command: python /code/manage.py runserver 0.0.0.0:8000
        volumes:
            - .:/code
        ports:
            - 8000:8000
        depends_on:
            - db

    db:
        image: postgres:14
        volumes:
            - postgres_data:/var/lib/postgresql/data/
        environment:
            - "POSTGRES_HOST_AUTH_METHOD=trust"

volumes:
  postgres_data:
```

- When Docker is running, use CLI command `Docker compose exec web` followed by other commands like `python manage.py migrate`
