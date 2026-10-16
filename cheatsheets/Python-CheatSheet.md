# Python Cheatsheet

## Basic Syntax

### Variables and Data Types

```python
# Variables
x = 5
y = "Hello, World!"
z = 3.14

# Data Types
x = 5                       # int
y = "Hello, World!"         # str
z = 3.14                    # float
w = 1j                      # complex
b = True                    # bool
l = ["apple", "banana", "cherry"]    # list
t = ("apple", "banana", "cherry")   # tuple
s = {"apple", "banana", "cherry"}   # set
d = {"name": "John", "age": 36}     # dict

# Type Conversion
x = str(3)                  # '3'
y = int(3.5)                # 3
z = float("3.14")           # 3.14

# Printing
print("Hello, World!")

# Input
name = input("Enter your name: ")

# Comments
# This is a comment

```

# Control Flow

```python
# if-else statement
x = 5
if x > 0:
    print("x is positive")
elif x == 0:
    print("x is zero")
else:
    print("x is negative")

# for loop
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# while loop
i = 1
while i < 6:
    print(i)
    i += 1

# break and continue
for i in range(10):
    if i == 5:
        break
    if i % 2 == 0:
        continue
    print(i)
```
# Functions
```python
# Defining a function
def greet(name):
    print("Hello, " + name)

# Calling a function
greet("John")

# Default parameter value
def greet(name, greeting="Hello"):
    print(greeting + ", " + name)

greet("John")
greet("John", "Good morning")

```
# Modules and Packages
```python
# Importing a module
import random
print(random.randint(1, 10))

# Importing specific functions from a module
from math import sqrt
print(sqrt(25))

# Creating a package
# mypackage/
#   __init__.py
#   math/
#     __init__.py
#     operations.py

# Importing from a package
from mypackage.math.operations import add
print(add(2, 3))
```
# File I/O

Use a context manager so each file is closed even if an operation raises an
exception. Write the sample file first so it also works in a new folder.

```python
with open("myfile.txt", "w", encoding="utf-8") as file:
    file.write("Hello, World!")

with open("myfile.txt", "r", encoding="utf-8") as file:
    print(file.read())  # Hello, World!
```

Opening a file with `"w"` truncates existing content. Use `"a"` to append instead.
# Exception Handling
```python
# Catch the failure expected from this operation.
try:
    age = int("not a number")
except ValueError as error:
    print(f"Invalid age: {error}")

# Raise a specific exception for an invalid argument.
def require_nonnegative(value):
    if value < 0:
        raise ValueError("value cannot be negative")
    return value

try:
    require_nonnegative(-1)
except ValueError as error:
    print(error)  # value cannot be negative
```
# Object-Oriented Programming
```python
# Defining a class
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print("Hello, my name is " + self.name)

# Creating an object
p1 = Person("John", 36)

# Accessing object properties
print(p1.name)
print(p1.age)

# Calling object methods
p1.greet()

# Inheritance
class Student(Person):
    def __init__(self, name, age, year):
        super().__init__(name, age)
        self.year = year

    def study(self):
        print(self.name + " is studying")

# Creating a derived class object
s1 = Student("Jane", 21, 2022)

# Accessing properties from the base class
print(s1.name)
print(s1.age)

# Calling methods from the base class
s1.greet()

# Calling methods from the derived class
s1.study()
```
# Regular Expressions
```python
import re

# Matching a pattern
txt = "The rain in Spain"
x = re.search(r"^The.*Spain$", txt)

if x:
    print("Match found")
else:
    print("Match not found")

# Replacing a string
txt = "The rain in Spain"
x = re.sub(r"\s", "-", txt)

print(x)
```
# Networking
```python
import socket

# A low-level HTTP demonstration; use an HTTP client for application code.
request = (
    b"GET / HTTP/1.1\r\n"
    b"Host: example.com\r\n"
    b"Connection: close\r\n\r\n"
)

with socket.create_connection(("example.com", 80), timeout=5) as connection:
    connection.sendall(request)
    # recv returns at most this many bytes; this is only a response preview.
    preview = connection.recv(1024)
    print(preview.decode("utf-8", errors="replace"))
```
# Multithreading
```python
import threading

# Creating a thread
def print_numbers():
    for i in range(10):
        print(i)

t = threading.Thread(target=print_numbers)

# Starting a thread
t.start()

# Waiting for a thread to finish
t.join()

# Using a thread pool
from concurrent.futures import ThreadPoolExecutor

def print_number(n):
    print(n)

with ThreadPoolExecutor(max_workers=2) as executor:
    executor.submit(print_number, 1)
    executor.submit(print_number, 2)
```
# Data Science Libraries
```python
# Numpy
import numpy as np

# Creating an array
a = np.array([1, 2, 3])

# Basic operations
b = np.array([4, 5, 6])
c = a + b
d = a * b
e = np.dot(a, b)

# Pandas
import pandas as pd

# Creating a dataframe
data = {
    "name": ["John", "Jane", "Bob"],
    "age": [36, 21, 44]
}
df = pd.DataFrame(data)

# Accessing data
print(df["name"])
print(df.iloc[0])
print(df.loc[df["age"] > 30])

# Matplotlib
import matplotlib.pyplot as plt

# Creating a plot
x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 4, 6, 8, 10])
plt.plot(x, y)

# Displaying the plot
plt.show()
```
# Conclusion
This is just a basic Python cheatsheet with code snippets for various topics.
