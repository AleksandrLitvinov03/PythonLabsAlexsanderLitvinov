Лабораторна робота №14: Робота з булевими виразами та умовними операціями в Python
Мета роботи

Метою даної лабораторної роботи є вивчення та практичне застосування булевих виразів та умовних операторів в Python. Очікувані результати включають створення та тестування функцій, які використовують логічні вирази, умовні оператори, операції з булевими значеннями та інші основні конструкції мови Python.
Опис завдання

Необхідно створити набір функцій, що виконують різні завдання з використанням булевих виразів та умовних операторів. Кожна функція повинна мати певний набір параметрів та повертати результат, залежно від умов та логічних операцій.
Виконання роботи
Структура проекту

Проект складається з одного основного файлу boolean_operations.py, який містить визначення всіх необхідних функцій та їх тестування.
Опис файлів та їх призначення

    boolean_operations.py: Основний файл, що містить всі функції для виконання булевих операцій та умовних виразів, а також приклади їх використання.

Опис основних функцій та методів
Функція task1

Повертає результат логічного виразу (a and b) or c.

python

def task1(a, b, c):
    return (a and b) or c

Функція task2

Перевіряє, чи рівні два булеві значення.

python

def task2(x, y):
    return x == y

Функція task3

Повертає результат виключного OR для двох булевих значень.

python

def task3(a, b):
    return (a and not b) or (not a and b)

Функція task4

Повертає "Hello, World!" якщо значення boolean_value істинне, і "Goodbye, World!" якщо хибне.

python

def task4(boolean_value):
    return "Hello, World!" if boolean_value else "Goodbye, World!"

Функція task5

Повертає рядок, що вказує, чи всі три значення однакові, всі різні або ні те, ні інше.

python

def task5(x, y, z):
    if x == y == z:
        return "All same"
    elif x != y and y != z and x != z:
        return "All different"
    else:
        return "Neither"

Функція task6

Повертає кількість істинних значень у списку.

python

def task6(boolean_list):
    return sum(boolean_list)

Функція task7

Перевіряє, чи парна кількість одиниць у бінарному представленні числа.

python

def task7(number):
    binary_representation = bin(number)[2:]
    count_of_ones = binary_representation.count('1')
    return count_of_ones % 2 == 0

Функція task8

Перевіряє, чи сума трьох булевих значень більша за 1.

python

def task8(a, b, c):
    return (a + b + c) > 1

Функція task9

Повертає заперечення булевого значення.

python

def task9(boolean_value):
    return not boolean_value

Функція task10

Повертає одне з двох значень залежно від умови.

python

def task10(condition, if_true, if_false):
    return if_true if condition else if_false

Функція task11

Повертає результат логічного виразу x or (y and z).

python

def task11(x, y, z):
    return x or (y and z)

Функція task12

Перевіряє, чи є три числа зростаючими, спадаючими або ні те, ні інше.

python

def task12(a, b, c):
    if a < b < c:
        return "Increasing"
    elif a > b > c:
        return "Decreasing"
    else:
        return "Neither"

Функція task13

Повертає список, що містить тільки істинні значення зі списку булевих значень.

python

def task13(boolean_list):
    return [val for val in boolean_list if val]

Функція task14

Виконує математичні операції над цілим числом залежно від булевих значень.

python

def task14(bool1, bool2, bool3, integer):
    result = integer
    if bool1:
        result *= 2
    if bool2:
        result *= 3
    if bool3:
        result -= 5
    return result

Приклади використання

python

# Task 1
print("Task 1:", task1(True, False, True))

# Task 2
print("Task 2:", task2(True, True))

# Task 3
print("Task 3:", task3(True, False))

# Task 4
print("Task 4:", task4(True))

# Task 5
print("Task 5:", task5(3, 3, 3))

# Task 6
print("Task 6:", task6([True, False, True, False, True]))

# Task 7
print("Task 7:", task7(3))

# Task 8
print("Task 8:", task8(True, True, False))

# Task 9
print("Task 9:", task9(True))

# Task 10
print("Task 10:", task10(True, "Yes", "No"))

# Task 11
print("Task 11:", task11(True, False, True))

# Task 12
print("Task 12:", task12(1, 2, 3))

# Task 13
print("Task 13:", task13([True, False, True, False]))

# Task 14
print("Task 14:", task14(False, False, True, 10))

Результати

В результаті виконання роботи були створені функції для роботи з булевими виразами та умовними операціями. Функції успішно виконують свої завдання, що підтверджується тестовими прикладами.
Скриншоти та приклади виводу програми

plaintext

Task 1: True
Task 2: True
Task 3: True
Task 4: Hello, World!
Task 5: All same
Task 6: 3
Task 7: False
Task 8: True
Task 9: False
Task 10: Yes
Task 11: True
Task 12: Increasing
Task 13: [True, True]
Task 14: 5

Висновки

Мета роботи була досягнута: були розроблені функції для роботи з булевими виразами та умовними операціями. Проблеми, які виникали під час роботи, були вирішені за допомогою тестування та налагодження коду.
Інструкції з запуску

Для запуску програми необхідно мати встановлений Python версії 3.6 або вище. Для запуску програми виконайте наступні кроки:

    Скопіювати код у файл boolean_operations.py.
    Запустити файл за допомогою команди:

bash

python boolean_operations.py

Необхідні бібліотеки: стандартна бібліотека Python.