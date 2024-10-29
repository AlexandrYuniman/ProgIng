# Тема 8. Основы объектно-ориентированног программирования
Отчет по Теме #8 выполнил(а):
- Юниман Александр Сергеевич
- ИВТ-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1

### Создайте класс "Car" с атрибутами производитель и модель. Создайте объект этого класса. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

my_car = Car("Lada", "2107")
```
## Выводы


## Лабораторная работа №2

### Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину "поехать". Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Lada", "2107")
my_car.drive()
```
### Результат.

## Выводы


## Лабораторная работа №3

### Создайте новый класс "ElectricCar” с методом “charge" и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

class ElectricCar(Car):
    def __init__(self, make, model, battery_capacity):
        super().__init__(make, model)
        self.battery_capacity = battery_capacity

    def charge(self):
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")

my_electric_car = ElectricCar("Tesla", "Model X", 80)
my_electric_car.drive()
my_electric_car.charge()
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/lab3.png)

## Выводы


## Лабораторная работа №4

### Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать.

```python
class Car:
    def __init__(self, make, model):
        self._make = make
        self.__model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Lada", "2107")
print(my_car._make)
print(my_car.__model)
my_car.drive()
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/lab4.png)

## Выводы


## Лабораторная работа №5

### Реализуйте полиморфизм создав основной (общий) класс "Shape", а также еще два класса "Rectangle" и "Circle". Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. 

```python
import math

class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
            return self.width * self.height
        

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * pow(self.radius, 2)
    
shapes = [Rectangle(5,5), Circle(2)]
for shape in shapes:
    print(shape.area())
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/lab5.png)

## Выводы


## Самостоятельная работа №1

### Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, name, length, weigth):
        self.name = name
        self.length = length
        self.weigth = weigth

my_animal = Animal('Ramzes', 40, 6)
print(my_animal.name)
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/sam1.png)

## Выводы

## Самостоятельная работа №2

### Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, name, length, weigth):
        self.name = name
        self.length = length
        self.weigth = weigth

    def run(self, speed):
        print(f"{self.name} бежить со скоростью {speed} km/h")

my_animal = Animal('Рамзес', 40, 6)
print(my_animal.name)
my_animal.run(14)
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/sam2.png)

## Выводы

## Самостоятельная работа №3

### Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, name, length, weigth):
        self.name = name        
        self.length = length
        self.weigth = weigth

    def run(self, speed):
        print(f"{self.name} бежить со скоростью {speed} km/h")

class Wolf(Animal):
    def __init__(self, name, length, weigth, role):
        super().__init__(name, length, weigth)
        self.role = role
    
    def howl(self):
        print(f"Сейчас воет волк {self.role}")

my_wolf = Wolf('Волк',200, 80, 'Альфа')
my_wolf.howl()
my_wolf.run(60)
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/sam3.png)

## Выводы

## Самостоятельная работа №4

### Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, name, length, weigth):
        self._name = name        
        self.__length = length
        self.__weigth = weigth

    def run(self, speed):
        print(f"{self.name} бежить со скоростью {speed} km/h")

class Wolf(Animal):
    def __init__(self, name, length, weigth, role):
        super().__init__(name, length, weigth)
        self.role = role
    
    def howl(self):
        print(f"Сейчас воет волк {self.role}")

my_wolf = Wolf('Волк',200, 80, 'Альфа')
print(my_wolf._name)
print(my_wolf.length)
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/sam4.png)

## Выводы

## Самостоятельная работа №5

### Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, name, length, weigth):
        self._name = name        
        self.__length = length
        self.__weigth = weigth

    def run(self, speed):
        print(f"{self.name} бежить со скоростью {speed} km/h")

    def sound(self):
        pass

class Wolf(Animal):
    def __init__(self, name, length, weigth, role):
        super().__init__(name, length, weigth)
        self.role = role
    
    def sound(self):
        print(f"{self.role} сейчас воет на луну")

class Lion(Animal):
    def __init__(self, name, length, weigth):
        super().__init__(name, length, weigth)

    def sound(self):
        print(f"{self._name} сейчас рычит")

my_wolf = Wolf('Волк',200, 80, 'Альфа')
my_wolf.sound()

my_lion = Lion('Симба', 500, 300)
my_lion.sound()
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_8/pic/sam5.png)

## Выводы

