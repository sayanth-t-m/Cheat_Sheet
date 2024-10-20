
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


### **1. List Slicing:**

```python
# List Slicing
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(numbers[2:5])   # Outputs: [3, 4, 5]
print(numbers[:5])    # Outputs: [1, 2, 3, 4, 5]
print(numbers[5:])    # Outputs: [6, 7, 8, 9, 10]
print(numbers[-3:])   # Outputs: [8, 9, 10]
```

### **2. List Methods:**

```python
# List Methods
fruits = ["apple", "banana", "cherry"]
fruits.append("orange")  # Adds "orange" to the list
fruits.remove("banana")  # Removes "banana" from the list
print(fruits)            # Outputs: ['apple', 'cherry', 'orange']
```

### **3. Dictionary Methods:**

```python
# Dictionary Methods
person = {"name": "John", "age": 30, "city": "New York"}
print(person.keys())    # Outputs: dict_keys(['name', 'age', 'city'])
print(person.values())  # Outputs: dict_values(['John', 30, 'New York'])
print(person.items())   # Outputs: dict_items([('name', 'John'), ('age', 30), ('city', 'New York')])
```

### **4. Sorting Lists:**

```python
# Sorting Lists
numbers = [4, 2, 9, 1, 5, 6]
numbers.sort()
print(numbers)  # Outputs: [1, 2, 4, 5, 6, 9]

# Reverse Sorting
numbers.sort(reverse=True)
print(numbers)  # Outputs: [9, 6, 5, 4, 2, 1]
```

### **5. Nested Loops:**

```python
# Nested Loops
for i in range(1, 4):
    for j in range(1, 4):
        print(f"i={i}, j={j}")
```

### **6. List Comprehensions with Condition:**

```python
# List Comprehension with Condition
even_numbers = [x for x in range(10) if x % 2 == 0]
print(even_numbers)  # Outputs: [0, 2, 4, 6, 8]
```

### **7. Recursion:**

```python
# Recursion Example: Factorial
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  # Outputs: 120
```

### **8. Enumerate:**

```python
# Using Enumerate
fruits = ['apple', 'banana', 'cherry']
for index, fruit in enumerate(fruits):
    print(index, fruit)
# Outputs:
# 0 apple
# 1 banana
# 2 cherry
```

### **9. Zip Function:**

```python
# Zip Function
names = ['Alice', 'Bob', 'Charlie']
ages = [25, 30, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old")
# Outputs:
# Alice is 25 years old
# Bob is 30 years old
# Charlie is 35 years old
```

### **10. List Flattening:**

```python
# Flattening a List of Lists
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flat_list = [num for row in matrix for num in row]
print(flat_list)  # Outputs: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```


### **11. Using `map()` Function:**

```python
# Using map() to apply a function to all elements in a list
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)  # Outputs: [1, 4, 9, 16]
```

### **12. Using `filter()` Function:**

```python
# Using filter() to filter out even numbers from a list
numbers = [1, 2, 3, 4, 5, 6]
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # Outputs: [2, 4, 6]
```

### **13. Generators:**

```python
# Generator Example
def my_generator():
    yield 1
    yield 2
    yield 3

for value in my_generator():
    print(value)
# Outputs:
# 1
# 2
# 3
```

### **14. List to Dictionary Conversion:**

```python
# Converting Two Lists into a Dictionary
keys = ['name', 'age', 'city']
values = ['Alice', 25, 'New York']
person = dict(zip(keys, values))
print(person)  # Outputs: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```

### **15. Dictionary Comprehension:**

```python
# Dictionary Comprehension
squares = {x: x ** 2 for x in range(5)}
print(squares)  # Outputs: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

### **16. Set Operations:**

```python
# Set Operations
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

# Union
print(set_a | set_b)  # Outputs: {1, 2, 3, 4, 5, 6}

# Intersection
print(set_a & set_b)  # Outputs: {3, 4}

# Difference
print(set_a - set_b)  # Outputs: {1, 2}
```

### **17. List `extend()` Method:**

```python
# Using extend() to add multiple elements to a list
numbers = [1, 2, 3]
numbers.extend([4, 5, 6])
print(numbers)  # Outputs: [1, 2, 3, 4, 5, 6]
```

### **18. Using `all()` and `any()` Functions:**

```python
# all() and any() examples
numbers = [0, 1, 2, 3]

# all() returns True if all elements are truthy
print(all(numbers))  # Outputs: False (because 0 is considered False)

# any() returns True if any element is truthy
print(any(numbers))  # Outputs: True (because there are non-zero values)
```

### **19. Chaining Comparison Operators:**

```python
# Chaining Comparison Operators
x = 5
print(1 < x < 10)   # Outputs: True
print(10 > x > 3)   # Outputs: True
```

### **20. `itertools` Combinations:**

```python
# Using itertools to generate combinations
import itertools

letters = ['A', 'B', 'C']
combinations = list(itertools.combinations(letters, 2))
print(combinations)  # Outputs: [('A', 'B'), ('A', 'C'), ('B', 'C')]
```

### **21. Swapping Variables:**

```python
# Swapping variables in Python
a, b = 5, 10
a, b = b, a
print(a, b)  # Outputs: 10 5
```

### **22. Unpacking Values:**

```python
# Unpacking values from a list
numbers = [1, 2, 3]
a, b, c = numbers
print(a, b, c)  # Outputs: 1 2 3
```

### **23. Using `collections.Counter`:**

```python
# Using Counter from collections module
from collections import Counter

letters = ['a', 'b', 'a', 'c', 'b', 'a']
letter_count = Counter(letters)
print(letter_count)  # Outputs: Counter({'a': 3, 'b': 2, 'c': 1})
```

### **24. Using `defaultdict`:**

```python
# Using defaultdict from collections
from collections import defaultdict

d = defaultdict(int)
d['apple'] += 1
d['banana'] += 2
print(d)  # Outputs: defaultdict(<class 'int'>, {'apple': 1, 'banana': 2})
```

### **25. List `reverse()` Method:**

```python
# Reversing a list in place
numbers = [1, 2, 3, 4]
numbers.reverse()
print(numbers)  # Outputs: [4, 3, 2, 1]
```

### **26. Using `timeit` for Performance Testing:**

```python
# Using timeit for performance testing
import timeit

time_taken = timeit.timeit('"-".join(str(n) for n in range(100))', number=10000)
print(time_taken)
```