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
image = Picture(
    img = req.FILES['picture'],
    # picture - это name в input
)
picture.save()
```
