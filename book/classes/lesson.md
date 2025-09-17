# Classes and Objects in Python

## What are Classes and Objects?

A **class** is a blueprint or template for creating objects. An **object** is an instance of a class that contains both data (attributes) and code (methods) that work with that data. Think of a class as a cookie cutter and objects as the cookies made from that cutter.

## Why Use Classes?

Classes provide several benefits:
- **Organization**: Group related data and functions together
- **Reusability**: Create multiple objects from the same class
- **Encapsulation**: Hide internal details and provide controlled access
- **Inheritance**: Create new classes based on existing ones
- **Polymorphism**: Use the same interface for different types of objects

## Basic Class Syntax

In Python, you define a class using the `class` keyword:

```python
class ClassName:
    """Optional docstring describing the class"""
    
    def __init__(self):
        """Constructor method - called when creating an object"""
        pass
    
    def method_name(self):
        """Instance method"""
        pass
```

## Creating Your First Class

Let's start with a simple `Person` class:

```python
class Person:
    """A simple class representing a person"""
    
    def __init__(self, name, age):
        """Initialize a Person object with name and age"""
        self.name = name
        self.age = age
    
    def introduce(self):
        """Method to introduce the person"""
        print(f"Hi, I'm {self.name} and I'm {self.age} years old.")

# Creating objects (instances) of the Person class
person1 = Person("Alice", 25)
person2 = Person("Bob", 30)

# Using the objects
person1.introduce()  # Output: Hi, I'm Alice and I'm 25 years old.
person2.introduce()  # Output: Hi, I'm Bob and I'm 30 years old.
```

## The `__init__` Method (Constructor)

The `__init__` method is called automatically when you create a new object. It's used to initialize the object's attributes:

```python
class Car:
    """A class representing a car"""
    
    def __init__(self, make, model, year):
        """Initialize a Car object"""
        self.make = make
        self.model = model
        self.year = year
        self.mileage = 0  # Default value
    
    def drive(self, miles):
        """Add miles to the car's mileage"""
        self.mileage += miles
        print(f"The {self.year} {self.make} {self.model} has driven {miles} more miles.")
    
    def get_info(self):
        """Return information about the car"""
        return f"{self.year} {self.make} {self.model} with {self.mileage} miles"

# Creating car objects
my_car = Car("Toyota", "Camry", 2020)
your_car = Car("Honda", "Civic", 2019)

# Using the objects
my_car.drive(100)  # Output: The 2020 Toyota Camry has driven 100 more miles.
print(my_car.get_info())  # Output: 2020 Toyota Camry with 100 miles
```

## Instance Attributes vs Class Attributes

**Instance attributes** belong to specific objects, while **class attributes** are shared by all instances of the class:

```python
class Dog:
    # Class attribute (shared by all instances)
    species = "Canis familiaris"
    
    def __init__(self, name, breed):
        # Instance attributes (unique to each object)
        self.name = name
        self.breed = breed
        self.tricks = []
    
    def add_trick(self, trick):
        """Add a trick to the dog's repertoire"""
        self.tricks.append(trick)
    
    def get_info(self):
        """Return information about the dog"""
        return f"{self.name} is a {self.breed} and knows {len(self.tricks)} tricks"

# Creating dog objects
dog1 = Dog("Buddy", "Golden Retriever")
dog2 = Dog("Max", "German Shepherd")

# Adding tricks
dog1.add_trick("sit")
dog1.add_trick("roll over")
dog2.add_trick("fetch")

# Accessing attributes
print(dog1.get_info())  # Output: Buddy is a Golden Retriever and knows 2 tricks
print(dog2.get_info())  # Output: Max is a German Shepherd and knows 1 tricks
print(f"Both dogs are {Dog.species}")  # Output: Both dogs are Canis familiaris
```

## Methods: Instance, Class, and Static

### Instance Methods
Instance methods work with instance data and take `self` as the first parameter:

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance=0):
        self.account_holder = account_holder
        self.balance = initial_balance
    
    def deposit(self, amount):
        """Deposit money into the account"""
        if amount > 0:
            self.balance += amount
            print(f"Deposited ${amount}. New balance: ${self.balance}")
        else:
            print("Deposit amount must be positive")
    
    def withdraw(self, amount):
        """Withdraw money from the account"""
        if amount > 0 and amount <= self.balance:
            self.balance -= amount
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid withdrawal amount")
    
    def get_balance(self):
        """Return the current balance"""
        return self.balance

# Using the BankAccount class
account = BankAccount("John Doe", 1000)
account.deposit(500)   # Output: Deposited $500. New balance: $1500
account.withdraw(200)  # Output: Withdrew $200. New balance: $1300
```

### Class Methods
Class methods work with the class itself and take `cls` as the first parameter:

```python
class Student:
    total_students = 0  # Class attribute
    
    def __init__(self, name, student_id):
        self.name = name
        self.student_id = student_id
        Student.total_students += 1
    
    @classmethod
    def get_total_students(cls):
        """Return the total number of students"""
        return cls.total_students
    
    @classmethod
    def create_from_string(cls, student_string):
        """Create a student from a string like 'John Doe,12345'"""
        name, student_id = student_string.split(',')
        return cls(name.strip(), student_id.strip())

