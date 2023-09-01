# Python general questions

### 🔶 1. What is the complexity in O-notation of the len operation of list?

---
#### Answer:
The complexity of the len operation of a list in Python is O(1). This is because the length of a list is stored as a separate attribute, making it a constant-time operation to retrieve the length.

### 🔶 2. And in the O-notation, the difficulty of obtaining an element by index in a list?

---
#### Answer:
The complexity of obtaining an element by index in a list in Python is O(1). This is because lists in Python are implemented as arrays, which allow for constant-time access to elements by index.

### 🔶 3. What is the structure of the implementation of dictionaries? How is the fight against key collisions implemented?

---
#### Answer:
Dictionaries in Python are implemented as a hash table. The fight against key collisions is implemented by using a technique called open addressing, which involves finding the next open slot in the table for a key-value pair that would have otherwise collided with an existing key.

### 🔶 4. How does the Garbage Collector work in Python?

---
#### Answer:
The Garbage Collector in Python works by periodically checking for objects in memory that are no longer being used by the program. Once such objects are identified, they are deallocated and their memory is freed up.

### 🔶 5. With what data structure is set implemented?

---
#### Answer:
A set in Python is implemented as a hash table. This allows for fast insertion, deletion and membership tests.

### 🔶 6. What are decorators and how do they work?

---
#### Answer:
Decorators in Python are a way to modify or extend the functionality of a function or class. They are implemented as functions that take another function as an argument and return a new function that usually includes the functionality of the original function.
```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("hello!")

say_hello()
# Output: 
# Something is happening before the function is called.
# hello!
# Something is happening after the function is called.

```
### 🔶 7. What are generators and how do they work?

---
#### Answer:
Generators in Python are a special type of iterator that allow a programmer to iterate over a sequence of items, without the need to keep the entire sequence in memory. They are implemented as functions that use the "yield" keyword to return an iterator, instead of a list. When a generator function is called, it returns a generator object, which can be used in a for loop or with the next() function to iterate through the generated sequence.
```python
def my_gen():
    yield 1
    yield 2
    yield 3

for i in my_gen():
    print(i)
# Output:
# 1
# 2
# 3
```
### 🔶 8. What are context managers and how do they work?

---
#### Answer:
Context managers in Python are used to set up and tear down a context around a block of code. They are implemented using the "with" statement and a context manager object, which has methods such as "enter" and "exit" that are called when the context is entered and exited. This is useful for managing resources such as file and network connections, where it's important to ensure that the resources are properly closed and cleaned up after use. The "with" statement automatically handles the calls to the "enter" and "exit" methods, making it easy to ensure that the resources are properly managed, even in the presence of exceptions.

### <a href="#top"> Back to top ⬆️</a>

# Python general questions

### 🔶 1. What is the complexity in O-notation of the len operation of list?

---
#### Answer:
The complexity of the len operation of a list in Python is O(1). This is because the length of a list is stored as a separate attribute, making it a constant-time operation to retrieve the length.

### 🔶 2. And in the O-notation, the difficulty of obtaining an element by index in a list?

---
#### Answer:
The complexity of obtaining an element by index in a list in Python is O(1). This is because lists in Python are implemented as arrays, which allow for constant-time access to elements by index.

### 🔶 3. What is the structure of the implementation of dictionaries? How is the fight against key collisions implemented?

---
#### Answer:
Dictionaries in Python are implemented as a hash table. The fight against key collisions is implemented by using a technique called open addressing, which involves finding the next open slot in the table for a key-value pair that would have otherwise collided with an existing key.

### 🔶 4. How does the Garbage Collector work in Python?

---
#### Answer:
The Garbage Collector in Python works by periodically checking for objects in memory that are no longer being used by the program. Once such objects are identified, they are deallocated and their memory is freed up.

### 🔶 5. With what data structure is set implemented?

---
#### Answer:
A set in Python is implemented as a hash table. This allows for fast insertion, deletion and membership tests.

### 🔶 6. What are decorators and how do they work?

---
#### Answer:
Decorators in Python are a way to modify or extend the functionality of a function or class. They are implemented as functions that take another function as an argument and return a new function that usually includes the functionality of the original function.
```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("hello!")

say_hello()
# Output: 
# Something is happening before the function is called.
# hello!
# Something is happening after the function is called.

```
### 🔶 7. What are generators and how do they work?

