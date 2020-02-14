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
#Модель названия
name = models.CharField(max_length=50)
# max_length - максимальная длина текста

#Модель числа
num = models.IntegerField()

#Модель даты
field_name = models.DateField()
#Автоматически добаляет сегодняшнюю дату

#Модель текста
text = models.TextField()
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

