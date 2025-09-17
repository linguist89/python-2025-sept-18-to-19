# Variables in Python

## What are Variables?

Variables are containers that store data values. In Python, you can think of a variable as a labeled box where you can put different types of information. Unlike some other programming languages, Python doesn't require you to declare variables with a specific type - Python automatically determines the type based on the value you assign.

## Creating Variables

In Python, you create a variable by simply assigning a value to it using the equals sign (`=`):

```python
# Creating variables
name = "Alice"
age = 25
height = 5.6
is_student = True
```

## Variable Naming Rules

When naming variables in Python, you must follow these rules:

1. **Start with a letter or underscore**: Variable names cannot start with a number
2. **Use only letters, numbers, and underscores**: No spaces or special characters
3. **Case sensitive**: `name` and `Name` are different variables
4. **Cannot use reserved words**: Don't use Python keywords like `if`, `for`, `while`, etc.

```python
# Valid variable names
my_variable = 10
_variable = 20
variable123 = 30
VariableName = 40

# Invalid variable names (these will cause errors)
# 123variable = 10  # Cannot start with number
# my-variable = 10  # Cannot use hyphens
# my variable = 10  # Cannot use spaces
```

## Data Types

Python automatically assigns data types to variables based on their values:

```python
# String (text)
name = "Python Programming"
message = 'Hello, World!'

# Integer (whole numbers)
count = 42
negative_number = -10

# Float (decimal numbers)
price = 19.99
pi = 3.14159

# Boolean (True or False)
is_active = True
is_complete = False

# List (collection of items)
fruits = ["apple", "banana", "orange"]
numbers = [1, 2, 3, 4, 5]
```

## Variable Assignment and Reassignment

You can change the value of a variable by assigning a new value to it:

```python
# Initial assignment
x = 10
print(x)  # Output: 10

# Reassignment
x = 20
print(x)  # Output: 20

# You can even change the data type
x = "Now I'm a string!"
print(x)  # Output: Now I'm a string!
```

## Multiple Assignment

Python allows you to assign values to multiple variables in a single line:

```python
# Assign the same value to multiple variables
a = b = c = 10

# Assign different values to multiple variables
name, age, city = "Bob", 30, "New York"

# This is equivalent to:
# name = "Bob"
# age = 30
# city = "New York"
```

## Using Variables in Operations

Variables can be used in mathematical operations and string concatenation:

```python
# Mathematical operations
a = 10
b = 5
sum_result = a + b  # 15
difference = a - b  # 5
product = a * b     # 50
quotient = a / b    # 2.0

# String operations
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name  # "John Doe"

# Using variables in expressions
radius = 5
area = 3.14159 * radius * radius  # Calculate circle area
```

## Variable Scope

Variables have different scopes depending on where they are defined:

```python
# Global variable (accessible throughout the program)
global_var = "I'm global"

def my_function():
    # Local variable (only accessible within this function)
    local_var = "I'm local"
    print(global_var)  # Can access global variable
    print(local_var)   # Can access local variable

# print(local_var)  # This would cause an error - local_var is not accessible here
```

## Best Practices

1. **Use descriptive names**: Choose names that clearly indicate what the variable represents
2. **Use snake_case**: In Python, it's conventional to use lowercase letters with underscores
3. **Avoid single letters**: Except for simple counters like `i`, `j`, `k` in loops
4. **Initialize variables**: Always give variables an initial value before using them

```python
# Good variable names
user_name = "Alice"
total_score = 100
is_logged_in = True

# Avoid these
n = "Alice"  # What does 'n' mean?
ts = 100     # What does 'ts' mean?
flag = True  # What kind of flag?
```

## Summary

Variables are fundamental to programming in Python. They allow you to:
- Store and organize data
- Make your code more readable and maintainable
- Perform calculations and operations
- Build dynamic programs that can work with different data

Remember: Python variables are dynamically typed, meaning you don't need to declare their type, and you can change their type by assigning different values to them.
