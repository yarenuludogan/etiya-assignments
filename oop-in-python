## Object-Oriented Programming (OOP)

**Object-Oriented Programming (OOP)** is a software development approach that emerged as a result of scalability challenges in the software development world. The "scale" mentioned here refers to the scope defined during project planning, where decisions are made about how large the project will be and what it will include.

The fundamental idea of OOP is to use virtual objects, rather than focusing primarily on functions and logic, to represent and solve real-world problems within software systems.

---

### Object

An object contains both data and methods, making programs more modular and reusable. Objects are defined by **classes**, which serve as blueprints for creating objects. This concept makes it easier to simulate real-life entities.

### Instance

An **instance** is a specific realization of an object at runtime, meaning it takes on actual values for each attribute. Each instance of an object can hold different attribute values, providing flexibility and dynamism in programming.

### Class

A **class** is a user-defined blueprint used to create objects. It defines the data members and member functions that objects of the class will have. Using classes, multiple objects with similar properties and behavior can be created without rewriting code repeatedly.

All classes have a built-in method called `__init__()` in Python, which is always executed when the class is being initiated. The method is used to assign values to objects or perform operations necessary when the object is being created.

Without the `__init__` method, you would need to set properties manually for each object.

### Example

```python
class Person:

    def __init__(self, name, age):
        self.name = name
        self.age = age

p1 = Person("Emil", 36)

print(p1.name)
print(p1.age)
```

## Advantages of OOP

