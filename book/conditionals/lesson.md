# Conditionals in Python

## What are Conditionals?

Conditionals allow your program to make decisions and execute different code based on whether certain conditions are true or false. They are fundamental to creating dynamic programs that can respond to different situations.

## The `if` Statement

The most basic conditional statement is `if`. It executes code only when a condition is `True`:

```python
age = 18

if age >= 18:
    print("You are an adult")
```

**Important**: Notice the colon (`:`) after the condition and the indentation (4 spaces) for the code block.

## Comparison Operators

Before diving deeper into conditionals, let's review the comparison operators:

```python
# Equal to
5 == 5  # True
5 == 3  # False

# Not equal to
5 != 3  # True
5 != 5  # False

# Greater than
10 > 5  # True
5 > 10  # False

# Less than
3 < 7   # True
7 < 3   # False

# Greater than or equal to
5 >= 5  # True
5 >= 3  # True
5 >= 7  # False

# Less than or equal to
5 <= 5  # True
5 <= 7  # True
5 <= 3  # False
```

## The `else` Statement

The `else` statement provides an alternative path when the `if` condition is `False`:

```python
age = 16

if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")
```

## The `elif` Statement

`elif` (short for "else if") allows you to check multiple conditions:

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```

## Logical Operators

You can combine conditions using logical operators:

### `and` Operator
Both conditions must be `True`:

```python
age = 25
has_license = True

if age >= 18 and has_license:
    print("You can drive")
else:
    print("You cannot drive")
```

### `or` Operator
At least one condition must be `True`:

```python
weather = "rainy"
temperature = 15

if weather == "sunny" or temperature > 20:
    print("Good weather for outdoor activities")
else:
    print("Stay indoors")
```

### `not` Operator
Reverses the boolean value:

```python
is_weekend = False

if not is_weekend:
    print("It's a weekday")
else:
    print("It's the weekend")
```

## Nested Conditionals

You can place conditionals inside other conditionals:

```python
age = 20
has_license = True

if age >= 18:
    if has_license:
        print("You can drive")
    else:
        print("You need a license to drive")
else:
    print("You must be 18 or older to drive")
```

## Multiple Conditions with `elif`

You can chain multiple `elif` statements:

```python
day = "Wednesday"

if day == "Monday":
    print("Start of the work week")
elif day == "Tuesday":
    print("Second day of work")
elif day == "Wednesday":
    print("Midweek")
elif day == "Thursday":
    print("Almost Friday")
elif day == "Friday":
    print("TGIF!")
elif day == "Saturday" or day == "Sunday":
    print("Weekend!")
else:
    print("Invalid day")
```

## Truthiness in Python

In Python, certain values are considered "falsy" (evaluate to `False` in boolean context):

```python
# Falsy values
False
None
0
0.0
""  # Empty string
[]  # Empty list
{}  # Empty dictionary

# Truthy values (everything else)
True
1
"hello"
[1, 2, 3]
{"key": "value"}
```

You can use this in conditionals:

```python
name = ""

if name:  # This is False because empty string is falsy
    print(f"Hello, {name}")
else:
    print("No name provided")
```

## Conditional Expressions (Ternary Operator)

Python has a concise way to write simple conditionals:

```python
# Traditional way
age = 20
if age >= 18:
    status = "adult"
else:
    status = "minor"

# Using conditional expression
status = "adult" if age >= 18 else "minor"
```

## Common Patterns

### Checking if a value is in a list:

```python
fruits = ["apple", "banana", "orange"]
fruit = "banana"

if fruit in fruits:
    print(f"{fruit} is available")
else:
    print(f"{fruit} is not available")
```

### Checking if a string contains a substring:

```python
email = "user@example.com"

if "@" in email:
    print("Valid email format")
else:
    print("Invalid email format")
```

### Range checking:

```python
score = 75

if 0 <= score <= 100:
    print("Valid score")
else:
    print("Score must be between 0 and 100")
```

## Best Practices

1. **Use meaningful variable names**: `is_authenticated` instead of `flag`
2. **Keep conditions simple**: Break complex conditions into multiple variables
3. **Use parentheses for clarity**: `(age >= 18) and (has_license)`
4. **Avoid deep nesting**: Use `elif` instead of nested `if` statements when possible
5. **Be consistent with indentation**: Use 4 spaces (Python standard)

```python
# Good example
user_age = 25
has_valid_license = True
is_weekend = False

if (user_age >= 18) and has_valid_license:
    if is_weekend:
        print("You can drive for leisure")
    else:
        print("You can drive to work")
else:
    print("You cannot drive")
```

## Summary

Conditionals are essential for creating programs that can:
- Make decisions based on user input
- Handle different scenarios
- Validate data
- Control program flow

Key concepts to remember:
- Use `if`, `elif`, and `else` for decision making
- Understand comparison and logical operators
- Know about truthiness in Python
- Keep your conditions readable and maintainable
