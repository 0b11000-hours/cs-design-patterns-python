# Python


## Data Types

## Numbers

### Max, Min and sum of Numbers

```python
# Max and Min numbers
max_number = max(1, 2, 3)
min_number = min(1, 2, 3)

# Sum of numbers
sum_numbers = sum([1, 2, 3])

# Sum of numbers with start value
sum_numbers = sum([1, 2, 3], 10)

# Maximum integer and minimum integer
max_int = float('inf')
min_int = float('-inf')
print(f'max_int: {max_int}, min_int: {min_int}')

# Current maximum integer in a list
max_int = float('-inf') # Initialize with minimum integer
for number in [i for i in random.sample(range(1, 100), 10)]:
    max_int = max(max_int, number)
print(f'max_int: {max_int}')

# Current minimum integer in a list
min_int = float('inf') # Initialize with maximum integer
for number in [i for i in random.sample(range(1, 100), 10)]:
    min_int = min(min_int, number)
print(f'min_int: {min_int}')

```

### Random Numbers

```python
import random

# Random number between 0 and 1
random_number = random.random()
print(f'random_number: {random_number}')

# Random number between 1 and 10
random_number = random.randint(1, 10)
print(f'random_number: {random_number}')

# Random number between 1 and 10 with step 2 (odd numbers)
random_number = random.randrange(1, 10, 2)
print(f'random_number: {random_number}')

```

### Math Functions

```python
import math
# Absolute value
abs_value = abs(-1)
print(f'abs_value: {abs_value}') # 1

# Power
power_value = pow(2, 3)
print(f'power_value: {power_value}') # 8

# Square root
sqrt_value = math.sqrt(4)
print(f'sqrt_value: {sqrt_value}') # 2.0

# Logarithm
log_value = math.log(100)
print(f'log_value: {log_value}') # 4.605170185988092

# Logarithm base 2
log2_value = math.log2(32)
print(f'log2_value: {log2_value}')  # 5.0

# Logarithm base 10
log10_value = math.log10(1000)
print(f'log10_value: {log10_value}') # 3.0

# Factorial
factorial_value = math.factorial(5)
print(f'factorial_value: {factorial_value}') # 120

```

### Modulus

```python
# Modulus
modulus_value = 10 % 3
print(f'modulus_value: {modulus_value}') # 1

# Modulus with negative numbers
modulus_value = -10 % 3
print(f'modulus_value: {modulus_value}') # 2

# modf returns the fractional and integer parts of a number
fractional, integer = math.modf(10.75)
print(f'fractional: {fractional}, integer: {integer}') # fractional: 0.75, integer: 10.0

# reminder and quotient of a division
reminder, quotient = divmod(10, 3)
print(f'reminder: {reminder}, quotient: {quotient}') # reminder: 1, quotient: 3

# Rotation with modulus operator
rotation = 0 # Initialize rotation
for i in range(8):
    rotation = (rotation + 1) % 4
    print(f'rotation: {rotation}') # 1, 2, 3, 0, 1, 2, 3, 0

```

## Iteration

### Lists Iteration

```python
# Iterating over a list
for item in [1, 2, 3]:
    print(f'item {item}')

# Iterating over a list with index
for index, item in enumerate([1, 2, 3]):
    print(f'index {index}: item {item}')

# Iterating over a list with index and start index
for index, item in enumerate([1, 2, 3], start=1):
    print(f'index {index}: item {item}')

# Iterating over a list in reverse
for item in reversed([1, 2, 3]):
    print(f'item {item}')

# Iterating over a list in reverse with index
for index, item in enumerate(reversed([1, 2, 3])):
    print(f'index {index}: item {item}')

# Iterating over a list in reverse with index and start index
for index, item in enumerate(reversed([1, 2, 3]), start=1):
    print(f'index {index}: item {item}')
```

### Double loop Iteration

```python
# Double loop iteration
for i in range(3):
    for j in range(3):
        print(f'i {i}: j {j}')

# Double loop iteration using single loop
for i, j in [(i, j) for i in range(3) for j in range(3)]:
    print(f'i {i}: j {j}')

# Print first 64 numbers for base 8
counter = [0, 0, 0]
no_of_digits = 3
base = 4
for i in range(66):
    print(f'{counter}')
    for i in range(no_of_digits):
        counter[i] = (counter[i] + 1) % base
        if counter[i] != 0:
            break

```

### Dictionaries Iteration

```python
# Iterating over a dictionary
for key, value in {'a': 1, 'b': 2}.items():
    print(f'key {key}: value {value}')

# Iterating over a dictionary keys
for key in {'a': 1, 'b': 2}.keys():
    print(f'key {key}')

# Iterating over a dictionary values
for value in {'a': 1, 'b': 2}.values():
    print(f'value {value}')

# Iterating over a dictionary with index
for index, (key, value) in enumerate({'a': 1, 'b': 2}.items()):
    print(f'index {index}: key {key}: value {value}')

```

### Sets Iteration

```python
# Iterating over a set
for item in {1, 2, 3}:
    print(f'item {item}')

# Iterating over a set with index
for index, item in enumerate({1, 2, 3}):
    print(f'index {index}: item {item}')
```

## Comprehension

### List Comprehension

```python
# List comprehension
squares = [x**2 for x in range(10)] # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# List comprehension with condition
even_squares = [x**2 for x in range(10) if x % 2 == 0] # [0, 4, 16, 36, 64]

# List comprehension with nested loops
pairs = [(x, y) for x in range(3) for y in range(3)] # [(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2), (2, 0), (2, 1), (2, 2)]
```

## Scratch Pad

- Data Types
- Loops and list comprehension
- Data Structure - Stack and Queue
- Dictonary
- Class and Introspection
- Math
  - step function
  - modulous
  - factorial and fibonacci
- Memonization or dynamic programming
- Greedy
