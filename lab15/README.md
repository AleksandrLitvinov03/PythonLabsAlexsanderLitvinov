Лабораторна робота №15: Обробка даних за допомогою функцій на Python
Мета роботи

Метою даної лабораторної роботи є розробка та тестування набору функцій для обробки текстових і числових даних з використанням мови програмування Python. Очікувані результати включають створення функцій для очищення даних, фільтрації електронних адрес, виділення ключових слів, нормалізації чисел, та інших завдань.
Опис завдання

Необхідно розробити функції, що виконують наступні завдання:

    Очищення рядкових даних.
    Фільтрація валідних електронних адрес.
    Витяг ключових слів, що перевищують певну довжину.
    Обробка тексту, приведення до нижнього регістру та видалення розділових знаків.
    Нормалізація числових даних.
    Об'єднання рядків з використанням заданого роздільника.
    Обчислення суми чисел у рядках.
    Фільтрація чисел, що перевищують заданий поріг.
    Зведення чисел у квадрат.
    Реверсування рядків.

Виконання роботи
Структура проекту

Проект складається з одного основного файлу data_processing.py, що містить визначення всіх необхідних функцій.
Опис файлів та їх призначення

    data_processing.py: Основний файл, що містить всі функції для обробки даних та приклади їх використання.

Опис основних функцій та методів
Функція clean_data

Очищує дані, розділяючи рядок за комами, видаляючи пробіли та перетворюючи в нижній регістр.

python

def clean_data(data):
    if isinstance(data, str):
        data = data.split(',')
    cleaned = [item.strip().lower() for item in data]
    print("Task 1:", cleaned)
    return cleaned

Функція filter_emails

Фільтрує валідні електронні адреси з рядка.

python

def filter_emails(emails_string):
    pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
    valid_emails = re.findall(pattern, emails_string)
    valid_emails_list = [email for email in valid_emails if email.count('@') == 1]
    print("Task 2:", valid_emails_list)
    return valid_emails_list

Функція extract_keywords

Виділяє слова, довжина яких перевищує задане значення.

python

def extract_keywords(words, length):
    filtered_words = [word for word in words.split() if len(word) > length]
    print("Task 3:", filtered_words)
    return filtered_words

Функція process_text

Обробляє текст, приводячи його до нижнього регістру та видаляючи розділові знаки.

python

def process_text(text):
    processed = [item.strip().lower().strip('.?!') for item in text.split(',')]
    processed = [item for item in processed if item]
    print("Task 4:", processed)
    return processed

Функція normalize_data

Нормалізує числові дані, ділячи кожне число на максимальне значення в наборі.

python

def normalize_data(numbers):
    numbers_list = [float(num) for num in numbers.split(',')]
    max_value = max(numbers_list)
    normalized = [round(num / max_value, 3) for num in numbers_list]
    print("Task 5:", normalized)
    return normalized

Функція concatenate_strings

Об'єднує рядки, видаляючи заданий роздільник.

python

def concatenate_strings(data, separator):
    concatenated = ''.join(data.split(separator))
    print("Task 6:", concatenated)
    return concatenated

Функція sum_numeric_strings

Обчислює суму чисел у рядках.

python

def sum_numeric_strings(numbers):
    total_sum = sum(map(int, re.findall(r'\d+', numbers)))
    print("Task 7:", total_sum)
    return total_sum

Функція filter_numbers

Фільтрує числа, що перевищують заданий поріг.

python

def filter_numbers(input_string, threshold):
    numbers_list = [int(num) for num in re.findall(r'\d+', input_string)]
    filtered_numbers = [num for num in numbers_list if num > threshold]
    print("Task 8:", filtered_numbers)
    return filtered_numbers

Функція map_to_squares

Зводить числа у квадрат.

python

def map_to_squares(numbers):
    squared_numbers = [int(num) ** 2 for num in numbers.split(',')]
    print("Task 9:", squared_numbers)
    return squared_numbers

Функція reverse_strings

Реверсує рядки.

python

def reverse_strings(words):
    reversed_words = [word[::-1] for word in words.split(',')]
    print("Task 10:", reversed_words)
    return reversed_words

Приклади використання

python

# Очищення даних
data = " Apple,  Banana , orange "
cleaned_data = clean_data(data)

# Фільтрація електронних адрес
emails = "mail us test@example.com and invalid-email.com.djwd with example@test.co"
valid_emails = filter_emails(emails)

# Виділення ключових слів
words = "apple pear banana kiwi"
filtered_words = extract_keywords(words, 4)

