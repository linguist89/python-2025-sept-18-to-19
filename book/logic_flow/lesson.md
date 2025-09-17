# Logic Flow in Python

## What is Logic Flow?

Logic flow refers to how your program makes decisions and controls the execution path through your code. It combines conditionals and loops to create complex, intelligent programs that can handle various scenarios and make decisions based on data.

## Combining Conditionals and Loops

The real power of programming comes from combining conditionals and loops to create sophisticated logic flows.

### Conditional Loops

You can use conditionals inside loops to make decisions during iteration:

```python
# Print only even numbers from 1 to 10
for i in range(1, 11):
    if i % 2 == 0:
        print(f"{i} is even")
    else:
        print(f"{i} is odd")
```

### Loop Control with Conditionals

Use conditionals to control loop behavior:

```python
# Find the first number divisible by 7
numbers = [15, 23, 7, 42, 8, 14, 3]

for num in numbers:
    if num % 7 == 0:
        print(f"Found first number divisible by 7: {num}")
        break
    else:
        print(f"{num} is not divisible by 7")
```

## Common Logic Flow Patterns

### Input Validation Loop

```python
# Keep asking for input until valid
while True:
    age = input("Enter your age (1-120): ")
    
    if age.isdigit():
        age = int(age)
        if 1 <= age <= 120:
            print(f"Valid age: {age}")
            break
        else:
            print("Age must be between 1 and 120")
    else:
        print("Please enter a valid number")
```

### Menu-Driven Programs

```python
# Simple calculator menu
while True:
    print("\nCalculator Menu:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Exit")
    
    choice = input("Enter your choice (1-5): ")
    
    if choice == "5":
        print("Goodbye!")
        break
    elif choice in ["1", "2", "3", "4"]:
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        
        if choice == "1":
            result = num1 + num2
        elif choice == "2":
            result = num1 - num2
        elif choice == "3":
            result = num1 * num2
        elif choice == "4":
            if num2 != 0:
                result = num1 / num2
            else:
                print("Error: Division by zero!")
                continue
        
        print(f"Result: {result}")
    else:
        print("Invalid choice. Please try again.")
```

### Data Processing with Conditions

```python
# Process student grades
students = [
    {"name": "Alice", "grades": [85, 92, 78, 96]},
    {"name": "Bob", "grades": [67, 73, 81, 69]},
    {"name": "Charlie", "grades": [95, 98, 92, 94]}
]

for student in students:
    name = student["name"]
    grades = student["grades"]
    
    # Calculate average
    average = sum(grades) / len(grades)
    
    # Determine letter grade
    if average >= 90:
        letter_grade = "A"
    elif average >= 80:
        letter_grade = "B"
    elif average >= 70:
        letter_grade = "C"
    elif average >= 60:
        letter_grade = "D"
    else:
        letter_grade = "F"
    
    # Check for honors
    if average >= 95:
        honors = " (High Honors!)"
    elif average >= 90:
        honors = " (Honors)"
    else:
        honors = ""
    
    print(f"{name}: {average:.1f} ({letter_grade}){honors}")
```

## Nested Logic Structures

### Complex Decision Trees

```python
# Weather-based activity recommendation
temperature = 25
weather = "sunny"
wind_speed = 5
is_weekend = True

if is_weekend:
    if weather == "sunny":
        if temperature > 20:
            if wind_speed < 10:
                print("Perfect day for a picnic!")
            else:
                print("Good day for outdoor activities, but it's windy")
        else:
            print("Nice day for a walk")
    elif weather == "rainy":
        if temperature > 15:
            print("Good day for indoor activities or a cozy café")
        else:
            print("Perfect day to stay home and read")
    else:
        print("Decent day for outdoor activities")
else:
    print("Weekday - focus on work and responsibilities")
```

### Loop with Multiple Conditions

