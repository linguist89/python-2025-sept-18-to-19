# Loops in Python

## What are Loops?

Loops allow you to execute a block of code repeatedly. They are essential for automating repetitive tasks and processing collections of data. Python provides two main types of loops: `for` loops and `while` loops.

## The `for` Loop

The `for` loop is used to iterate over a sequence (like a list, string, or range) and execute code for each item.

### Basic `for` Loop Syntax

```python
for item in sequence:
    # Code to execute for each item
    print(item)
```

### Iterating Over Lists

```python
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(f"I like {fruit}")
```

Output:
```
I like apple
I like banana
I like orange
```

### Iterating Over Strings

```python
word = "Python"

for letter in word:
    print(letter)
```

Output:
```
P
y
t
h
o
n
```

### Using `range()` Function

The `range()` function generates a sequence of numbers:

```python
# range(stop) - from 0 to stop-1
for i in range(5):
    print(i)
```

Output:
```
0
1
2
3
4
```

```python
# range(start, stop) - from start to stop-1
for i in range(2, 6):
    print(i)
```

Output:
```
2
3
4
5
```

```python
# range(start, stop, step) - with step size
for i in range(0, 10, 2):
    print(i)
```

Output:
```
0
2
4
6
8
```

## The `while` Loop

The `while` loop repeats code as long as a condition is `True`:

```python
count = 0

while count < 5:
    print(f"Count: {count}")
    count += 1  # Don't forget to update the condition!
```

Output:
```
Count: 0
Count: 1
Count: 2
Count: 3
Count: 4
```

### Important: Avoiding Infinite Loops

Always ensure your `while` loop has a way to terminate:

```python
# Good example
count = 0
while count < 3:
    print(f"Count: {count}")
    count += 1  # This will eventually make count >= 3

# Bad example (infinite loop - don't run this!)
# count = 0
# while count < 3:
#     print(f"Count: {count}")
#     # Missing count += 1 - this will run forever!
```

## Loop Control Statements

### `break` Statement

The `break` statement exits the loop immediately:

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for num in numbers:
    if num == 5:
        break
    print(num)
```

Output:
```
1
2
3
4
```

### `continue` Statement

The `continue` statement skips the rest of the current iteration and moves to the next one:

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for num in numbers:
    if num % 2 == 0:  # Skip even numbers
        continue
    print(num)
```

Output:
```
1
3
5
7
9
```

### `else` Clause with Loops

You can use `else` with loops. The `else` block executes when the loop completes normally (not via `break`):

```python
numbers = [1, 3, 5, 7, 9]

for num in numbers:
    if num % 2 == 0:
        print(f"Found even number: {num}")
        break
else:
    print("No even numbers found")
```

Output:
```
No even numbers found
```

## Nested Loops

You can place loops inside other loops:

```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} × {j} = {i * j}")
    print()  # Empty line after each row
```

Output:
```
1 × 1 = 1
1 × 2 = 2
1 × 3 = 3

2 × 1 = 2
2 × 2 = 4
2 × 3 = 6

3 × 1 = 3
3 × 2 = 6
3 × 3 = 9
```

## Common Loop Patterns

### Accumulating Values

```python
# Sum of numbers
numbers = [1, 2, 3, 4, 5]
total = 0

for num in numbers:
    total += num

print(f"Sum: {total}")  # Output: Sum: 15
```

### Finding Maximum/Minimum

```python
# Find the largest number
numbers = [3, 7, 2, 9, 1, 5]
max_num = numbers[0]  # Start with first number

for num in numbers:
    if num > max_num:
        max_num = num

print(f"Maximum: {max_num}")  # Output: Maximum: 9
```

### Counting Occurrences

```python
# Count vowels in a string
text = "Hello, World!"
vowels = "aeiouAEIOU"
count = 0

for char in text:
    if char in vowels:
        count += 1

print(f"Vowel count: {count}")  # Output: Vowel count: 3
```

### Building Lists

```python
# Create a list of squares
squares = []

for i in range(1, 6):
    squares.append(i ** 2)

print(squares)  # Output: [1, 4, 9, 16, 25]
```

## When to Use `for` vs `while`

### Use `for` loops when:
- You know how many times to iterate
- You're iterating over a collection
- You have a definite sequence

```python
# Good for loop examples
for item in shopping_list:
    print(f"Buy: {item}")

for i in range(10):
    print(f"Step {i}")
```

### Use `while` loops when:
- You don't know how many times to iterate
- You're waiting for a condition to change
- You need to repeat until something happens

```python
# Good while loop examples
user_input = ""
while user_input.lower() != "quit":
    user_input = input("Enter a command (or 'quit' to exit): ")
    print(f"You entered: {user_input}")

# Reading until end of file
while True:
    line = file.readline()
    if not line:
        break
    print(line)
```

## List Comprehensions (Advanced)

List comprehensions provide a concise way to create lists using loops:

```python
# Traditional way
squares = []
for i in range(1, 6):
    squares.append(i ** 2)

# List comprehension way
squares = [i ** 2 for i in range(1, 6)]

# Both produce: [1, 4, 9, 16, 25]
```

## Best Practices

1. **Use meaningful variable names**: `for student in students:` not `for x in y:`
2. **Avoid modifying lists while iterating**: Create a copy if needed
3. **Use `enumerate()` for index and value**: `for i, item in enumerate(items):`
4. **Be careful with infinite loops**: Always have an exit condition in `while` loops
5. **Use `break` and `continue` judiciously**: They can make code harder to read

```python
# Good example with enumerate
fruits = ["apple", "banana", "orange"]

for index, fruit in enumerate(fruits):
    print(f"{index + 1}. {fruit}")
```

Output:
```
1. apple
2. banana
3. orange
```

## Summary

Loops are fundamental for:
- Processing collections of data
- Automating repetitive tasks
- Implementing algorithms
- Creating interactive programs

Key concepts:
- `for` loops for definite iteration
- `while` loops for indefinite iteration
- `break` and `continue` for loop control
- Nested loops for complex patterns
- Always ensure loops can terminate
