
2.1 Назва роботи:

Лабораторна робота №10: Основи об'єктно-орієнтованого програмування (ООП) на Python
2.2 Мета роботи:

Метою цієї лабораторної роботи є ознайомлення з основними принципами об'єктно-орієнтованого програмування (ООП) та їх застосування на мові програмування Python. Очікувані результати включають здатність створювати класи, реалізовувати успадкування, поліморфізм та інкапсуляцію.
2.3 Опис завдання:

Необхідно виконати наступні завдання:

    Створення класу Student
        Реалізувати конструктор для ініціалізації імені, віку та оцінки студента.
    Створення методу display_info
        Додати метод, який повертає інформацію про студента.
    Успадкування
        Створити клас Animal з конструктором та методом make_sound. Реалізувати клас Dog, який успадковує Animal.
    Поліморфізм
        Створити базовий клас Bird з методом fly. Реалізувати два класи Sparrow та Penguin, які перевизначають метод fly.
    Інкапсуляція
        Створити клас Encapsulation з публічним, захищеним і приватним атрибутами.
    Створення класу Rectangle
        Реалізувати конструктор та метод для обчислення периметру.
    Клас AverageCalculator
        Створити клас, який обчислює середнє значення чисел в списку.

2.4 Виконання роботи:
Структура проекту:

Проект складається з одного файлу main.py, в якому реалізовані класи та методи згідно завдання.
Опис кожного файлу та його призначення:

    main.py: містить реалізацію класів та методів, а також приклади їх використання.

Опис основних функцій та методів з поясненням їх роботи:

    Клас Student:

    python

class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade

    def display_info(self):
        return f"Name: {self.name}, Age: {self.age}, Grade: {self.grade}"

Клас Animal і успадкований Dog:

python

class Animal:
    def __init__(self, name, sound):
        self.name = name
        self.sound = sound

    def make_sound(self):
        return f"{self.name}: {self.sound}"

class Dog(Animal):
    def __init__(self, name, sound, breed):
        super().__init__(name, sound)
        self.breed = breed

Поліморфізм в класах Bird, Sparrow, Penguin:

python

class Bird:
    def fly(self):
        return None

class Sparrow(Bird):
    def fly(self):
        return "Sparrow flies high"

class Penguin(Bird):
    def fly(self):
        return "Penguin cannot fly"

Інкапсуляція в класі Encapsulation:

python

class Encapsulation:
    def __init__(self, public, _private, __protected):
        self.public = public
        self._private = _private
        self.__protected = __protected

Клас Rectangle з методом для обчислення периметру:

python

class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def calculate_perimeter(self):
        return 2 * (self.width + self.height)

Клас AverageCalculator для обчислення середнього значення:

python

    class AverageCalculator:
        def __init__(self, numbers):
            self.numbers = numbers

        def calculate_average(self):
            return sum(self.numbers) / len(self.numbers)

Приклади використання:

python

# Task 1
student = Student(name="Ivan", age=30, grade="2")
print(student.name, student.age, student.grade)

# Task 2
print(student.display_info())

# Task 3
animal = Animal(name="Lala", sound="")
dog = Dog(name="Lala", sound="Auuuuuuuuuu", breed="spitz")
print(animal.make_sound())
print(dog.make_sound(), dog.breed)

# Task 4
bird = Bird()
sparrow = Sparrow()
penguin = Penguin()
print(bird.fly())
print(sparrow.fly())
print(penguin.fly())

# Task 5
obj = Encapsulation(1, 2, 3)
print(obj.public)
print(obj._private)
print(obj._Encapsulation__protected)  # Note: accessing __protected through name mangling

# Task 6
rectangle = Rectangle(width=5, height=4)
print(rectangle.calculate_perimeter())

# Task 7
numbers = [5, 10, 15, 20]
avg_calculator = AverageCalculator(numbers)
print(avg_calculator.calculate_average())

2.5 Результати:

Отримані результати демонструють правильність роботи класів та методів для кожного з завдань. Кожен приклад використання підтверджує коректність реалізації.
2.6 Висновки:

Мета роботи була досягнута: реалізовані класи для обробки даних та об'єктно-орієнтоване програмування (ООП) на Python. Проблеми, які виникли під час виконання роботи, були пов'язані з розумінням концепцій ООП, але були успішно вирішені.
2.7 Інструкції з запуску:
Вимоги до середовища:

    Python 3.6 або вище

Запуск програми:

    Завантажте файл main.py.
    Запустіть файл main.py за допомогою команди:

    bash

python main.py

Програма виведе результати роботи класів та методів на екран.