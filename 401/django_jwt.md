# Setting up JWT

For using Simple JWT, [these docs](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/getting_started.html) were used.

## Common Steps

- >`pip install djangorestframework-simplejwt`
- in settings.py, add to REST_FRAMEKWORK:

```python
 'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.SessionAuthentication',
        'rest_framework.authentication.BasicAuthentication',
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
```

- in urls.py, import jwt view:

>`from rest_framework_simplejwt import views as jwt_views`

- now add two new url patterns:

```python
    ...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
    ...
```
