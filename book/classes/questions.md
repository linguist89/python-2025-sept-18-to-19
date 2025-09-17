# Classes and Objects - Practice Questions

## Question 1: Basic Class Creation
Create a class called `Student` with attributes `name`, `age`, and `grade`. Include a method called `introduce` that prints the student's information.

```python
# Your code here
```

## Question 2: Class with Methods
Create a class called `Rectangle` with attributes `length` and `width`. Include methods to:
- Calculate the area
- Calculate the perimeter
- Return a string representation of the rectangle

```python
# Your code here
```

## Question 3: Bank Account Class
Create a class called `BankAccount` with attributes `account_holder` and `balance`. Include methods to:
- Deposit money
- Withdraw money (with balance checking)
- Get the current balance
- Display account information

```python
# Your code here
```

## Question 4: Car Class with Methods
Create a class called `Car` with attributes `make`, `model`, `year`, and `mileage`. Include methods to:
- Start the car
- Drive a certain number of miles
- Get car information
- Check if the car needs maintenance (if mileage > 100,000)

```python
# Your code here
```

## Question 5: Class Attributes vs Instance Attributes
Create a class called `Employee` with:
- A class attribute `company` set to "Tech Corp"
- Instance attributes `name`, `employee_id`, and `salary`
- A class method to get the total number of employees
- An instance method to display employee information

```python
# Your code here
```

## Question 6: Inheritance - Animal Classes
Create a base class `Animal` with attributes `name` and `species`, and a method `make_sound`. Then create two subclasses:
- `Dog` that overrides `make_sound` to print "Woof!"
- `Cat` that overrides `make_sound` to print "Meow!"

```python
# Your code here
```

## Question 7: Property Decorators
Create a class called `Temperature` with a private attribute `_celsius`. Use property decorators to:
- Get the temperature in Celsius
- Set the temperature in Celsius (with validation: must be >= -273.15)
- Get the temperature in Fahrenheit (computed property)

```python
# Your code here
```

## Question 8: Special Methods (Magic Methods)
Create a class called `Fraction` with attributes `numerator` and `denominator`. Implement the following special methods:
- `__str__` to display the fraction as "numerator/denominator"
- `__add__` to add two fractions
- `__eq__` to check if two fractions are equal

```python
# Your code here
```

## Question 9: Library Book Management
Create a class called `Book` with attributes `title`, `author`, `isbn`, and `is_borrowed`. Include methods to:
- Borrow the book
- Return the book
- Check if the book is available
- Display book information

Then create a `Library` class that can:
- Add books
- Find books by title
- List all available books
- List all borrowed books

```python
# Your code here
```

## Question 10: Calculator Class
Create a class called `Calculator` with methods for basic operations:
- `add(a, b)`
- `subtract(a, b)`
- `multiply(a, b)`
- `divide(a, b)` (handle division by zero)
- `power(a, b)`
- `square_root(a)` (handle negative numbers)

```python
# Your code here
```

## Question 11: Student Grade Management
Create a class called `StudentGrades` with attributes `student_name` and `grades` (a list). Include methods to:
- Add a grade
- Calculate the average grade
- Get the highest grade
- Get the lowest grade
- Get the letter grade (A, B, C, D, F based on average)

```python
# Your code here
```

## Question 12: Shopping Cart Class
Create a class called `ShoppingCart` with methods to:
- Add items (with name, price, and quantity)
- Remove items
- Calculate the total cost
- Apply a discount percentage
- Display the cart contents
- Clear the cart

```python
# Your code here
```

## Question 13: Bank Account with Interest
Extend the `BankAccount` class from Question 3 to include:
- An interest rate attribute
- A method to add interest to the balance
- A method to get account statement with transaction history
- A method to transfer money to another account

```python
# Your code here
```

## Question 14: Shape Hierarchy
Create a base class `Shape` with methods `area()` and `perimeter()`. Then create subclasses:
- `Circle` with radius attribute
- `Rectangle` with length and width attributes
- `Triangle` with base and height attributes

Each subclass should implement the area and perimeter methods appropriately.

```python
# Your code here
```

## Question 15: Employee Management System
Create a class called `Employee` with attributes `name`, `employee_id`, `department`, and `salary`. Include methods to:
- Give a raise (percentage increase)
- Change department
- Get employee information
- Compare salaries with another employee

Then create a `Company` class that can:
- Add employees
- Remove employees
- Find employees by department
- Calculate total payroll
- Give raises to all employees in a department

```python
# Your code here
```

## Question 16: Game Character Class
Create a class called `GameCharacter` with attributes `name`, `health`, `attack_power`, and `defense`. Include methods to:
- Attack another character
- Take damage
- Heal
- Check if the character is alive
- Display character status

```python
# Your code here
```

## Question 17: Book Library with Categories
Create a class called `Book` with attributes `title`, `author`, `isbn`, `category`, and `is_borrowed`. Then create a `Library` class that can:
- Add books with categories
- Find books by category
- Find books by author
- Borrow and return books
- Get statistics (total books, books by category, etc.)

```python
# Your code here
```

## Question 18: Bank Account with Multiple Types
Create a base class `BankAccount` and two subclasses:
- `SavingsAccount` with interest rate and minimum balance
- `CheckingAccount` with overdraft limit

Each should have appropriate methods for their specific functionality.

```python
# Your code here
```

## Question 19: Student Course Management
Create a class called `Course` with attributes `course_name`, `course_code`, `credits`, and `students` (list). Include methods to:
- Add a student
- Remove a student
- Get the number of enrolled students
- Check if a student is enrolled

Then create a `Student` class that can:
- Enroll in courses
- Drop courses
- Calculate total credits
- Get GPA (you can use a simple grade system)

```python
# Your code here
```

## Question 20: Restaurant Order Management
Create a class called `MenuItem` with attributes `name`, `price`, and `category`. Then create a class called `Order` that can:
- Add menu items to the order
- Remove items from the order
- Calculate the total cost
- Apply tax
- Apply tip
- Display the order summary

```python
# Your code here
```

## Bonus Challenge: Complete Library Management System
Create a comprehensive library management system with:
- `Book` class with all necessary attributes
- `Member` class for library members
- `Library` class that manages books and members
- `Transaction` class to track borrowing/returning
- Methods for searching, borrowing, returning, and generating reports

```python
# Your code here
```

## Advanced Challenge: Bank System with Multiple Account Types
Create a complete banking system with:
- Base `Account` class
- `SavingsAccount`, `CheckingAccount`, and `BusinessAccount` subclasses
- `Customer` class to manage multiple accounts
- `Bank` class to manage customers and accounts
- Transaction history and reporting features

```python
# Your code here
```
