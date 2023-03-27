# Python Cheatsheet

## Data Types
# integer
my_int = 42
# floating point
my_float = 3.14
# boolean
my_bool = True
# string
my_string = "Hello World!"

## Control Structures
# if statement
if my_bool == True:
  # do something
else:
  # do something else

# for loop
for i in range(10):
  # do something

# while loop
while my_bool == True:
  # do something

## Functions
# function with no parameters and no return value
def my_function():
  # do something

# function with parameters and a return value
def add_numbers(x, y):
  return x + y

## Classes and Objects
# class definition
class MyClass:
  # properties
  my_property = 42
  # methods
  def my_method(self):
    # do something

# object instantiation
my_object = MyClass()
# set property
my_object.my_property = 42
# call method
my_object.my_method()

## Exception Handling
try:
  # do something that might throw an exception
except Exception as e:
  # handle the exception
finally:
  # always do this

## File I/O
# write to a file
with open("myfile.txt", "w") as f:
  f.write("Hello World!")

# read from a file
with open("myfile.txt", "r") as f:
  line = f.readline()

## Regular Expressions
import re
# match a pattern
pattern = re.compile(r"\d+")
match = pattern.match("123abc456def")
if match:
  # do something with match

## Modules and Packages
# import a module
import math
# use a function from the module
x = math.sqrt(4)

# import a module under an alias
import numpy as np
# use a function from the module
x = np.array([1, 2, 3])

# import a function from a module
from math import sqrt
# use the function
x = sqrt(4)

# create a package
my_package/
  __init__.py
  my_module.py
  subpackage/
    __init__.py
    my_submodule.py

# import a module from a package
from my_package import my_module
# use a function from the module
x = my_module.my_function()

# import a submodule from a package
from my_package.subpackage import my_submodule
# use a function from the submodule
x = my_submodule.my_function()

## List Comprehensions
# create a list of squares
squares = [x**2 for x in range(10)]

# create a list of even numbers
evens = [x for x in range(10) if x % 2 == 0]

## Lambda Functions
# define a lambda function
add = lambda x, y: x + y
# use the function
z = add(2, 3)

## Map and Filter
# apply a function to each element of a list
squares = list(map(lambda x: x**2, [1, 2, 3]))

# filter elements from a list
evens = list(filter(lambda x: x % 2 == 0, [1, 2, 3, 4]))

## Generators
# define a generator function
def my_generator():
  yield 1
  yield 2
  yield 3

# use the generator
gen = my_generator()
x = next(gen)  # 1
y = next(gen)  # 2
z = next(gen)  # 3

## Decorators
# define a decorator function
def my_decorator(func):
  def wrapper():
    print("Before the function is called.")
    func()
    print("After the function is called.")
  return wrapper

# apply the decorator to a function
@my_decorator
def my_function():
  print("Hello World!")

# call the decorated function
my_function()

## Context Managers
# define a context manager
class MyContextManager:
  def __enter__(self):
    print("Entering the context.")
  def __exit__(self, exc_type, exc_val, exc_tb):
    print("Exiting the context.")

# use the context manager
with MyContextManager():
  # do something in the context

## Threading
import threading
# define a worker function
def worker():
  # do something

# create a thread
thread = threading.Thread(target=worker)
# start the thread
thread.start()
# wait for the thread to finish
thread.join()

## Multiprocessing
import multiprocessing
# define a worker function
def worker():
  # do something

# create a process
process = multiprocessing.Process(target=worker)
# start the process
process.start()
# wait for the process to finish
process.join()

## Networking
import socket
# create a socket
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# connect to a server
sock.connect(("localhost", 12345))
# send data
sock.sendall(b"Hello World!")
# receive data
data = sock.recv(1024)
# close the socket
sock.close()

## Web Scraping
import requests
from bs4 import BeautifulSoup
# make a request to a webpage
response = requests.get("http://example.com")
# parse the HTML using BeautifulSoup
soup = BeautifulSoup(response.content, "html.parser")
# find all links on the page
links = soup.find_all("a")
# print the href attribute of each link
for link in links:
  print(link.get("href"))

## Data Science
import pandas as pd
# create a DataFrame
df = pd.DataFrame({"x": [1, 2, 3], "y": [4, 5, 6]})
# print the DataFrame
print(df)
# compute the mean of a column
mean = df["x"].mean()

import numpy as np
# create an array
arr = np.array([1, 2, 3])
# print the array
print(arr)
# compute the mean of the array
mean = np.mean(arr)

import matplotlib.pyplot as plt
# create a plot
x = np.linspace(0, 2*np.pi, 100)
y = np.sin(x)
plt.plot(x, y)
plt.show()
