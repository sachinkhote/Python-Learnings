
## 1. Why OOP?
- **Problem with old style (procedural programming)**:  
  Code is just functions + raw data. As projects grow, it becomes messy and hard to maintain.
- **Solution with OOP**:  
  Bundle **data + behavior** together into **objects**.  
  Example: Instead of separate deposit/withdraw functions, create an **Account class** with attributes (`balance`) and methods (`deposit()`, `withdraw()`).

---

## 2. Classes and Objects
- **Class** = Blueprint (like a house plan).  
- **Object** = Actual instance (like a real house built from the plan).

### Example:
```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
    
    def start(self):
        print(f"{self.year} {self.make} {self.model} is starting.")

car1 = Car("Toyota", "Camry", 2020)
car1.start()   # Output: 2020 Toyota Camry is starting.
```

---

## 3. Key OOP Concepts

### A) **Encapsulation**
- Hide internal details, expose only safe methods.
- Example: Bank account balance is private, accessed only via `deposit()`, `withdraw()`, `get_balance()`.

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance   # private
    
    def deposit(self, amount):
        self.__balance += amount
    
    def get_balance(self):
        return self.__balance
```

---

### B) **Inheritance**
- Reuse code by creating a base class and extending it.
- Example: `Car` and `Bike` inherit from `Vehicle`.

```python
class Vehicle:
    def __init__(self, make):
        self.make = make

class Car(Vehicle):
    def __init__(self, make, doors):
        super().__init__(make)
        self.doors = doors
```

---

### C) **Polymorphism**
- Same method name, different behavior depending on the object.
- Example: `make_sound()` works differently for Dog and Cat.

```python
class Animal:
    def make_sound(self): pass

class Dog(Animal):
    def make_sound(self): return "Bark"

class Cat(Animal):
    def make_sound(self): return "Meow"

def animal_sound(animal):
    print(animal.make_sound())

animal_sound(Dog())  # Bark
animal_sound(Cat())  # Meow
```

---

### D) **Abstraction**
- Show only what’s necessary, hide the complex details.
- Example: Abstract `Shape` class defines `area()`, but doesn’t say how.  
  Circle and Rectangle implement it differently.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self): pass

class Circle(Shape):
    def area(self): return 3.14 * 5 * 5
```

---

## 4. Real-Life Example: Library System
- **Book class** → attributes: title, author; methods: `check_out()`, `return_book()`.
- **Member class** → attributes: name, borrowed_books; methods: `borrow_book()`, `return_book()`.

This models how books and members interact in a real library.

---

## 5. Benefits of OOP
1. **Manages complexity** → modular, organized code.  
2. **Reusability** → inheritance avoids duplication.  
3. **Extensibility** → easy to add new features.  
4. **Encapsulation & Abstraction** → protect data, simplify usage.  
5. **Polymorphism** → flexible functions that work with different objects.

---

# 🎯 Key Takeaways
- **Class = blueprint, Object = instance.**
- OOP makes code **modular, reusable, and easier to maintain**.
- Four pillars of OOP:  
  - **Encapsulation** (hide data)  
  - **Inheritance** (reuse code)  
  - **Polymorphism** (same interface, different behavior)  
  - **Abstraction** (hide complexity)

---
