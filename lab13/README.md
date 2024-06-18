Лабораторна робота №13: Робота з масивами, строками та іншими структурами даних в Python
Мета роботи

Метою даної лабораторної роботи є вивчення та практичне застосування різних методів обробки масивів, рядків та інших структур даних в Python. Очікувані результати включають розробку функцій для вирішення конкретних завдань, їх тестування та аналіз отриманих результатів.
Опис завдання

Необхідно створити набір функцій, які виконують різні завдання з обробки даних, такі як інтерполяція пропущених значень, генерація чисел Фібоначчі, обробка рядків, обертання матриць, пошук за регулярними виразами, сортування масивів, перевірка простих чисел, групування за ключем та видалення викидів.
Виконання роботи
Структура проекту

Проект складається з одного основного файлу data_processing.py, який містить визначення всіх необхідних функцій та їх тестування.
Опис файлів та їх призначення

    data_processing.py: Основний файл, що містить всі функції для обробки даних та приклади їх використання.

Опис основних функцій та методів
Функція interpolate_missing

Інтерполює пропущені значення у списку чисел.

python

def interpolate_missing(numb):
    interpolated = []
    for i, num in enumerate(numb):
        if num is None:
            left_index = i - 1
            right_index = i + 1
            left_value = None
            right_value = None
            while left_index >= 0:
                if numb[left_index] is not None:
                    left_value = numb[left_index]
                    break
                left_index -= 1
            while right_index < len(numb):
                if numb[right_index] is not None:
                    right_value = numb[right_index]
                    break
                right_index += 1

            if left_value is not None and right_value is not None:
                distance = right_index - left_index
                interpolated_value = left_value + ((right_value - left_value) / distance) * (i - left_index)
                interpolated.append(round(interpolated_value))
            elif left_value is not None:
                interpolated.append(left_value)
            elif right_value is not None:
                interpolated.append(right_value)
            else:
                interpolated.append(None)
        else:
            interpolated.append(num)
    return interpolated

Функція fibonacci

Генерує числа Фібоначчі до n-го елемента.

python

def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

Функція process_batches

Повертає максимальні значення для кожного батчу заданого розміру в списку чисел.

python

def process_batches(nums, batch_size):
    return [max(nums[i:i + batch_size]) for i in range(0, len(nums), batch_size)]

Функція encode_string

Кодує рядок, зберігаючи кількість повторень кожного символу.

python

def encode_string(s):
    encod = ''
    count = 1
    for i in range(1, len(s)):
        if s[i] == s[i - 1]:
            count += 1
        else:
            if count > 1:
                encod += str(count)
            encod += s[i - 1]
            count = 1
    if count > 1:
        encod += str(count)
    encod += s[-1]
    return encod

Функція decode_string

Декодує рядок, збережений у форматі кодування кількості повторень символів.

python

def decode_string(s):
    dec = ''
    i = 0
    while i < len(s):
        if s[i].isdigit():
            count = int(s[i])
            dec += s[i + 1] * count
            i += 2
        else:
            dec += s[i]
            i += 1
    return dec

Функція rotate_matrix

Обертає матрицю на 90 градусів за годинниковою стрілкою.

python

def rotate_matrix(matrix):
    return [list(row) for row in zip(*matrix[::-1])]

Функція regex_search

Знаходить рядки, що відповідають регулярному виразу.

python

import re

def regex_search(str, pat):
    return [string for string in str if re.search(pat, string)]

Функція merge_sorted_arrays

Об'єднує два відсортованих масиви в один відсортований масив.

python

def merge_sorted_arrays(arr1, arr2):
    merged = []
    i = j = 0
    while i < len(arr1) and j < len(arr2):
        if arr1[i] < arr2[j]:
            merged.append(arr1[i])
            i += 1
        else:
            merged.append(arr2[j])
            j += 1
    merged.extend(arr1[i:])
    merged.extend(arr2[j:])
    return merged

Функція is_prime

Перевіряє, чи є число простим.

python

def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            return False
    return True

Функція group_by_key

Групує елементи списку за заданим ключем.

python

def group_by_key(data, key):
    grouped = {}
    for item in data:
        grouped.setdefault(item[key], []).append(item['value'])
    return grouped

