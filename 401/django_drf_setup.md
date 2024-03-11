# Setting up DRF

Follow Django Project Setup until creating Views.
**NOTE: Templates will not be used**

## Common Steps

- In this setup demo, we have a book app with a Book model.
- >`pip install djangorestframework`
- in settings.py, add 'rest_framework' to INSTALLED_APPS.
- In views.py, use the following:

```python
from rest_framework.generics import ListCreateAPIView, RetrieveUpdateDestroyAPIView
from .models import Book
from .serializers import BookSerializer

class BookList(ListCreateAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer

class BookDetail(RetrieveUpdateDestroyAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```

- make a serializer class:

>`touch books/serializers.py`

- in serializers.py, use the following:

```python
from rest_framework import serializers
from .models import Book

class BookSerializer(serializers.ModelSerializer):
  class Meta:
    fields = ("insert", "desired", "model", "attributes")
    model = Book
```

- in urls.py at the app level, no real difference from the first tip sheet:

```python
from django.urls import path
from .views import BookList, BookDetail

urlpatterns = [
    path('', BookList.as_view(), name='book_list'),
    path('<int:pk>/', BookDetail.as_view(), name='book_detail'),
]
```

- in urls.py at the project level, need to include a path for 'rest_framework.urls':

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/v1/books/', include('books.urls')),
    path('api-auth/', include('rest_framework.urls')),
]
```