# Using class methods
student1 = Student("Alice", "12345")
student2 = Student("Bob", "67890")
print(Student.get_total_students())  # Output: 2

# Creating student from string
student3 = Student.create_from_string("Charlie, 11111")
print(Student.get_total_students())  # Output: 3
```

### Static Methods
Static methods don't work with instance or class data and don't take `self` or `cls`:

```python
class MathUtils:
    @staticmethod
    def add(a, b):
        """Add two numbers"""
        return a + b
    
    @staticmethod
    def multiply(a, b):
        """Multiply two numbers"""
        return a * b
    
    @staticmethod
    def is_even(number):
        """Check if a number is even"""
        return number % 2 == 0

# Using static methods
result = MathUtils.add(5, 3)  # Output: 8
print(MathUtils.is_even(10))  # Output: True
```

## Encapsulation: Private and Protected Attributes

Python uses naming conventions to indicate the visibility of attributes:

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance=0):
        self.account_holder = account_holder
        self._balance = initial_balance  # Protected (single underscore)
        self.__account_number = "12345"  # Private (double underscore)
    
    def get_balance(self):
        """Public method to access balance"""
        return self._balance
    
    def __validate_transaction(self, amount):
        """Private method for internal use"""
        return amount > 0 and amount <= self._balance
    
    def deposit(self, amount):
        """Deposit money with validation"""
        if self.__validate_transaction(amount):
            self._balance += amount
            return True
        return False

# Using the class
account = BankAccount("John", 1000)
print(account.get_balance())  # Output: 1000
# print(account.__account_number)  # This would cause an error
```

## Inheritance

Inheritance allows you to create new classes based on existing ones:

```python
class Animal:
    """Base class for all animals"""
    
    def __init__(self, name, species):
        self.name = name
        self.species = species
    
    def make_sound(self):
        """Generic animal sound"""
        print(f"{self.name} makes a sound")
    
    def eat(self):
        """Generic eating behavior"""
        print(f"{self.name} is eating")

class Dog(Animal):
    """Dog class inheriting from Animal"""
    
    def __init__(self, name, breed):
        super().__init__(name, "Canine")  # Call parent constructor
        self.breed = breed
    
    def make_sound(self):
        """Override the parent method"""
        print(f"{self.name} barks")
    
    def fetch(self):
        """Dog-specific method"""
        print(f"{self.name} is fetching the ball")

class Cat(Animal):
    """Cat class inheriting from Animal"""
    
    def __init__(self, name, color):
        super().__init__(name, "Feline")
        self.color = color
    
    def make_sound(self):
        """Override the parent method"""
        print(f"{self.name} meows")
    
    def climb(self):
        """Cat-specific method"""
        print(f"{self.name} is climbing")

# Using the classes
dog = Dog("Buddy", "Golden Retriever")
cat = Cat("Whiskers", "Orange")

dog.make_sound()  # Output: Buddy barks
cat.make_sound()  # Output: Whiskers meows
dog.fetch()       # Output: Buddy is fetching the ball
cat.climb()       # Output: Whiskers is climbing
```

## Multiple Inheritance

Python supports multiple inheritance, where a class can inherit from multiple parent classes:

```python
class Flyable:
    """Mixin class for flying behavior"""
    
    def fly(self):
        print(f"{self.name} is flying")

class Swimmable:
    """Mixin class for swimming behavior"""
    
    def swim(self):
        print(f"{self.name} is swimming")

class Duck(Animal, Flyable, Swimmable):
    """Duck inherits from Animal, Flyable, and Swimmable"""
    
    def __init__(self, name):
        super().__init__(name, "Bird")
    
    def make_sound(self):
        print(f"{self.name} quacks")

# Using the Duck class
duck = Duck("Donald")
duck.make_sound()  # Output: Donald quacks
duck.fly()         # Output: Donald is flying
duck.swim()        # Output: Donald is swimming
```

## Special Methods (Magic Methods)

Special methods allow you to define how objects behave with built-in functions and operators:

```python
class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
    
    def __str__(self):
        """String representation for print()"""
        return f"'{self.title}' by {self.author}"
    
    def __len__(self):
        """Length representation for len()"""
        return self.pages
    
    def __eq__(self, other):
        """Equality comparison"""
        return self.title == other.title and self.author == other.author
    
    def __add__(self, other):
        """Addition operator"""
        return Book(f"{self.title} & {other.title}", 
                   f"{self.author} & {other.author}", 
                   self.pages + other.pages)

# Using the Book class
book1 = Book("Python Basics", "John Doe", 300)
book2 = Book("Advanced Python", "Jane Smith", 400)

print(book1)           # Output: 'Python Basics' by John Doe
print(len(book1))      # Output: 300
print(book1 == book2)  # Output: False

combined = book1 + book2
print(combined)        # Output: 'Python Basics & Advanced Python' by John Doe & Jane Smith
```

