# Functions - Practice Questions

## Question 1: Basic Function Creation
Create a function called `greet_user` that takes a name as a parameter and prints "Hello, [name]! Welcome to Python programming!"

```python
def greet_user(name):
    """Greets a user with their name"""
    print(f"Hello, {name}! Welcome to Python programming!")

# Test the function
greet_user("Alice")
greet_user("Bob")
```

## Question 2: Function with Return Value
Create a function called `multiply` that takes two numbers as parameters and returns their product. Test it with the numbers 7 and 8.

```python
def multiply(a, b):
    """Multiplies two numbers and returns the result"""
    return a * b

# Test the function
result = multiply(7, 8)
print(f"7 * 8 = {result}")
```

## Question 3: Multiple Parameters
Create a function called `calculate_rectangle` that takes length and width as parameters and returns both the area and perimeter of a rectangle. Use it to calculate the area and perimeter of a rectangle with length 10 and width 5.

```python
def calculate_rectangle(length, width):
    """Calculates area and perimeter of a rectangle"""
    area = length * width
    perimeter = 2 * (length + width)
    return area, perimeter

# Test the function
area, perimeter = calculate_rectangle(10, 5)
print(f"Rectangle with length 10 and width 5:")
print(f"Area: {area}")
print(f"Perimeter: {perimeter}")
```

## Question 4: Default Parameters
Create a function called `create_email` that takes a username and domain (with default value "gmail.com") and returns a formatted email address. Test it with:
- Username "john.doe" (using default domain)
- Username "jane.smith" with domain "company.com"

```python
def create_email(username, domain="gmail.com"):
    """Creates an email address from username and domain"""
    return f"{username}@{domain}"

# Test the function
email1 = create_email("john.doe")
email2 = create_email("jane.smith", "company.com")
print(f"Default domain: {email1}")
print(f"Custom domain: {email2}")
```

## Question 5: Temperature Converter
Create a function called `celsius_to_fahrenheit` that converts Celsius to Fahrenheit using the formula: F = (C × 9/5) + 32. Test it with 25°C.

```python
def celsius_to_fahrenheit(celsius):
    """Converts Celsius to Fahrenheit"""
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

# Test the function
celsius_temp = 25
fahrenheit_temp = celsius_to_fahrenheit(celsius_temp)
print(f"{celsius_temp}°C = {fahrenheit_temp}°F")
```

## Question 6: List Processing Function
Create a function called `find_largest` that takes a list of numbers and returns the largest number. Test it with the list [45, 23, 78, 12, 91, 34].

```python
def find_largest(numbers):
    """Finds the largest number in a list"""
    if not numbers:
        return None
    
    largest = numbers[0]
    for num in numbers:
        if num > largest:
            largest = num
    return largest

# Test the function
numbers_list = [45, 23, 78, 12, 91, 34]
largest_num = find_largest(numbers_list)
print(f"The largest number in {numbers_list} is {largest_num}")
```

## Question 7: String Processing
Create a function called `count_vowels` that takes a string and returns the number of vowels (a, e, i, o, u) in the string. Test it with "Hello, World!".

```python
def count_vowels(text):
    """Counts the number of vowels in a string"""
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

# Test the function
test_string = "Hello, World!"
vowel_count = count_vowels(test_string)
print(f"The string '{test_string}' has {vowel_count} vowels")
```

## Question 8: Function with *args
Create a function called `sum_all` that uses *args to accept any number of arguments and returns their sum. Test it with different numbers of arguments.

```python
def sum_all(*args):
    """Sums all provided arguments"""
    total = 0
    for num in args:
        total += num
    return total

# Test the function
result1 = sum_all(1, 2, 3, 4, 5)
result2 = sum_all(10, 20, 30)
result3 = sum_all(5)
print(f"Sum of 1,2,3,4,5: {result1}")
print(f"Sum of 10,20,30: {result2}")
print(f"Sum of 5: {result3}")
```

## Question 9: Function with **kwargs
Create a function called `print_student_info` that uses **kwargs to print student information. The function should print each key-value pair in a formatted way. Test it with name, age, grade, and subject information.

```python
def print_student_info(**kwargs):
    """Prints student information from keyword arguments"""
    print("Student Information:")
    for key, value in kwargs.items():
        print(f"{key.title()}: {value}")

# Test the function
print_student_info(name="Alice", age=20, grade="A", subject="Python")
print_student_info(name="Bob", age=22, grade="B+", subject="Data Science")
```

## Question 10: Lambda Function
Create a lambda function that squares a number. Then use it with the `map` function to square all numbers in the list [1, 2, 3, 4, 5].

```python
# Create a lambda function that squares a number
square = lambda x: x ** 2

# Use map function to square all numbers in the list
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(square, numbers))
print(f"Original numbers: {numbers}")
print(f"Squared numbers: {squared_numbers}")
```

