# Classes and Objects - Practice Questions

## Question 1: Basic Class Creation
Create a class called `Student` with attributes `name`, `age`, and `grade`. Include a method called `introduce` that prints the student's information.

```python
class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade
    
    def introduce(self):
        print(f"Hi, I'm {self.name}, I'm {self.age} years old, and I'm in grade {self.grade}.")

# Test the class
student1 = Student("Alice", 16, 10)
student2 = Student("Bob", 17, 11)
student1.introduce()
student2.introduce()
```

## Question 2: Class with Methods
Create a class called `Rectangle` with attributes `length` and `width`. Include methods to:
- Calculate the area
- Calculate the perimeter
- Return a string representation of the rectangle

```python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width
    
    def area(self):
        return self.length * self.width
    
    def perimeter(self):
        return 2 * (self.length + self.width)
    
    def __str__(self):
        return f"Rectangle with length {self.length} and width {self.width}"

# Test the class
rect = Rectangle(5, 3)
print(rect)
print(f"Area: {rect.area()}")
print(f"Perimeter: {rect.perimeter()}")
```

## Question 3: Bank Account Class
Create a class called `BankAccount` with attributes `account_holder` and `balance`. Include methods to:
- Deposit money
- Withdraw money (with balance checking)
- Get the current balance
- Display account information

```python
class BankAccount:
    def __init__(self, account_holder, balance=0):
        self.account_holder = account_holder
        self.balance = balance
    
    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposited ${amount}. New balance: ${self.balance}")
        else:
            print("Deposit amount must be positive")
    
    def withdraw(self, amount):
        if amount > 0 and amount <= self.balance:
            self.balance -= amount
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid withdrawal amount")
    
    def get_balance(self):
        return self.balance
    
    def display_info(self):
        print(f"Account Holder: {self.account_holder}")
        print(f"Current Balance: ${self.balance}")

# Test the class
account = BankAccount("John Doe", 1000)
account.display_info()
account.deposit(500)
account.withdraw(200)
account.display_info()
```

## Question 4: Car Class with Methods
Create a class called `Car` with attributes `make`, `model`, `year`, and `mileage`. Include methods to:
- Start the car
- Drive a certain number of miles
- Get car information
- Check if the car needs maintenance (if mileage > 100,000)

```python
```

## Question 5: Class Attributes vs Instance Attributes
Create a class called `Employee` with:
- A class attribute `company` set to "Tech Corp"
- Instance attributes `name`, `employee_id`, and `salary`
- A class method to get the total number of employees
- An instance method to display employee information

```python
```

## Question 6: Inheritance - Animal Classes
Create a base class `Animal` with attributes `name` and `species`, and a method `make_sound`. Then create two subclasses:
- `Dog` that overrides `make_sound` to print "Woof!"
- `Cat` that overrides `make_sound` to print "Meow!"

```python
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species
    
    def make_sound(self):
        print(f"{self.name} makes a sound")

class Dog(Animal):
    def __init__(self, name):
        super().__init__(name, "Canine")
    
    def make_sound(self):
        print("Woof!")

class Cat(Animal):
    def __init__(self, name):
        super().__init__(name, "Feline")
    
    def make_sound(self):
        print("Meow!")

# Test the classes
dog = Dog("Buddy")
cat = Cat("Whiskers")
dog.make_sound()
cat.make_sound()
```

## Question 7: Property Decorators
Create a class called `Temperature` with a private attribute `_celsius`. Use property decorators to:
- Get the temperature in Celsius
- Set the temperature in Celsius (with validation: must be >= -273.15)
- Get the temperature in Fahrenheit (computed property)

```python
```

## Question 8: Special Methods (Magic Methods)
Create a class called `Fraction` with attributes `numerator` and `denominator`. Implement the following special methods:
- `__str__` to display the fraction as "numerator/denominator"
- `__add__` to add two fractions
- `__eq__` to check if two fractions are equal

```python
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
```

## Question 11: Student Grade Management
Create a class called `StudentGrades` with attributes `student_name` and `grades` (a list). Include methods to:
- Add a grade
- Calculate the average grade
- Get the highest grade
- Get the lowest grade
- Get the letter grade (A, B, C, D, F based on average)

```python
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
```

## Question 13: Bank Account with Interest
Extend the `BankAccount` class from Question 3 to include:
- An interest rate attribute
- A method to add interest to the balance
- A method to get account statement with transaction history
- A method to transfer money to another account

```python
```

## Question 14: Shape Hierarchy
Create a base class `Shape` with methods `area()` and `perimeter()`. Then create subclasses:
- `Circle` with radius attribute
- `Rectangle` with length and width attributes
- `Triangle` with base and height attributes

Each subclass should implement the area and perimeter methods appropriately.

```python
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
```

## Question 16: Game Character Class
Create a class called `GameCharacter` with attributes `name`, `health`, `attack_power`, and `defense`. Include methods to:
- Attack another character
- Take damage
- Heal
- Check if the character is alive
- Display character status

```python
```

## Question 17: Book Library with Categories
Create a class called `Book` with attributes `title`, `author`, `isbn`, `category`, and `is_borrowed`. Then create a `Library` class that can:
- Add books with categories
- Find books by category
- Find books by author
- Borrow and return books
- Get statistics (total books, books by category, etc.)

```python
```

## Question 18: Bank Account with Multiple Types
Create a base class `BankAccount` and two subclasses:
- `SavingsAccount` with interest rate and minimum balance
- `CheckingAccount` with overdraft limit

Each should have appropriate methods for their specific functionality.

```python
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
```

## Bonus Challenge: Complete Library Management System
Create a comprehensive library management system with:
- `Book` class with all necessary attributes
- `Member` class for library members
- `Library` class that manages books and members
- `Transaction` class to track borrowing/returning
- Methods for searching, borrowing, returning, and generating reports

```python
```

## Advanced Challenge: Bank System with Multiple Account Types
Create a complete banking system with:
- Base `Account` class
- `SavingsAccount`, `CheckingAccount`, and `BusinessAccount` subclasses
- `Customer` class to manage multiple accounts
- `Bank` class to manage customers and accounts
- Transaction history and reporting features

```python
```