---
#### Answer:
Generators in Python are a special type of iterator that allow a programmer to iterate over a sequence of items, without the need to keep the entire sequence in memory. They are implemented as functions that use the "yield" keyword to return an iterator, instead of a list. When a generator function is called, it returns a generator object, which can be used in a for loop or with the next() function to iterate through the generated sequence.
```python
def my_gen():
    yield 1
    yield 2
    yield 3

for i in my_gen():
    print(i)
# Output:
# 1
# 2
# 3
```
### 🔶 8. What are context managers and how do they work?

---
#### Answer:
Context managers in Python are used to set up and tear down a context around a block of code. They are implemented using the "with" statement and a context manager object, which has methods such as "enter" and "exit" that are called when the context is entered and exited. This is useful for managing resources such as file and network connections, where it's important to ensure that the resources are properly closed and cleaned up after use. The "with" statement automatically handles the calls to the "enter" and "exit" methods, making it easy to ensure that the resources are properly managed, even in the presence of exceptions.

### <a href="#top"> Back to top ⬆️</a>

# SQL

### 🔶 1. What types of relationships between tables do you know?

---
#### Answer:
Types of relationships between tables are:
- One-to-One: where one record in table A corresponds to one record in table B
- One-to-Many: where one record in table A corresponds to multiple records in table B
- Many-to-Many: where multiple records in table A correspond to multiple records in table B
### 🔶 2. What types of JOIN do you know? What is the difference?

---
#### Answer:
- INNER JOIN: only returns records where there is a match in both tables
- LEFT JOIN: returns all records from the left table and any matching records from the right table
- RIGHT JOIN: returns all records from the right table and any matching records from the left table
- FULL OUTER JOIN: returns all records from both tables
### 🔶 3. What is selectivity?

---
#### Answer:
Selectivity is the degree to which the values of a column in a table are unique. A column with high selectivity has unique values, while a column with low selectivity has many repeating values. This is important when creating indexes, because an index on a column with high selectivity will be more efficient than an index on a column with low selectivity.
### 🔶 4. Have you ever profiled requests?

---
#### Answer:
Profiling requests is the process of measuring the performance of a database query and identifying bottlenecks. This can be done using tools such as the EXPLAIN command in SQL or a database profiler.

#### Example:
```postgresql
EXPLAIN SELECT * FROM users_table WHERE name = 'Alice';
```
### 🔶 5. What is the difference between explain and explain analyze?

---
#### Answer:
The difference between EXPLAIN and EXPLAIN ANALYZE is that EXPLAIN shows the execution plan of the query without actually running it, while EXPLAIN ANALYZE not only shows the execution plan but also runs the query and provides statistics on its performance.

### 🔶 6. In what order is the SELECT query evaluated?

---
#### Answer:
SELECT query is evaluated in the following order:
- FROM clause
- JOIN clause
- WHERE clause
- GROUP BY clause
- HAVING clause
- SELECT clause
- ORDER BY clause
### 🔶 7. What is an index?

---
#### Answer:
An index is a database feature that allows for faster searching and sorting of data. Indexes can be created on one or more columns of a table, and are used to quickly locate specific rows in the table.
### 🔶 8. What indexes do you know?

---
#### Answer:
Types of indexes:
- B-Tree index
- Bitmap index
- Hash index
- Full-text index
- Spatial index

### 🔶 9. What is B-Tree?

---
#### Answer:
B-Tree index is a balanced tree data structure that stores data in a sorted order and allows for efficient insertion, deletion and search operations. It is commonly used in databases to improve the performance of SELECT, INSERT and UPDATE operations. In a B-Tree, the data is stored in a balanced tree, so the height of the tree is always

---

## Here is a list of features that correspond to the Middle+ level:
- You quickly answer simple questions about indexes.
- You are answering a question about transaction isolation levels.
- You have experience in query profiling and optimization.
- You can write complex queries such as window functions and CTEs.
- You understand when not to write complex queries.

### <a href="#top"> Back to top ⬆️</a>

# OOP

### 🔶 1. Explain the basic principles of OOP.

