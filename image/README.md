# Изображения

### Пакет для работы с изображениями
```bash
pip install Pillow 
```

### Настройка папки Media
Папка для сохранения файлов
```python
#file 'settings.py'

MEDIA_ROOT = os.path.join(BASE_DIR, "media/")
MEDIA_URL = "/media/"
```

### Настройка url изображений
```python
#file 'urls.py'

from django.conf.urls.static import static
from django.conf import settings

urlpatterns = [
    ...
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

### Модель
```python
class Picture(models.Model):
    image = models.ImageField(...)
    # Атрибуты:
    # height_field - высота изображения
    # width_field - ширина изображения
    # upload_to - папка для сохранения
    # null - может быть пустым
```

### Добавление в модель
```python
from my_app.models import Picture

DBimage = Picture(
    img = req.FILES['picture'],
    # picture - это name в input
    # смотреть ниже в HTML форма
)
DBimage.save()
```
### Взятие из модели
```python
from my_app.models import Picture

#Все изображения
picture = Picture.objects.all() 

#Последнее изображение
picture = Picture.objects.last()

#Изобрадение по атрибуту
picture = Picture.objects.get(attr="value", ...)
```

### HTML форма 
```HTML
<form action="" method="POST" enctype="multipart/form-data">
    <!--Обязательный токен Django -->
    {% csrf_token %}
    <input type="file" name="picture">
    <input type="submit" value="Submit">
</form>
```

### HTML вывод изображений
```HTML
{% for pic in picture %}
    <img src="{{pic.file.url}}" alt="">
{% endfor %}
```