## Property Decorators

Properties allow you to create getter and setter methods that look like regular attributes:

```python
class Circle:
    def __init__(self, radius):
        self._radius = radius
    
    @property
    def radius(self):
        """Getter for radius"""
        return self._radius
    
    @radius.setter
    def radius(self, value):
        """Setter for radius with validation"""
        if value < 0:
            raise ValueError("Radius cannot be negative")
        self._radius = value
    
    @property
    def area(self):
        """Calculate and return area"""
        import math
        return math.pi * self._radius ** 2
    
    @property
    def circumference(self):
        """Calculate and return circumference"""
        import math
        return 2 * math.pi * self._radius

# Using the Circle class
circle = Circle(5)
print(f"Radius: {circle.radius}")        # Output: Radius: 5
print(f"Area: {circle.area:.2f}")        # Output: Area: 78.54
print(f"Circumference: {circle.circumference:.2f}")  # Output: Circumference: 31.42

circle.radius = 10  # Using the setter
print(f"New area: {circle.area:.2f}")    # Output: New area: 314.16
```

## Practical Examples

### Example 1: Library Management System

```python
class Book:
    def __init__(self, title, author, isbn):
        self.title = title
        self.author = author
        self.isbn = isbn
        self.is_borrowed = False
    
    def borrow(self):
        if not self.is_borrowed:
            self.is_borrowed = True
            return True
        return False
    
    def return_book(self):
        self.is_borrowed = False
    
    def __str__(self):
        status = "Available" if not self.is_borrowed else "Borrowed"
        return f"'{self.title}' by {self.author} - {status}"

class Library:
    def __init__(self, name):
        self.name = name
        self.books = []
    
    def add_book(self, book):
        self.books.append(book)
    
    def find_book(self, title):
        for book in self.books:
            if book.title.lower() == title.lower():
                return book
        return None
    
    def list_available_books(self):
        available = [book for book in self.books if not book.is_borrowed]
        return available

# Using the library system
library = Library("City Library")

book1 = Book("Python Programming", "John Doe", "123456789")
book2 = Book("Data Science", "Jane Smith", "987654321")

library.add_book(book1)
library.add_book(book2)

print(book1)  # Output: 'Python Programming' by John Doe - Available
book1.borrow()
print(book1)  # Output: 'Python Programming' by John Doe - Borrowed
```

### Example 2: Bank Account with Interest

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance=0, interest_rate=0.01):
        self.account_holder = account_holder
        self.balance = initial_balance
        self.interest_rate = interest_rate
        self.transaction_history = []
    
    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            self.transaction_history.append(f"Deposit: +${amount}")
            return True
        return False
    
    def withdraw(self, amount):
        if 0 < amount <= self.balance:
            self.balance -= amount
            self.transaction_history.append(f"Withdrawal: -${amount}")
            return True
        return False
    
    def add_interest(self):
        interest = self.balance * self.interest_rate
        self.balance += interest
        self.transaction_history.append(f"Interest: +${interest:.2f}")
    
    def get_statement(self):
        print(f"Account Holder: {self.account_holder}")
        print(f"Current Balance: ${self.balance:.2f}")
        print("Transaction History:")
        for transaction in self.transaction_history:
            print(f"  {transaction}")

# Using the bank account
account = BankAccount("Alice Johnson", 1000, 0.02)
account.deposit(500)
account.withdraw(200)
account.add_interest()
account.get_statement()
```

## Best Practices

1. **Use descriptive class and method names**
2. **Follow the single responsibility principle** - each class should have one job
3. **Use docstrings** to document your classes and methods
4. **Keep methods small and focused**
5. **Use properties for computed attributes**
6. **Prefer composition over inheritance** when possible

```python
class GoodExample:
    """A well-designed class following best practices"""
    
    def __init__(self, name, value):
        """
        Initialize the object.
        
        Args:
            name (str): The name of the object
            value (float): The initial value
        """
        self.name = name
        self._value = value
    
    @property
    def value(self):
        """Get the current value"""
        return self._value
    
    @value.setter
    def value(self, new_value):
        """Set the value with validation"""
        if new_value < 0:
            raise ValueError("Value cannot be negative")
        self._value = new_value
    
    def calculate_something(self):
        """Perform a calculation and return the result"""
        return self._value * 2
```

## Summary

Classes and objects are fundamental to object-oriented programming in Python. They allow you to:

- **Organize code** into logical, reusable components
- **Model real-world entities** with data and behavior
- **Create multiple instances** from the same blueprint
- **Inherit and extend** functionality from existing classes
- **Encapsulate data** and provide controlled access

Key concepts to remember:
- Classes are blueprints, objects are instances
- Use `__init__` to initialize objects
- Instance methods work with object data
- Inheritance allows code reuse and extension
- Special methods customize object behavior
- Properties provide controlled access to attributes
