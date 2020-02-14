# Модели

### Создание модели
```python
#file models.py

from django.db import models

# Создание модели Picture
class Picture(models.Model):
  ...
```


### Типы моделей
```python
#Тип названия
name = models.CharField(max_length=50)
# max_length - максимальная длина текста

#Тип текста
text = models.TextField()

#Тип числа
num = models.IntegerField()

#Тип дробного числа
float = models.FloatField()

#Тип даты
date = models.DateField()
#Автоматически добаляет сегодняшнюю дату

#Тип дата и время
datetime = models.DateTimeField(default=timezone.now)

#Тип почты
email = models.EmailField()

#Тип файла
file = models.FileField()

#Тип изображения
image = models.ImageField()

#Тип IP адресса
ip = models.GenericIPAddressField()

#Тип названий
url = models.SlugField()

#Тип время
time = models.TimeField()

#Тип url
url = models.URLField()
```

### Внешние ключи
```python
class Manufacturer(models.Model):
    ...

class Car(models.Model):
    #Делат ключ на модель Manufacturer
    manufacturer = models.ForeignKey(Manufacturer, on_delete=models.CASCADE)
    ...
```