* Provides a clear structure to programs
* Makes code easier to maintain, reuse, and debug
* Helps keep your code DRY (**Don't Repeat Yourself**)
* Allows you to build reusable applications with less code

## Four Tenets of OOP

### 1. Encapsulation

Encapsulation allows you to bundle data and behaviors within a class to create a cohesive unit. By defining methods to control access to attributes and their modification, encapsulation helps maintain data integrity and promotes modular, secure code.

This prevents accidental changes to your data and hides the internal details of how your class works.

#### Advantages of Encapsulation

* **Data hiding** → Sensitive data is protected from direct external access
* **Controlled access** → Data is accessed and modified only through defined methods (getters/setters)
* **Security** → Prevents unintended or incorrect use of data
* **Maintainability** → Internal implementation can change without affecting external code
* **Flexibility** → Validation and logic can be added when accessing or updating data
* **Reduced complexity** → Users interact only with the necessary parts of an object

In Python, you can make properties private by using a double underscore (`__`) prefix:

```python
self.__age = age
```

#### Getter Example

```python
def get_age(self):
    return self.__age
```

### Setter Example

```python
def set_age(self, age):
    if age > 0:
        self.__age = age
    else:
        print("Age must be positive")
```

---

### 2. Inheritance

Inheritance enables the creation of hierarchical relationships between classes, allowing a subclass to inherit attributes and methods from a parent class. This promotes code reuse and reduces duplication.

Inheritance is the process by which one class takes on the attributes and methods of another.

* **Parent Class** → The class being inherited from
* **Child Class** → The class that inherits from the parent class

#### Advantages of Inheritance

* **Code reusability**
* **Time saving**
* **Maintainability**
* **Extensibility**
* **Logical hierarchy**
* **Method overriding support**

#### Example

```python
class Parent:
    hair_color = "brown"

class Child(Parent):
    pass
```

Child classes can override or extend the attributes and methods of parent classes.

### Using `super()`

Python provides the `super()` function, which allows child classes to inherit methods and properties from the parent class.

```python
class Student(Person):

    def __init__(self, fname, lname):
        super().__init__(fname, lname)
```

---

### 3. Abstraction

Abstraction focuses on hiding implementation details and exposing only the essential functionality of an object.

It allows developers to focus on **what an object does** rather than **how it works internally**.

In large-scale systems, abstraction reduces complexity by separating high-level functionality from low-level implementation details.

#### Advantages

* Enhanced modularity
* Improved code readability
* Increased maintainability
* Better code reusability
* Reduced complexity

---

#### Abstract Base Class (ABC)

An **Abstract Base Class (ABC)** is used to achieve abstraction by defining a common interface for its subclasses.

It cannot be instantiated directly and serves as a blueprint for other classes.

Abstract classes are created using the `abc` module and the `@abstractmethod` decorator.

```python
from abc import ABC, abstractmethod

class Greet(ABC):

    @abstractmethod
    def say_hello(self):
        pass

class English(Greet):

    def say_hello(self):
        return "Hello!"

g = English()
print(g.say_hello())
```

#### Important

Abstract classes **cannot be instantiated directly**:

```python
g = Greet()  # TypeError
```

If a subclass does not implement all abstract methods, it also cannot be instantiated.

---

### Components of Abstraction

Python provides the `abc` module (**Abstract Base Classes**) to create custom abstract classes.

#### 1. Abstract Method

Abstract methods are method declarations without implementation.

```python
from abc import ABC, abstractmethod

class Animal(ABC):

    @abstractmethod
    def make_sound(self):
        pass
```

`make_sound()` must be implemented by subclasses.

---

#### 2. Concrete Method

Concrete methods are fully implemented methods within an abstract class.

```python
from abc import ABC, abstractmethod

class Animal(ABC):

    @abstractmethod
    def make_sound(self):
        pass

    def move(self):
        return "Moving"

class Dog(Animal):

    def make_sound(self):
        return "Bark"

dog = Dog()
print(dog.move())
```

---

#### 3. Abstract Properties

Abstract properties require subclasses to implement specific properties.

```python
from abc import ABC, abstractmethod

class Animal(ABC):

    @property
    @abstractmethod
    def species(self):
        pass

class Dog(Animal):

    @property
    def species(self):
        return "Canine"

dog = Dog()
print(dog.species)
```

---

#### 4. Multiple Abstract Methods

Subclasses must implement all abstract methods.

```python
from abc import ABC, abstractmethod

class Shape(ABC):

    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass

class Square(Shape):

    def area(self):
        return 4 * 4

    def perimeter(self):
        return 4 * 4

sq = Square()

print(sq.area(), sq.perimeter())
```

---

### 4. Polymorphism

The word **polymorphism** means **"many forms."**

In programming, it refers to methods, functions, or operators with the same name behaving differently depending on the object or data type.

Python's duck typing makes polymorphism especially powerful because it focuses on behavior rather than type.

#### Advantages of Polymorphism

* Code flexibility
* Code reusability
* Extensibility
* Simplified code
* Maintainability
* Loose coupling
* Improved readability

---

### Types of Polymorphism

#### 1. Compile-Time Polymorphism

Compile-time polymorphism involves selecting a method or operation before execution.

Python does not support traditional compile-time polymorphism but similar behavior can be achieved using:

* Default arguments
* `*args`
* `**kwargs`

---

#### 2. Runtime Polymorphism (Method Overriding)

Runtime polymorphism occurs when the behavior of a method is determined while the program is running.

A child class overrides a method from its parent class.

---

#### Polymorphism in Built-in Functions

Python built-in functions are polymorphic because they work with different data types.

```python
print(len("Hello"))
print(len([1, 2, 3]))

print(max(1, 3, 2))
print(max("a", "z", "m"))
```

---

#### Polymorphism in Functions

Using duck typing, functions can work with different object types.

```python
class Pen:

    def use(self):
        return "Writing"

class Eraser:

    def use(self):
        return "Erasing"

def perform_task(tool):
    print(tool.use())

perform_task(Pen())
perform_task(Eraser())
```

---

#### Polymorphism with Inheritance

```python
class Animal:

    def speak(self):
        return "Some sound"

class Dog(Animal):

    def speak(self):
        return "Bark"

class Cat(Animal):

    def speak(self):
        return "Meow"

animals = [Dog(), Cat()]

for animal in animals:
    print(animal.speak())
```

The same method (`speak`) produces different outputs depending on the object.

---

#### Operator Overloading

Operator overloading is a form of polymorphism where operators behave differently depending on the objects they are used with.

```python
class Number:

    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return Number(self.value + other.value)

    def __str__(self):
        return str(self.value)

n1 = Number(5)
n2 = Number(10)

print(n1 + n2)
```

---

#### Method Overloading in Python

Python does not support traditional method overloading. Similar behavior can be achieved using:

* Default arguments
* `*args`
* `**kwargs`

#### Example

```python
def add(a, b=0, c=0):
    return a + b + c

print(add(5))
print(add(5, 10))
print(add(5, 10, 15))
```

---

#### Duck Typing

Duck typing means that the actual type of an object is less important than the methods it provides.Python focuses on behavior rather than object type.

> "If it looks like a duck and quacks like a duck, it's a duck."


#### Example

```python
class Bird:

    def fly(self):
        return "Flying"

class Airplane:

    def fly(self):
        return "Flying in the sky"

def make_it_fly(obj):
    print(obj.fly())

make_it_fly(Bird())
make_it_fly(Airplane())
```

- Both objects work because they share the same method (`fly`), not the same class.
