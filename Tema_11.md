# Тема 11. Итераторы и генераторы
Отчет по Теме #11 выполнил(а):
- Юниман Александр Сергеевич
- ИВТ-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | - |
| Задание 3 | + | 
| Задание 4 | + | 
| Задание 5 | + | 

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1

### 

```python
numbers = [0,1,2,3,4,5]
for item in numbers:
    print(item)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_11/pic/lab1.png)

## Выводы 
Создается список и проходимся по нему итератором


## Лабораторная работа №2

### 

```python
class CountDown:
    def __init__(self, start):
        self.count = start + 1

    def __iter__(self):
        return self
    
    def __next__(self):
        self.count -= 1
        if self.count < 0:
            raise StopIteration
        return self.count
    

if __name__ == '__main__':
    counter = CountDown(5)
    for i in counter:
        print(i)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_11/pic/lab2.png)

## Выводы 
Создается класс итератор, в котором реализуются методы __iter__ и __next__(

## Лабораторная работа №3

### 

```python
a = [i ** 2 for i in range(1,5)]

print ('a - ', a)
for i in a:
    print(i)

print('iter(a) - ', iter(a))
for i in a:
    print(i)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_11/pic/lab3.png)

## Выводы 
Список генерируется с помощью генераторв, после чего выводится

## Лабораторная работа №4

### 

```python
b = (i ** 2 for i in range(1,5))
print(b)
print ('first')
for i in b:
    print(i)

print('second')
for i in b:
    print(i)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_11/pic/lab4.png)

## Выводы 
Список создается при помощи генераторного выражения

## Лабораторная работа №5

### 

```python
def countdown(count):
    while count >= 0:
        yield count
        count -= 1

if __name__ == '__main__':
    counter = countdown(5)
    for i in counter:
        print(i)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_11/pic/lab5.png)

## Выводы 
Список как в первом задании, но с использованием генератора и yield

## Самостоятельная работа №5

### 
```python
def fib(n):
    first, second = 1, 1
    for __ in range(n):
        yield second
        first, second = second, first + second

print(list(fib(200))) 
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_11/pic/sam1.png)

## Выводы
Программа считает числа Фибоначчи с минимальными затратами ресурсов
