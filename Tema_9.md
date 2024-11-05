# Тема 9. ООП на Python: концепции, принципы и примеры реализации
Отчет по Теме #9 выполнил(а):
- Юниман Александр Сергеевич
- ИВТ-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | 
| Задание 3 | + | 
| Задание 4 | + | 
| Задание 5 | + | 

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1

### Допустим, что вы решили оригинально и немного странно познакомится с человеком. Для этого у вас должен быть написан свой класс на Python, который будет проверять угадал ваше имя человек или нет. Для этого создайте класс, указав в свойствах только имя. Дальше создайте функцию init (), а в ней сделайте проверку на то угадал человек ваше имя или нет. Также можете проверить что будет, если в этой функции указав атрибут, который не указан в вашем классе, например, попробуйте вызвать фамилию.

```python
class Ivan: 
    __slots__ = ['name']

    def __init__(self, name):
        if name == 'Иван':
            self.name = f"Да, я {name}"
        else:
            self.name = f"Я не {name}, а Иван"

person1 = Ivan('Алексей')
person2 = Ivan('Иван')
print(person1.name)
print(person2.name)

person2.surname = 'Петров'

```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_9/pic/lab1.png)

## Выводы

## Лабораторная работа №2

### Вам дали важное задание, написать продавцу мороженого программу, которая будет писать добавили ли топпинг в мороженое и цену после возможного изменения. Для этого вам нужно написать класс, в котором
будет определяться изменили ли состав мороженого или нет. В этом классе реализуйте метод, выводящий на печать «Мороженое с {ТОППИНГ}» в случае наличия добавки, а иначе отобразится следующая фраза: «Обычное мороженое». При этом программа должна воспринимать как топпинг только атрибуты типа string.

```python
class Icecream:
    def __init__(self, ingredient = None):
        if isinstance(ingredient, str):
            self.ingredient = ingredient
        else:
            self.ingredient = None
        
    def composition(self):
        if self.ingredient:
            print(f"Мороженое с {self.ingredient}")
        else: 
            print('Обычное мороженое')

icecream = Icecream()
icecream.composition()
icecream = Icecream('шоколадом')
icecream.composition()
icecream = Icecream(5)
icecream.composition()
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_9/pic/lab2.png)

## Выводы


## Лабораторная работа №3

### Петя - начинающий программист и на занятиях ему сказали реализовать икапсу...что-то. А вы хороший друг Пети и ко всему прочему прекрасно знаете, что икапсу... что-то это инкапсуляция, поэтому решаете помочь вашему другу с написанием класса с инкапсуляцией. Ваш класс будет не просто инкапсуляцией, а классом с сеттером, геттером и деструктором. После написания класса вам необходимо продемонстрировать что все написанные вами функции работают.
Также вас необходимо объяснить Пете почему на скриншоте ниже в консоли выводится ошибка.

```python
class MyClass:
    def __init__(self, value):
        self._value = value

    def set_value(self, value):
        self._value = value

    def get_value(self):
        return self._value
    
    def del_value(self):
        del self._value

    value = property(get_value, set_value, del_value, "Свойство value")

obj = MyClass(42)
print(obj.get_value())
obj.set_value(45)
print(obj.get_value())
obj.set_value(100)
print(obj.get_value())
obj.del_value()
print(obj.get_value())
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_9/pic/lab3.png)

## Выводы


## Лабораторная работа №4

### Вам прекрасно известно, что кошки И собаки являются млекопитающими, но компьютер этого не понимает, поэтому вам нужно написать три класса: Кошки, Собаки, Млекопитающие. И при помощи "наследования" объяснить компьютеру что кошки и собаки млекопитающие. Также добавьте какой-нибудь свой атрибут для кошек и собак, чтобы показать, что они чем-то отличаются друг от друга.
это

```python
class Mammal:
    className = 'Mammal'

class Dog(Mammal):
    species = 'canine'
    sounds = 'wow'

class Cat(Mammal):
    species = 'feline'
    sounds = 'meow'

dog = Dog()
cat = Cat()
print(f"Dog is {dog.className}, but they say {dog.sounds}")
print(f"Cat is {cat.className}, but they say {cat.sounds}")
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_9/pic/lab4.png)

## Выводы


## Лабораторная работа №5

### На разных языках здороваются по-разному, но суть остается одинаковой, люди друг с другом здороваются. Давайте вместе с вами реализуем программу с полиморфизмом, которая будет описывать всю суть первого предложения задачи. Для этого мы можем выбрать два языка, например, русский и английский и написать для них отдельные классы, в которых будет в виде атрибута слово, которым здороваются на этих языках. А также напишем функцию, которая будет выводить информацию о том, как на этих языках здороваются.

```python
class Russian:
    @staticmethod
    def greeting():
        print('Привет')

class English:
    @staticmethod
    def greeting():
        print('Hello')

def greet(language):
    language.greeting()

Ivan = Russian()
greet(Ivan)
John = English()
greet(John)
```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_9/pic/lab5.png)

## Выводы


## Самостоятельная работа №1

### Задание садовник и помидоры

```python
class Tomato:
    states = {0: 'отсутствует', 1: 'цветение', 2: 'зеленый', 3: 'красный'}
    
    def __init__(self, index):
        self._index = index
        self._state = 0  
    
    def grow(self):
        self._state += 1
    
    def is_ripe(self):
        if self._state == 3:
            return True
        else:
            return False

class TomatoBush:
    def __init__(self, numb_of_tomatoes):
        self.tomatoes = [Tomato(i) for i in range(numb_of_tomatoes)]
    
    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()
    
    def all_are_ripe(self):        
        if (all(tomato.is_ripe() for tomato in self.tomatoes)):
            return True
        else:
            return False
    
    def give_away_all(self):
        self.tomatoes.clear()
        

class Gardener:
    def __init__(self, name, plant):
        self.name = name
        self._plant = plant
        #Динамические свойства
    
    def work(self):
        self._plant.grow_all()
        print(f"Садовник {self.name} поработал, стадия созревания теперь {self._plant.tomatoes[0].states[self._plant.tomatoes[0]._state]}" )
    
    def harvest(self):
        if self._plant.all_are_ripe():
            print("Урожай собран")
            self._plant.give_away_all()    
            print('Кусты теперь пустые')        
        else:
            print("Томаты еще не созрели, рано собирать урожай")
    
    @staticmethod
    def knowledge_base():
        print("Справка по садоводству")

Gardener.knowledge_base()
firstBush = TomatoBush(3)
secondBush = TomatoBush(5)

firstGardener = Gardener('Петя', firstBush)
secondGardener = Gardener("Вася", secondBush)

firstGardener.work()
firstGardener.harvest()
firstGardener.work()
firstGardener.work()
firstGardener.harvest()


```
### Результат.
![Меню](https://github.com/AlexandrYuniman/ProgIng/blob/Tema_9/pic/sam1.png)

