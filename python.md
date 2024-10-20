
# Python Guide

## **Python Indentation:**

In Python, **indentation** is crucial because it defines the structure of code blocks such as functions, loops, conditionals, etc. Unlike other programming languages (like C, Java, etc.) that use braces `{}` to define code blocks, Python uses indentation (whitespace) to determine the beginning and end of these blocks.

**Key Points:**
- Python requires consistent indentation. The most common practice is to use 4 spaces for each level of indentation (though you can also use tabs, but mixing tabs and spaces leads to errors).
- Indentation is not just for readability; it is **syntactically significant** in Python.
- Incorrect indentation will raise an `IndentationError`.

**Example:**

```python
# Correct indentation
if x > 5:
    print("x is greater than 5")  # Indented under 'if' block
else:
    print("x is 5 or less")       # Indented under 'else' block

# Incorrect indentation (raises IndentationError)
if x > 5:
    print("x is greater than 5")
 print("This line is incorrectly indented")  # This will cause an IndentationError
```

---

## **Basic Syntax:**

```python
# Print Statement
print("Hello, World!")

# Variables
x = 10              # Integer
y = 3.14            # Float
name = "Alice"      # String
is_valid = True     # Boolean

# Comments
# This is a single-line comment

'''
This is a
multi-line comment
'''

# Data Structures
# Lists (mutable, ordered)
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Outputs: apple

# Tuples (immutable, ordered)
fruits_tuple = ("apple", "banana", "cherry")
print(fruits_tuple[1])  # Outputs: banana

# Sets (unordered, unique elements)
fruits_set = {"apple", "banana", "cherry"}
print(fruits_set)  # Outputs: {'banana', 'apple', 'cherry'}

# Dictionaries (key-value pairs, unordered)
person = {"name": "John", "age": 30}
print(person['name'])  # Outputs: John
```

---

## **Control Flow:**

```python
# If-Else
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is 5")
else:
    print("x is less than 5")

# For Loop (Iterating through a list)
for fruit in fruits:
    print(fruit)  # Outputs each fruit in the list

# While Loop
count = 0
while count < 5:
    print(count)
    count += 1  # Increment count

# List Comprehensions (efficient way to create lists)
squares = [i ** 2 for i in range(10)]
print(squares)  # Outputs: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

---

## **Functions:**

```python
# Function Definition
def greet(name):
    return f"Hello, {name}!"

# Calling a Function
print(greet("Alice"))  # Outputs: Hello, Alice!

# Lambda Functions (anonymous function)
square = lambda x: x ** 2
print(square(5))  # Outputs: 25

# Default Arguments in Function
def add(a, b=10):
    return a + b

print(add(5))  # Outputs: 15 (b takes default value)
print(add(5, 7))  # Outputs: 12 (overrides default value)
```

---

## **Classes and Objects:**

```python
# Class Definition
class Person:
    def __init__(self, name, age):
        self.name = name  # Instance variable
        self.age = age    # Instance variable

    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# Creating an Object (Instance of the class)
john = Person("John", 30)
print(john.greet())  # Outputs: Hello, my name is John and I am 30 years old.

# Inheritance Example
class Employee(Person):
    def __init__(self, name, age, employee_id):
        super().__init__(name, age)
        self.employee_id = employee_id

emp = Employee("Alice", 28, "E12345")
print(emp.greet())  # Inherited method, Outputs: Hello, my name is Alice and I am 28 years old.
```

---

## **Common Modules:**

```python
# Importing a Module
import math

# Using a Module
print(math.sqrt(16))  # Outputs: 4.0

# Random Numbers
import random
print(random.randint(1, 10))  # Outputs a random number between 1 and 10

# Datetime
import datetime
print(datetime.datetime.now())  # Outputs the current date and time
```

---

## **File Handling:**

```python
# Opening a File
with open('filename.txt', 'r') as file:
    content = file.read()
    print(content)

# Writing to a File
with open('filename.txt', 'w') as file:
    file.write("Hello, World!")
```

---

## **Error Handling:**

```python
# Try-Except Block
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("This will always run.")
```

---

## **NumPy:**

```python
import numpy as np

# Creating Arrays
arr = np.array([1, 2, 3, 4])
print(arr)

# Array Operations
print(arr + 2)
```

---

## **Pandas:**

```python
import pandas as pd

# Creating a DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35]
}
df = pd.DataFrame(data)
print(df)

# Reading CSV File
df = pd.read_csv('filename.csv')
print(df.head())
```

---

## **Matplotlib:**

```python
import matplotlib.pyplot as plt

# Plotting a Graph
x = [1, 2, 3, 4]
y = [10, 20, 25, 30]
plt.plot(x, y)
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('Sample Plot')
plt.show()
```

---

## **Scikit-learn:**

```python
from sklearn.linear_model import LinearRegression
import numpy as np

# Sample Data
X = np.array([1, 2, 3, 4]).reshape(-1, 1)
y = np.array([2, 3, 5, 7])

# Creating and Training the Model
model = LinearRegression()
model.fit(X, y)

# Making Predictions
predictions = model.predict(X)
print(predictions)
```