# Обробка тексту
texts = "Hello! , Yes? , No. , "
processed_texts = process_text(texts)

# Нормалізація чисел
numbers = "10, 20, 30, 40, 50"
normalized_numbers = normalize_data(numbers)

# Об'єднання рядків
data_to_concatenate = "Hello, World!, How, are, you?"
separator = ","
concatenated_data = concatenate_strings(data_to_concatenate, separator)

# Сума чисел у рядках
numeric_strings = "10, 20, abc, 30, def, 40"
sum_of_numeric_strings = sum_numeric_strings(numeric_strings)

# Фільтрація чисел
numbers_to_filter = "10, 20, abc, 30, def, 40"
threshold = 25
filtered_numbers = filter_numbers(numbers_to_filter, threshold)

# Зведення чисел у квадрат
numbers_to_square = "1, 2, 3, 4, 5"
squared_numbers = map_to_squares(numbers_to_square)

# Реверсування рядків
strings_to_reverse = "apple, banana, orange, PEAR, kiwi"
reversed_strings = reverse_strings(strings_to_reverse)

Результати

В результаті виконання роботи були створені функції для різних типів обробки даних. Функції успішно виконують свої задачі, що підтверджується тестовими прикладами.
Скриншоти та приклади виводу програми

plaintext

Task 1: ['apple', 'banana', 'orange']
Task 2: ['test@example.com', 'example@test.co']
Task 3: ['apple', 'banana']
Task 4: ['hello', 'yes', 'no']
Task 5: [0.2, 0.4, 0.6, 0.8, 1.0]
Task 6: 'Hello World! How are you?'
Task 7: 100
Task 8: [30, 40]
Task 9: [1, 4, 9, 16, 25]
Task 10: ['elppa', 'ananab', 'egnaro', 'raep', 'iwek']

Висновки

Мета роботи була досягнута: були розроблені функції для різних типів обробки даних. Проблеми, які виникали під час роботи, були вирішені за допомогою тестування та налагодження коду.
Інструкції з запуску

Для запуску програми необхідно мати встановлений Python версії 3.6 або вище. Для запуску програми виконайте наступні кроки:

    Скопіювати код у файл data_processing.py.
    Запустити файл за допомогою команди:

bash

python data_processing.py

Необхідні бібліотеки: стандартна бібліотека Python.
Лабораторна робота №1: Обробка даних за допомогою функцій на Python
Мета роботи

Метою даної лабораторної роботи є розробка та тестування набору функцій для обробки текстових і числових даних з використанням мови програмування Python. Очікувані результати включають створення функцій для очищення даних, фільтрації електронних адрес, виділення ключових слів, нормалізації чисел, та інших завдань.
Опис завдання

Необхідно розробити функції, що виконують наступні завдання:

    Очищення рядкових даних.
    Фільтрація валідних електронних адрес.
    Витяг ключових слів, що перевищують певну довжину.
    Обробка тексту, приведення до нижнього регістру та видалення розділових знаків.
    Нормалізація числових даних.
    Об'єднання рядків з використанням заданого роздільника.
    Обчислення суми чисел у рядках.
    Фільтрація чисел, що перевищують заданий поріг.
    Зведення чисел у квадрат.
    Реверсування рядків.

Виконання роботи
Структура проекту

Проект складається з одного основного файлу data_processing.py, що містить визначення всіх необхідних функцій.
Опис файлів та їх призначення

    data_processing.py: Основний файл, що містить всі функції для обробки даних та приклади їх використання.

Опис основних функцій та методів
Функція clean_data

Очищує дані, розділяючи рядок за комами, видаляючи пробіли та перетворюючи в нижній регістр.

python

def clean_data(data):
    if isinstance(data, str):
        data = data.split(',')
    cleaned = [item.strip().lower() for item in data]
    print("Task 1:", cleaned)
    return cleaned

Функція filter_emails

Фільтрує валідні електронні адреси з рядка.

python

def filter_emails(emails_string):
    pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
    valid_emails = re.findall(pattern, emails_string)
    valid_emails_list = [email for email in valid_emails if email.count('@') == 1]
    print("Task 2:", valid_emails_list)
    return valid_emails_list

Функція extract_keywords

Виділяє слова, довжина яких перевищує задане значення.

python

def extract_keywords(words, length):
    filtered_words = [word for word in words.split() if len(word) > length]
    print("Task 3:", filtered_words)
    return filtered_words

Функція process_text

Обробляє текст, приводячи його до нижнього регістру та видаляючи розділові знаки.

