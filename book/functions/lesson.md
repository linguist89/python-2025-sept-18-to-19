# Functions in Python

## What are Functions?

Functions are reusable blocks of code that perform a specific task. They help you organize your code, avoid repetition, and make your programs more modular and easier to maintain. Think of a function as a recipe that you can follow multiple times with different ingredients.

## Why Use Functions?

Functions provide several benefits:
- **Reusability**: Write once, use many times
- **Modularity**: Break complex problems into smaller, manageable pieces
- **Readability**: Make your code easier to understand
- **Maintainability**: Easier to update and debug
- **Testing**: Test individual pieces of functionality

## Basic Function Syntax

In Python, you define a function using the `def` keyword:

```python
def function_name():
    """Optional docstring describing what the function does"""
    # Function body - the code that runs when function is called
    pass  # placeholder for actual code
```

## Creating Your First Function

Let's start with a simple function that prints a greeting:

```python
def say_hello():
    """Prints a greeting message"""
    print("Hello, World!")

# To use (call) the function:
say_hello()  # Output: Hello, World!
```

## Functions with Parameters

Parameters allow you to pass data into a function. They make functions more flexible and useful:

```python
def greet_person(name):
    """Greets a person by name"""
    print(f"Hello, {name}!")

# Using the function with different names
greet_person("Alice")  # Output: Hello, Alice!
greet_person("Bob")    # Output: Hello, Bob!
```

## Multiple Parameters

Functions can accept multiple parameters:

```python
def introduce_person(name, age, city):
    """Introduces a person with their details"""
    print(f"Hi! I'm {name}, I'm {age} years old, and I live in {city}.")

# Using the function
introduce_person("Sarah", 25, "New York")
# Output: Hi! I'm Sarah, I'm 25 years old, and I live in New York.
```

## Default Parameters

You can provide default values for parameters:

```python
def greet_with_title(name, title="Mr."):
    """Greets a person with an optional title"""
    print(f"Hello, {title} {name}!")

# Using with default title
greet_with_title("Smith")  # Output: Hello, Mr. Smith!

# Using with custom title
greet_with_title("Johnson", "Dr.")  # Output: Hello, Dr. Johnson!
```

## Return Values

Functions can return values using the `return` statement:

```python
def add_numbers(a, b):
    """Adds two numbers and returns the result"""
    result = a + b
    return result

# Using the function
sum_result = add_numbers(5, 3)
print(sum_result)  # Output: 8

# You can also use the return value directly
print(add_numbers(10, 20))  # Output: 30
```

## Multiple Return Values

Python functions can return multiple values:

```python
def calculate_rectangle(length, width):
    """Calculates area and perimeter of a rectangle"""
    area = length * width
    perimeter = 2 * (length + width)
    return area, perimeter

# Using the function
area, perimeter = calculate_rectangle(5, 3)
print(f"Area: {area}, Perimeter: {perimeter}")
# Output: Area: 15, Perimeter: 16
```

## Function Documentation (Docstrings)

Docstrings describe what a function does. They're written in triple quotes:

```python
def calculate_circle_area(radius):
    """
    Calculate the area of a circle.
    
    Parameters:
    radius (float): The radius of the circle
    
    Returns:
    float: The area of the circle
    """
    import math
    return math.pi * radius ** 2

# You can access the docstring
print(calculate_circle_area.__doc__)
```

## Local vs Global Variables

Variables defined inside a function are local to that function:

```python
global_var = "I'm global"

def my_function():
    local_var = "I'm local"
    print(global_var)  # Can access global variable
    print(local_var)   # Can access local variable

my_function()
# print(local_var)  # This would cause an error - local_var doesn't exist here
```

## Modifying Global Variables

To modify a global variable inside a function, use the `global` keyword:

```python
counter = 0

def increment_counter():
    global counter
    counter += 1
    print(f"Counter is now: {counter}")

increment_counter()  # Output: Counter is now: 1
increment_counter()  # Output: Counter is now: 2
```

## Lambda Functions (Anonymous Functions)

Lambda functions are small, anonymous functions defined with the `lambda` keyword:

