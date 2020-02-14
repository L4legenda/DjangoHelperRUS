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
#Модель текста
name = models.CharField(max_length=50)
```