## Question 11: Palindrome Checker
Create a function called `is_palindrome` that checks if a word is a palindrome (reads the same forwards and backwards). The function should ignore case and spaces. Test it with "racecar" and "A man a plan a canal Panama".

```python
def is_palindrome(word):
    """Checks if a word is a palindrome"""
    # Remove spaces and convert to lowercase
    cleaned = word.replace(" ", "").lower()
    # Check if the cleaned string equals its reverse
    return cleaned == cleaned[::-1]

# Test the function
print(f"Is 'racecar' a palindrome? {is_palindrome('racecar')}")
print(f"Is 'A man a plan a canal Panama' a palindrome? {is_palindrome('A man a plan a canal Panama')}")
print(f"Is 'hello' a palindrome? {is_palindrome('hello')}")
```

## Question 12: Grade Calculator
Create a function called `calculate_grade` that takes a percentage score and returns the corresponding letter grade:
- 90-100: A
- 80-89: B
- 70-79: C
- 60-69: D
- Below 60: F

Test it with scores 95, 85, 75, 65, and 55.

```python
def calculate_grade(percentage):
    """Calculates letter grade based on percentage"""
    if percentage >= 90:
        return "A"
    elif percentage >= 80:
        return "B"
    elif percentage >= 70:
        return "C"
    elif percentage >= 60:
        return "D"
    else:
        return "F"

# Test the function
test_scores = [95, 85, 75, 65, 55]
for score in test_scores:
    grade = calculate_grade(score)
    print(f"Score {score}% = Grade {grade}")
```

## Question 13: Password Validator
Create a function called `validate_password` that checks if a password meets these criteria:
- At least 8 characters long
- Contains at least one uppercase letter
- Contains at least one lowercase letter
- Contains at least one digit

The function should return True if valid, False otherwise. Test it with different passwords.

```python
def validate_password(password):
    """Validates password based on criteria"""
    if len(password) < 8:
        return False
    
    has_upper = any(c.isupper() for c in password)
    has_lower = any(c.islower() for c in password)
    has_digit = any(c.isdigit() for c in password)
    
    return has_upper and has_lower and has_digit

# Test the function
test_passwords = ["Password123", "weak", "NoNumbers", "nouppercase123", "12345678"]
for pwd in test_passwords:
    is_valid = validate_password(pwd)
    print(f"Password '{pwd}': {'Valid' if is_valid else 'Invalid'}")
```

## Question 14: Fibonacci Function
Create a function called `fibonacci` that takes a number n and returns the nth number in the Fibonacci sequence. The Fibonacci sequence starts with 0, 1, and each subsequent number is the sum of the two preceding numbers.

```python
def fibonacci(n):
    """Returns the nth number in the Fibonacci sequence"""
    if n <= 0:
        return 0
    elif n == 1:
        return 1
    else:
        a, b = 0, 1
        for _ in range(2, n + 1):
            a, b = b, a + b
        return b

# Test the function
for i in range(10):
    print(f"Fibonacci({i}) = {fibonacci(i)}")
```

## Question 15: Word Counter
Create a function called `word_frequency` that takes a text string and returns a dictionary with each word as a key and its frequency as the value. Ignore punctuation and case. Test it with "The quick brown fox jumps over the lazy dog. The dog is lazy."

```python
def word_frequency(text):
    """Counts word frequency in text"""
    import string
    
    # Remove punctuation and convert to lowercase
    translator = str.maketrans('', '', string.punctuation)
    cleaned_text = text.translate(translator).lower()
    
    # Split into words
    words = cleaned_text.split()
    
    # Count frequency
    frequency = {}
    for word in words:
        frequency[word] = frequency.get(word, 0) + 1
    
    return frequency

# Test the function
test_text = "The quick brown fox jumps over the lazy dog. The dog is lazy."
freq = word_frequency(test_text)
print("Word frequency:")
for word, count in freq.items():
    print(f"'{word}': {count}")
```

## Question 16: Number Guessing Game Function
Create a function called `guess_number` that:
- Generates a random number between 1 and 100
- Takes a user's guess as a parameter
- Returns "Too high", "Too low", or "Correct!" based on the guess
- If correct, also return the number of attempts

```python
import random

def guess_number(user_guess):
    """Simulates a number guessing game"""
    # Generate random number between 1 and 100
    secret_number = random.randint(1, 100)
    attempts = 1
    
    while user_guess != secret_number:
        if user_guess > secret_number:
            return "Too high", attempts
        else:
            return "Too low", attempts
        attempts += 1
    
    return "Correct!", attempts

# Test the function
result, attempts = guess_number(50)
print(f"Result: {result}, Attempts: {attempts}")
```