```python
# Regular function
def square(x):
    return x ** 2

# Lambda function (equivalent)
square_lambda = lambda x: x ** 2

# Both work the same way
print(square(5))        # Output: 25
print(square_lambda(5)) # Output: 25

# Lambda functions are often used with built-in functions
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)  # Output: [1, 4, 9, 16, 25]
```

## Function Arguments: *args and **kwargs

### *args (Arbitrary Arguments)

Allows a function to accept any number of positional arguments:

```python
def sum_all(*args):
    """Sums all provided numbers"""
    total = 0
    for number in args:
        total += number
    return total

print(sum_all(1, 2, 3))        # Output: 6
print(sum_all(1, 2, 3, 4, 5))  # Output: 15
```

### **kwargs (Keyword Arguments)

Allows a function to accept any number of keyword arguments:

```python
def print_info(**kwargs):
    """Prints information from keyword arguments"""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25, city="Boston")
# Output:
# name: Alice
# age: 25
# city: Boston
```

## Practical Examples

### Example 1: Temperature Converter

```python
def celsius_to_fahrenheit(celsius):
    """Convert Celsius to Fahrenheit"""
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

def fahrenheit_to_celsius(fahrenheit):
    """Convert Fahrenheit to Celsius"""
    celsius = (fahrenheit - 32) * 5/9
    return celsius

# Using the functions
temp_c = 25
temp_f = celsius_to_fahrenheit(temp_c)
print(f"{temp_c}°C is {temp_f}°F")  # Output: 25°C is 77.0°F
```

### Example 2: List Operations

```python
def find_max(numbers):
    """Find the maximum number in a list"""
    if not numbers:
        return None
    max_num = numbers[0]
    for num in numbers:
        if num > max_num:
            max_num = num
    return max_num

def calculate_average(numbers):
    """Calculate the average of numbers in a list"""
    if not numbers:
        return 0
    return sum(numbers) / len(numbers)

# Using the functions
scores = [85, 92, 78, 96, 88]
print(f"Highest score: {find_max(scores)}")      # Output: Highest score: 96
print(f"Average score: {calculate_average(scores)}")  # Output: Average score: 87.8
```

### Example 3: String Processing

```python
def count_words(text):
    """Count the number of words in a text"""
    words = text.split()
    return len(words)

def reverse_string(text):
    """Reverse a string"""
    return text[::-1]

def is_palindrome(text):
    """Check if a string is a palindrome"""
    text = text.lower().replace(" ", "")
    return text == text[::-1]

# Using the functions
sentence = "Python programming is fun"
print(f"Word count: {count_words(sentence)}")  # Output: Word count: 4
print(f"Reversed: {reverse_string(sentence)}")  # Output: Reversed: nuf si gnimmargorp nohtyP
print(f"Is palindrome: {is_palindrome('racecar')}")  # Output: Is palindrome: True
```

## Best Practices

1. **Use descriptive names**: Function names should clearly indicate what they do
2. **Keep functions small**: Each function should do one thing well
3. **Use docstrings**: Document what your function does
4. **Avoid global variables**: Use parameters and return values instead
5. **Handle edge cases**: Consider what happens with invalid inputs

```python
# Good function design
def calculate_discount(price, discount_percent):
    """
    Calculate the discounted price.
    
    Parameters:
    price (float): Original price
    discount_percent (float): Discount percentage (0-100)
    
    Returns:
    float: Discounted price
    """
    if price < 0:
        raise ValueError("Price cannot be negative")
    if discount_percent < 0 or discount_percent > 100:
        raise ValueError("Discount must be between 0 and 100")
    
    discount_amount = price * (discount_percent / 100)
    return price - discount_amount
```

## Summary

Functions are essential building blocks in Python programming. They help you:
- Organize code into reusable components
- Make programs more readable and maintainable
- Break complex problems into smaller, manageable pieces
- Avoid code duplication

Key concepts to remember:
- Use `def` to define functions
- Parameters make functions flexible
- Use `return` to send values back
- Document your functions with docstrings
- Keep functions focused on a single task