```python
# Process a list with multiple criteria
products = [
    {"name": "Laptop", "price": 999, "category": "electronics", "in_stock": True},
    {"name": "Book", "price": 15, "category": "education", "in_stock": True},
    {"name": "Phone", "price": 699, "category": "electronics", "in_stock": False},
    {"name": "Pen", "price": 2, "category": "office", "in_stock": True}
]

budget = 100
preferred_category = "electronics"

print("Recommended products within budget:")
for product in products:
    name = product["name"]
    price = product["price"]
    category = product["category"]
    in_stock = product["in_stock"]
    
    # Multiple conditions
    if in_stock and price <= budget:
        if category == preferred_category:
            print(f"⭐ {name} - ${price} (Perfect match!)")
        else:
            print(f"✓ {name} - ${price}")
    elif not in_stock:
        print(f"✗ {name} - Out of stock")
    else:
        print(f"✗ {name} - ${price} (Over budget)")
```

## Error Handling and Edge Cases

### Defensive Programming

```python
# Safe division with multiple checks
def safe_divide(a, b):
    # Check if inputs are numbers
    if not isinstance(a, (int, float)) or not isinstance(b, (int, float)):
        return "Error: Both inputs must be numbers"
    
    # Check for division by zero
    if b == 0:
        return "Error: Cannot divide by zero"
    
    # Check for very small numbers that might cause issues
    if abs(b) < 1e-10:
        return "Error: Divisor too close to zero"
    
    result = a / b
    
    # Check for overflow
    if abs(result) > 1e10:
        return "Error: Result too large"
    
    return result

# Test the function
print(safe_divide(10, 2))      # 5.0
print(safe_divide(10, 0))      # Error: Cannot divide by zero
print(safe_divide("10", 2))    # Error: Both inputs must be numbers
```

### Input Sanitization

```python
# Process user input safely
def get_positive_number():
    while True:
        user_input = input("Enter a positive number: ")
        
        # Check if input is empty
        if not user_input.strip():
            print("Please enter something!")
            continue
        
        # Try to convert to number
        try:
            number = float(user_input)
        except ValueError:
            print("Please enter a valid number!")
            continue
        
        # Check if positive
        if number <= 0:
            print("Please enter a positive number!")
            continue
        
        return number

# Use the function
number = get_positive_number()
print(f"You entered: {number}")
```

## State Machines

### Simple State Management

```python
# Simple game state machine
game_state = "menu"
score = 0
lives = 3

while True:
    if game_state == "menu":
        print("\n=== GAME MENU ===")
        print("1. Start Game")
        print("2. Quit")
        choice = input("Enter choice: ")
        
        if choice == "1":
            game_state = "playing"
            print("Game started!")
        elif choice == "2":
            print("Thanks for playing!")
            break
        else:
            print("Invalid choice!")
    
    elif game_state == "playing":
        print(f"\nScore: {score}, Lives: {lives}")
        action = input("Enter action (jump/duck/quit): ")
        
        if action == "jump":
            score += 10
            print("Jumped! +10 points")
        elif action == "duck":
            score += 5
            print("Ducked! +5 points")
        elif action == "quit":
            game_state = "menu"
        else:
            print("Invalid action!")
        
        # Check game over condition
        if lives <= 0:
            print("Game Over!")
            game_state = "menu"
            score = 0
            lives = 3
```

## Best Practices for Logic Flow

1. **Keep it readable**: Use clear variable names and comments
2. **Handle edge cases**: Always consider what could go wrong
3. **Avoid deep nesting**: Use early returns or break complex conditions
4. **Test your logic**: Try different inputs and scenarios
5. **Use functions**: Break complex logic into smaller, manageable functions

```python
# Good example: Clear and readable
def process_student_data(students):
    results = []
    
    for student in students:
        if not student or "grades" not in student:
            continue  # Skip invalid students
        
        grades = student["grades"]
        if not grades:  # Empty grades list
            continue
        
        average = sum(grades) / len(grades)
        
        if average >= 90:
            status = "Excellent"
        elif average >= 80:
            status = "Good"
        elif average >= 70:
            status = "Average"
        else:
            status = "Needs Improvement"
        
        results.append({
            "name": student.get("name", "Unknown"),
            "average": average,
            "status": status
        })
    
    return results
```

## Summary

Logic flow is about creating intelligent programs that can:
- Make decisions based on data
- Handle different scenarios gracefully
- Process information systematically
- Respond to user input appropriately
- Manage program state effectively

Key concepts:
- Combine conditionals and loops for complex logic
- Handle edge cases and errors
- Create user-friendly interfaces
- Manage program state
- Write readable and maintainable code