## Question 17: File Extension Checker
Create a function called `get_file_extension` that takes a filename and returns the file extension (the part after the last dot). If there's no extension, return "No extension". Test it with "document.pdf", "image.jpg", and "readme".

```python
def get_file_extension(filename):
    """Gets the file extension from a filename"""
    if '.' in filename:
        return filename.split('.')[-1]
    else:
        return "No extension"

# Test the function
test_files = ["document.pdf", "image.jpg", "readme"]
for filename in test_files:
    extension = get_file_extension(filename)
    print(f"File: {filename} -> Extension: {extension}")
```

## Question 18: Prime Number Checker
Create a function called `is_prime` that checks if a number is prime (only divisible by 1 and itself). Test it with numbers 2, 17, 25, and 29.

```python
def is_prime(number):
    """Checks if a number is prime"""
    if number < 2:
        return False
    
    for i in range(2, int(number ** 0.5) + 1):
        if number % i == 0:
            return False
    
    return True

# Test the function
test_numbers = [2, 17, 25, 29]
for num in test_numbers:
    prime_status = is_prime(num)
    print(f"{num} is {'prime' if prime_status else 'not prime'}")
```

## Question 19: List Manipulation
Create a function called `remove_duplicates` that takes a list and returns a new list with duplicates removed while preserving the original order. Test it with [1, 2, 2, 3, 4, 4, 5].

```python
def remove_duplicates(lst):
    """Removes duplicates while preserving order"""
    seen = set()
    result = []
    
    for item in lst:
        if item not in seen:
            seen.add(item)
            result.append(item)
    
    return result

# Test the function
original_list = [1, 2, 2, 3, 4, 4, 5]
unique_list = remove_duplicates(original_list)
print(f"Original: {original_list}")
print(f"Unique: {unique_list}")
```

## Question 20: Calculator Function
Create a function called `calculator` that takes two numbers and an operation (+, -, *, /) and returns the result. Handle division by zero. Test it with various operations.

```python
def calculator(a, b, operation):
    """Basic calculator function"""
    if operation == '+':
        return a + b
    elif operation == '-':
        return a - b
    elif operation == '*':
        return a * b
    elif operation == '/':
        if b == 0:
            return "Error: Division by zero"
        return a / b
    else:
        return "Error: Invalid operation"

# Test the function
print(f"5 + 3 = {calculator(5, 3, '+')}")
print(f"10 - 4 = {calculator(10, 4, '-')}")
print(f"6 * 7 = {calculator(6, 7, '*')}")
print(f"15 / 3 = {calculator(15, 3, '/')}")
print(f"10 / 0 = {calculator(10, 0, '/')}")
```

## Bonus Challenge: Text Analyzer
Create a comprehensive function called `analyze_text` that takes a text string and returns a dictionary with:
- Total number of characters
- Total number of words
- Total number of sentences
- Most common word
- Average word length

Test it with a paragraph of your choice.

```python
def analyze_text(text):
    """Comprehensive text analysis"""
    import string
    
    # Basic counts
    char_count = len(text)
    word_count = len(text.split())
    sentence_count = text.count('.') + text.count('!') + text.count('?')
    
    # Most common word
    translator = str.maketrans('', '', string.punctuation)
    cleaned_text = text.translate(translator).lower()
    words = cleaned_text.split()
    
    if words:
        word_freq = {}
        for word in words:
            word_freq[word] = word_freq.get(word, 0) + 1
        most_common_word = max(word_freq, key=word_freq.get)
        avg_word_length = sum(len(word) for word in words) / len(words)
    else:
        most_common_word = "N/A"
        avg_word_length = 0
    
    return {
        'characters': char_count,
        'words': word_count,
        'sentences': sentence_count,
        'most_common_word': most_common_word,
        'average_word_length': round(avg_word_length, 2)
    }

# Test the function
test_text = "Python is great! Python is powerful. Python programming is fun."
analysis = analyze_text(test_text)
print("Text Analysis:")
for key, value in analysis.items():
    print(f"{key.title()}: {value}")
```

## Advanced Challenge: Function Decorator
Create a simple decorator called `timing_decorator` that measures how long a function takes to execute. Apply it to a function that calculates the sum of numbers from 1 to 1000.

```python
import time

def timing_decorator(func):
    """Decorator that measures function execution time"""
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"Function {func.__name__} took {end_time - start_time:.4f} seconds")
        return result
    return wrapper

@timing_decorator
def sum_numbers(n):
    """Sums numbers from 1 to n"""
    total = 0
    for i in range(1, n + 1):
        total += i
    return total

# Test the decorator
result = sum_numbers(1000)
print(f"Sum of numbers 1-1000: {result}")
```