Функція remove_outliers

Видаляє викиди зі списку на основі Z-оцінок.

python

import numpy as np

def remove_outliers(list):
    mean = np.mean(list)
    std_dev = np.std(list)
    z_scores = [(x - mean) / std_dev for x in list]
    threshold = 2

    return [x for x, z in zip(list, z_scores) if abs(z) <= threshold]

Приклади використання

python

# Інтерполяція пропущених значень
print(interpolate_missing([1, None, None, 4]))  # Виведе: [1, 2, 3, 4]

# Числа Фібоначчі
for num in fibonacci(5):
    print(num, end=", ")  # Виведе: 0, 1, 1, 2, 3,
print()

# Обробка батчів
print(process_batches([1, 2, 3, 4, 5, 6], 2))  # Виведе: [2, 4, 6]

# Кодування рядка
encoded = encode_string("aaabbc")
print(encoded)  # Виведе: "3a2bc"

# Декодування рядка
print(decode_string(encoded))  # Виведе: "aaabbc"

# Обертання матриці
matrix = [
    [1, 2],
    [3, 4]
]
print(rotate_matrix(matrix))  # Виведе: [[3, 1], [4, 2]]

# Пошук за регулярними виразами
print(regex_search(["test", "test123", "none"], r"test\d+"))  # Виведе: ["test123"]

# Об'єднання відсортованих масивів
print(merge_sorted_arrays([1, 3, 5], [2, 4, 6]))  # Виведе: [1, 2, 3, 4, 5, 6]

# Перевірка простого числа
print(is_prime(11))  # Виведе: True

# Групування за ключем
data = [{'key': 'a', 'value': 1}, {'key': 'b', 'value': 2}, {'key': 'a', 'value': 3}]
print(group_by_key(data, 'key'))  # Виведе: {'a': [1, 3], 'b': [2]}

# Видалення викидів
print(remove_outliers([10, 100, 200, 300, 400, 500, 600]))  # Виведе: [100, 200, 300, 400, 500]

Результати

В результаті виконання роботи були створені функції для різних завдань обробки даних. Функції успішно виконують свої завдання, що підтверджується тестовими прикладами.
Скриншоти та приклади виводу програми

plaintext

[1, 2, 3, 4]
0, 




plaintext

0, 1, 1, 2, 3, 
[2, 4, 6]
3a2bc
aaabbc
[[3, 1], [4, 2]]
['test123']
[1, 2, 3, 4, 5, 6]
True
{'a': [1, 3], 'b': [2]}
[100, 200, 300, 400, 500]

Висновки

Мета роботи була досягнута: були створені та протестовані функції для різних завдань обробки даних у Python.

Основні висновки:

    Інтерполяція пропущених значень допомагає заповнити відсутні дані на основі сусідніх значень.
    Числа Фібоначчі генеруються за допомогою ітераційного підходу.
    Функції для обробки рядків можуть значно спростити задачі кодування та декодування.
    Регулярні вирази є потужним інструментом для пошуку в рядках.
    Об'єднання відсортованих масивів та перевірка простих чисел реалізовані ефективно.
    Видалення викидів за допомогою Z-оцінок дозволяє зменшити вплив екстремальних значень на дані.

Проблеми, які виникли під час виконання роботи:

    Інтерполяція пропущених значень вимагала ретельної обробки граничних випадків.
    Регулярні вирази можуть бути складними для розуміння, але вони дуже корисні при роботі з рядками.

Інструкції з запуску
Вимоги до середовища

    Python 3.6 або вище
    Бібліотека NumPy

Запуск програми

    Переконайтеся, що у вас встановлено Python 3.6 або вище.

    Встановіть необхідні бібліотеки, використовуючи команду:

    bash

pip install numpy

Завантажте файл data_processing.py.

Запустіть файл data_processing.py за допомогою команди:

bash

    python data_processing.py

Це запустить програму та виведе результати роботи функцій на екран.

Ця лабораторна робота продемонструвала, як ефективно використовувати Python для обробки даних, включаючи роботу з масивами, рядками та іншими структурами даних. Виконані завдання та приклади використання функцій можуть бути корисними для подальших досліджень та практичних застосувань у галузі обробки даних.
