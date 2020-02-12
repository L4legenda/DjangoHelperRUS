# Изображения

### Пакет для работы с изображениями
```bash
pip install Pillow 
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
DBimage = Picture(
    img = req.FILES['picture'],
    # picture - это name в input
    # смотреть ниже в HTML форма
)
DBimage.save()
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