---
#### Answer:
Object-oriented programming (OOP) is a programming paradigm that uses objects, which are instances of classes, to represent and manipulate data. The basic principles of OOP include encapsulation, inheritance, and polymorphism.
### 🔶 2. Are you familiar with SOLID? Look at the code, are there any SOLID principles violated here? How can this be fixed?

---
#### Answer:
SOLID is a set of five principles for object-oriented software design, which stands for Single responsibility, Open-closed, Liskov substitution, Interface segregation, and Dependency Inversion.

### Example:
```python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed
    def bark(self):
        print("Woof!")
    def fetch(self):
        print("Fetching...")
    def playDead(self):
        print("Playing dead...")
    def rollOver(self):
        print("Rolling over...")
    def chaseTail(self):
        print("Chasing tail...")
        
# This class violates the Single Responsibility Principle as it has too many methods which are doing different tasks.
```
It can be fixed by splitting the class into multiple classes each with a single responsibility

```python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed
    def bark(self):
        print("Woof!")

class Tricks:
    def fetch(self):
        print("Fetching...")
    def playDead(self):
        print("Playing dead...")
    def rollOver(self):
        print("Rolling over...")
    def chaseTail(self):
        print("Chasing tail...")

```
### 🔶 3. What OOP patterns are you familiar with?

---
#### Answer:

Some common OOP patterns include:
- Singleton pattern: which ensures that a class has only one instance
- Factory pattern: which creates objects without specifying the exact class of object that will be created
- Decorator pattern: which allows behavior to be added to an individual object, either statically or dynamically
- Observer pattern: which allows objects to be notified of changes to other objects
### 🔶 4. How is an interface different from an abstract class?

---
#### Answer:
An interface is a collection of abstract methods (methods with no implementation) that a class must implement. An abstract class is a class that contains one or more abstract methods, but may also have implemented methods. An interface defines a contract, but an abstract class can provide a partial implementation.
### 🔶 5. What are class methods defined through the @classmethod decorator? What are they needed for?

---
#### Answer:
Class methods are methods that are bound to the class and not the instance of the object. They are defined using the @classmethod decorator and take the class as the first argument instead of self. They are useful for creating alternative constructors for a class.

### Example:
```python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed
        
    @classmethod
    def create_from_tuple(cls, name_breed_tuple):
        return cls(*name_breed_tuple)

dog = Dog.create_from_tuple(("Fido", "Golden Retriever"))
print(dog.name)
```
### 🔶 6. How are private attributes declared in Python?

---
#### Answer:
In Python, private attributes are denoted by a double leading underscore. This is a convention indicating that the attribute should not be accessed directly from outside the class, although it can still be accessed if necessary.

### Example:
```python
class Dog:
    def __init__(self, name, breed):
        self.__name = name
        self.__breed = breed
    def get_name(self):
        return self.__name
    def get_breed(self):
        return self.__breed

dog = Dog("Fido", "Golden Retriever")
print(dog.__name)  # This will raise an AttributeError
print(dog.get_name())  # This will return "Fido"
```
### 🔶 7. What is MRO in Python?

---
#### Answer:
The Method Resolution Order (MRO) is the order in which the interpreter looks for methods in a class hierarchy. In Python, the MRO is determined by C3, which is a linearization algorithm that finds the order of methods that avoids diamond problem and provide a consistent method resolution order. It works by first determining the depth of the class, and then the order of classes by checking the left-most class first, and then moving to the right.

### Example:
```python
class A:
    def method(self):
        print("Class A method")

class B(A):
    pass

class C(A):
    def method(self):
        print("Class C method")

class D(B, C):
    pass

d = D()
d.method() # Output: "Class C method"
```
in the above example, python interpreter first look for the method in class D, it's not present then it looks in class B which also not present then it looks in class C and it found the method there so it will use this method.

You can use the built-in help function to check the MRO of a class, it prints the order of classes that Python will look through when searching for a method.
```python
help(D)
```
This will output something like
```python
class D(B, C)
 |  Method resolution order:
 |      D
 |      B
 |      C
 |      A
```
It lists the classes in the order that Python will look for methods in them.

### <a href="#top"> Back to top ⬆️</a>