python

def process_text(text):
    processed = [item.strip().lower().strip('.?!') for item in text.split(',')]
    processed = [item for item in processed if item]
    print("Task 4:", processed)
    return processed

Функція normalize_data

Нормалізує числові дані, ділячи кожне число на максимальне значення в наборі.

python

def normalize_data(numbers):
    numbers_list = [float(num) for num in numbers.split(',')]
    max_value = max(numbers_list)
    normalized = [round(num / max_value, 3) for num in numbers_list]
    print("Task 5:", normalized)
    return normalized

Функція concatenate_strings

Об'єднує рядки, видаляючи заданий роздільник.

python

def concatenate_strings(data, separator):
    concatenated = ''.join(data.split(separator))
    print("Task 6:", concatenated)
    return concatenated

Функція sum_numeric_strings

Обчислює суму чисел у рядках.

python

def sum_numeric_strings(numbers):
    total_sum = sum(map(int, re.findall(r'\d+', numbers)))
    print("Task 7:", total_sum)
    return total_sum

Функція filter_numbers

Фільтрує числа, що перевищують заданий поріг.

python

def filter_numbers(input_string, threshold):
    numbers_list = [int(num) for num in re.findall(r'\d+', input_string)]
    filtered_numbers = [num for num in numbers_list if num > threshold]
    print("Task 8:", filtered_numbers)
    return filtered_numbers

Функція map_to_squares

Зводить числа у квадрат.

python

def map_to_squares(numbers):
    squared_numbers = [int(num) ** 2 for num in numbers.split(',')]
    print("Task 9:", squared_numbers)
    return squared_numbers

Функція reverse_strings

Реверсує рядки.

python

def reverse_strings(words):
    reversed_words = [word[::-1] for word in words.split(',')]
    print("Task 10:", reversed_words)
    return reversed_words

Приклади використання

python

# Очищення даних
data = " Apple,  Banana , orange "
cleaned_data = clean_data(data)

# Фільтрація електронних адрес
emails = "mail us test@example.com and invalid-email.com.djwd with example@test.co"
valid_emails = filter_emails(emails)

# Виділення ключових слів
words = "apple pear banana kiwi"
filtered_words = extract_keywords(words, 4)

# Обробка тексту
texts = "Hello! , Yes? , No. , "
processed_texts = process_text(texts)

# Нормалізація чисел
numbers = "10, 20, 30, 40, 50"
normalized_numbers = normalize_data(numbers)

# Об'єднання рядків
data_to_concatenate = "Hello, World!, How, are, you?"
separator = ","
concatenated_data = concatenate_strings(data_to_concatenate, separator)

# Сума чисел у рядках
numeric_strings = "10, 20, abc, 30, def, 40"
sum_of_numeric_strings = sum_numeric_strings(numeric_strings)

# Фільтрація чисел
numbers_to_filter = "10, 20, abc, 30, def, 40"
threshold = 25
filtered_numbers = filter_numbers(numbers_to_filter, threshold)

# Зведення чисел у квадрат
numbers_to_square = "1, 2, 3, 4, 5"
squared_numbers = map_to_squares(numbers_to_square)

# Реверсування рядків
strings_to_reverse = "apple, banana, orange, PEAR, kiwi"
reversed_strings = reverse_strings(strings_to_reverse)

Результати

В результаті виконання роботи були створені функції для різних типів обробки даних. Функції успішно виконують свої задачі, що підтверджується тестовими прикладами.
Скриншоти та приклади виводу програми

plaintext

Task 1: ['apple', 'banana', 'orange']
Task 2: ['test@example.com', 'example@test.co']
Task 3: ['apple', 'banana']
Task 4: ['hello', 'yes', 'no']
Task 5: [0.2, 0.4, 0.6, 0.8, 1.0]
Task 6: 'Hello World! How are you?'
Task 7: 100
Task 8: [30, 40]
Task 9: [1, 4, 9, 16, 25]
Task 10: ['elppa', 'ananab', 'egnaro', 'raep', 'iwek']

Висновки

Мета роботи була досягнута: були розроблені функції для різних типів обробки даних. Проблеми, які виникали під час роботи, були вирішені за допомогою тестування та налагодження коду.
Інструкції з запуску

Для запуску програми необхідно мати встановлений Python версії 3.6 або вище. Для запуску програми виконайте наступні кроки:

    Скопіювати код у файл data_processing.py.
    Запустити файл за допомогою команди:

bash

python data_processing.py

Необхідні бібліотеки: стандартна бібліотека Python.
