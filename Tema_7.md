# Тема 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил(а):
- Юниман Александр Сергеевич
- ИВТ-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | - |
| Задание 3 | + | + |
| Задание 4 | + | - |
| Задание 5 | + | + |
| Задание 6 | + |
| Задание 7 | + |
| Задание 8 | + |
| Задание 9 | + |
| Задание 10 | + |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1 Составьте текстовый файл и положите его в одну директорию с программой на Python. Текстовый файл должен состоять минимум из двух строк.

### 

### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab1.png)


## Лабораторная работа №2

### Напишите программу, которая выведет только первую строку из Вашего файла, при этом используйте конструкцию open()/close().

```python
file = open('inp.txt', 'r')
print(file.readline())
file.close()

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab2.png)

## Выводы

## Лабораторная работа №3

### Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию оpen()/close().

```python
file = open('inp.txt', 'r')
print(file.readlines())
file.close()

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab3.png)

## Выводы

## Лабораторная работа №4

### Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open().


```python
with open('inp.txt', 'r') as file:
    print(file.readlines())

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab4.png)

## Выводы

## Лабораторная работа №5

### Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open().

```python
with open('inp.txt', 'r') as file:
    for line in file:
        print(line)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab5.png)

## Выводы

## Лабораторная работа №6

### Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались.

```python
with open('inp.txt', 'a+') as file:
    file.write('\nHello World, again')

with open('inp.txt', 'r') as file:
    for line in file:
        print(line)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab6.png)

## Выводы

## Лабораторная работа №7

### Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например напишет любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле.

```python
lines = ['one', 'two', 'three']
with open('inp.txt', 'w') as file:
    for line in lines:
        file.write('\nCycle run ' + line)
    print('Done')

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab7.1.png)
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab7.2.png)
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab7.3.png)

## Выводы

## Лабораторная работа №8
### Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory).

```python
import os

def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f"Папка {catalog[0]} содержит:")
        print(f"Директории: {", ".join([folder for folder in catalog[1]])}")
        print(f"Файлы: {", ".join([file for file in catalog[2]])}")
        print('-' * 40)

print_docs("C:\\Users\\Александр\\Desktop\\школа\\ProgIng")

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab8.png)

## Выводы

## Лабораторная работа №9

### Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину (или список слов, если таковых несколько). Проверьте работоспособность программы на своем наборе данных

```python
def longest_words(file):
    with open(file, encoding='utf-8') as file:
        words = file.read().split()
        max_length = len(max(words, key = len))
        for word in words:
            if len(word) == max_length:
                sought_words = word

        if len(sought_words) == 1:
            return sought_words[0]
        return sought_words
    
print(longest_words('inp.txt'))

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab9.png)

## Выводы

## Лабораторная работа №10

### 
Требуется создать csv-файл «rows_300.csv» со следующими
столбцами:
• No - номер по порядку (от 1 до 300);
• Секунда - текущая секунда на вашем ПК;
Микросекунда - текущая миллисекунда на часах.
Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунды.

```python
import csv
import datetime
import time

with open('rows_300.csv', 'w', encoding="utf-8", newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Секунда ', 'Микросекунда '])
    for line in range(1, 301):
        writer.writerow([line, datetime.datetime.now().second,
                         datetime.datetime.now().microsecond])
        time.sleep(0.01)

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/lab10.png)

## Выводы


## Самостоятельная работа №1

### Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.

```python
from collections import Counter
import re

with open('inp.txt', 'r', encoding='utf-8') as file:
    text= file.read()
    words = re.findall(r'\w+', text)
    print(words)
    words_count = Counter(words)
    most_common_word = words_count.most_common(1)[0]

print(f"{len(words)} - количество слов")
print(f"{most_common_word} Самое частое слово")

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/sam1.png)

## Выводы


## Самостоятельная работа №3

### Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.

```python
letters, words, lines = 0,0,0
with open('inp.txt', 'r', encoding='utf-8') as file:
    for line in file:
        lines += 1
        words += len(line.split())  
        letters += sum(1 for char in line if char.isalpha())

print(f"Количество букв: {letters}")
print(f"Количество слов: {words}")
print(f"Количество строк: {lines}")

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/sam3.png)

## Выводы

## Самостоятельная работа №5
### Hужно узнать встречается ли в текстовом файле слово, которое вводится с консоли, если встречается, то нужно узнать количество вхождений

```python
word = input("Введите искомое слово: ")
count = 0

with open('inp.txt', 'r', encoding='utf-8') as file:
    for line in file:
        count += line.lower().split().count(word.lower())

if count > 0:
    print(f"Искомое слово встречается {count} раз")
else:
    print(f"Искомого слова {word} нет в файле")

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_7/pic/sam5.png)

## Выводы
