# url запросы

### Подключение модуля

Должен быть подключен модуль
```python
#file 'settings.py'

INSTALLED_APPS = [
    ...
    'my_app',
]
```

Настройка url запроса
```python
#file 'urls.py'

from django.conf.urls import url, include

urlpatterns = [
    url(r'', include("my_app.urls")),
]
```

### Подключение запроса
```python
#file 'urls.py'

from django.conf.urls import url

from . import views

urlpatterns = [
    url(r'^$', views.index),
]
