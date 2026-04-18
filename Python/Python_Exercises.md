# 🐍 Python Programming Exercises

A structured collection of Python programming exercises organized by difficulty level. Each exercise includes a problem description, hints, and a solution.

---

## 📋 Table of Contents

- [Level Guide](#-level-guide)
- [Level 1 — Beginner](#-level-1--beginner)
- [Level 2 — Intermediate](#-level-2--intermediate)
- [Level 3 — Advanced](#-level-3--advanced)
- [Functions & Classes](#-functions--classes)
- [Data Structures](#-data-structures)
- [Object-Oriented Programming](#-object-oriented-programming)
- [Exception Handling](#-exception-handling)
- [Regular Expressions](#-regular-expressions)
- [Functional Programming](#-functional-programming)
- [Generators & Iterators](#-generators--iterators)
- [Random & Math Modules](#-random--math-modules)
- [Miscellaneous](#-miscellaneous)

---

## 📊 Level Guide

| Level | Label | Description |
|-------|-------|-------------|
| **1** | Beginner | Just completed an introductory Python course. Can solve problems with 1–2 Python classes or functions. Answers can typically be found in textbooks. |
| **2** | Intermediate | Has a programming background. Can solve problems involving 3+ Python classes or functions. Answers cannot be directly found in textbooks. |
| **3** | Advanced | Uses Python to solve complex problems with rich libraries, data structures, and algorithms. Involves multiple standard packages and advanced techniques. |

---

## 🟢 Level 1 — Beginner

---

### Q1 — Divisible by 7 but not by 5

**Question:**
Find all numbers between 2000 and 3200 (inclusive) which are divisible by 7 but not a multiple of 5. Print the numbers in a comma-separated sequence on a single line.

**Hints:**
- Use `range(begin, end)` method

<details>
<summary>💡 View Solution</summary>

```python
l = []
for i in range(2000, 3201):
    if (i % 7 == 0) and (i % 5 != 0):
        l.append(str(i))

print(','.join(l))
```
</details>

---

### Q2 — Factorial of a Number

**Question:**
Write a program to compute the factorial of a given number.

**Example:**
```
Input:  8
Output: 40320
```

**Hints:**
- Use console input

<details>
<summary>💡 View Solution</summary>

```python
def fact(x):
    if x == 0:
        return 1
    return x * fact(x - 1)

x = int(input())
print(fact(x))
```
</details>

---

### Q3 — Dictionary of Squares

**Question:**
With a given integer `n`, generate a dictionary that contains `(i, i*i)` for integers between 1 and n (inclusive). Print the dictionary.

**Example:**
```
Input:  8
Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64}
```

**Hints:**
- Use `dict()`

<details>
<summary>💡 View Solution</summary>

```python
n = int(input())
d = dict()
for i in range(1, n + 1):
    d[i] = i * i

print(d)
```
</details>

---

### Q4 — List and Tuple from Comma-Separated Input

**Question:**
Accept a sequence of comma-separated numbers from the console and generate both a list and a tuple containing every number.

**Example:**
```
Input:  34,67,55,33,12,98
Output: ['34', '67', '55', '33', '12', '98']
        ('34', '67', '55', '33', '12', '98')
```

**Hints:**
- `tuple()` can convert a list to a tuple

<details>
<summary>💡 View Solution</summary>

```python
values = input()
l = values.split(",")
t = tuple(l)
print(l)
print(t)
```
</details>

---

### Q5 — Class with getString and printString

**Question:**
Define a class with at least two methods:
- `getString`: to get a string from console input
- `printString`: to print the string in upper case

Include a simple test.

**Hints:**
- Use `__init__` to initialise instance parameters

<details>
<summary>💡 View Solution</summary>

```python
class InputOutString(object):
    def __init__(self):
        self.s = ""

    def getString(self):
        self.s = input()

    def printString(self):
        print(self.s.upper())

strObj = InputOutString()
strObj.getString()
strObj.printString()
```
</details>

---

### Q23 — Square Value of a Number

**Question:**
Write a method that calculates and returns the square value of a number.

**Hints:**
- Use the `**` operator

<details>
<summary>💡 View Solution</summary>

```python
def square(num):
    return num ** 2

print(square(2))
print(square(3))
```
</details>

---

### Q24 — Built-in Function Documentation

**Question:**
Print the built-in documentation for `abs()`, `int()`, and `input()`. Also add documentation for your own function.

**Hints:**
- Use `__doc__` to access documentation strings

<details>
<summary>💡 View Solution</summary>

```python
print(abs.__doc__)
print(int.__doc__)

def square(num):
    '''Return the square value of the input number.

    The input number must be an integer.
    '''
    return num ** 2

print(square(2))
print(square.__doc__)
```
</details>

---

### Q25 — Class Parameters vs Instance Parameters

**Question:**
Define a class that has both a class parameter and an instance parameter with the same name.

**Hints:**
- Define instance parameters inside the `__init__` method

<details>
<summary>💡 View Solution</summary>

```python
class Person:
    name = "Person"  # class parameter

    def __init__(self, name=None):
        self.name = name  # instance parameter

jeffrey = Person("Jeffrey")
print("%s name is %s" % (Person.name, jeffrey.name))

nico = Person()
nico.name = "Nico"
print("%s name is %s" % (Person.name, nico.name))
```
</details>

---

## 🟡 Level 2 — Intermediate

---

### Q6 — Square Root Formula

**Question:**
Calculate and print the value of `Q = sqrt((2 * C * D) / H)` where C=50, H=30, and D is a variable from comma-separated console input. Round results to nearest integer.

**Example:**
```
Input:  100,150,180
Output: 18,22,24
```

<details>
<summary>💡 View Solution</summary>

```python
import math

c = 50
h = 30
value = []
items = [x for x in input().split(',')]
for d in items:
    value.append(str(int(round(math.sqrt(2 * c * float(d) / h)))))

print(','.join(value))
```
</details>

---

### Q7 — 2D Array Generation

**Question:**
Take 2 digits X and Y as input and generate a 2D array where the element at row `i`, column `j` equals `i*j`.

**Example:**
```
Input:  3,5
Output: [[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8]]
```

<details>
<summary>💡 View Solution</summary>

```python
input_str = input()
dimensions = [int(x) for x in input_str.split(',')]
rowNum = dimensions[0]
colNum = dimensions[1]
multilist = [[0 for col in range(colNum)] for row in range(rowNum)]

for row in range(rowNum):
    for col in range(colNum):
        multilist[row][col] = row * col

print(multilist)
```
</details>

---

### Q8 — Sort Words Alphabetically

**Question:**
Accept a comma-separated sequence of words and print them sorted alphabetically.

**Example:**
```
Input:  without,hello,bag,world
Output: bag,hello,without,world
```

<details>
<summary>💡 View Solution</summary>

```python
items = [x for x in input().split(',')]
items.sort()
print(','.join(items))
```
</details>

---

### Q9 — Capitalize All Lines

**Question:**
Accept a sequence of lines as input and print them with all characters capitalized.

**Example:**
```
Input:  Hello world
        Practice makes perfect
Output: HELLO WORLD
        PRACTICE MAKES PERFECT
```

<details>
<summary>💡 View Solution</summary>

```python
lines = []
while True:
    s = input()
    if s:
        lines.append(s.upper())
    else:
        break

for sentence in lines:
    print(sentence)
```
</details>

---

### Q10 — Remove Duplicates and Sort

**Question:**
Accept whitespace-separated words, remove all duplicates, and print sorted alphanumerically.

**Example:**
```
Input:  hello world and practice makes perfect and hello world again
Output: again and hello makes perfect practice world
```

**Hints:**
- Use `set` to remove duplicates, then `sorted()` to sort

<details>
<summary>💡 View Solution</summary>

```python
s = input()
words = [word for word in s.split(" ")]
print(" ".join(sorted(list(set(words)))))
```
</details>

---

### Q11 — Binary Numbers Divisible by 5

**Question:**
Accept comma-separated 4-digit binary numbers and print those divisible by 5.

**Example:**
```
Input:  0100,0011,1010,1001
Output: 1010
```

<details>
<summary>💡 View Solution</summary>

```python
value = []
items = [x for x in input().split(',')]
for p in items:
    intp = int(p, 2)
    if not intp % 5:
        value.append(p)

print(','.join(value))
```
</details>

---

### Q12 — Numbers with All Even Digits

**Question:**
Find all numbers between 1000 and 3000 (inclusive) where every digit is an even number. Print in a comma-separated sequence.

<details>
<summary>💡 View Solution</summary>

```python
values = []
for i in range(1000, 3001):
    s = str(i)
    if (int(s[0]) % 2 == 0) and (int(s[1]) % 2 == 0) and (int(s[2]) % 2 == 0) and (int(s[3]) % 2 == 0):
        values.append(s)
print(",".join(values))
```
</details>

---

### Q13 — Count Letters and Digits

**Question:**
Accept a sentence and count the number of letters and digits.

**Example:**
```
Input:  hello world! 123
Output: LETTERS 10
        DIGITS 3
```

<details>
<summary>💡 View Solution</summary>

```python
s = input()
d = {"DIGITS": 0, "LETTERS": 0}
for c in s:
    if c.isdigit():
        d["DIGITS"] += 1
    elif c.isalpha():
        d["LETTERS"] += 1

print("LETTERS", d["LETTERS"])
print("DIGITS", d["DIGITS"])
```
</details>

---

### Q14 — Count Upper and Lower Case Letters

**Question:**
Accept a sentence and count the number of upper case and lower case letters.

**Example:**
```
Input:  Hello world!
Output: UPPER CASE 1
        LOWER CASE 9
```

<details>
<summary>💡 View Solution</summary>

```python
s = input()
d = {"UPPER CASE": 0, "LOWER CASE": 0}
for c in s:
    if c.isupper():
        d["UPPER CASE"] += 1
    elif c.islower():
        d["LOWER CASE"] += 1

print("UPPER CASE", d["UPPER CASE"])
print("LOWER CASE", d["LOWER CASE"])
```
</details>

---

### Q15 — a + aa + aaa + aaaa

**Question:**
Compute the value of `a + aa + aaa + aaaa` with a given digit `a`.

**Example:**
```
Input:  9
Output: 11106
```

<details>
<summary>💡 View Solution</summary>

```python
a = input()
n1 = int("%s" % a)
n2 = int("%s%s" % (a, a))
n3 = int("%s%s%s" % (a, a, a))
n4 = int("%s%s%s%s" % (a, a, a, a))
print(n1 + n2 + n3 + n4)
```
</details>

---

### Q16 — Filter Odd Numbers from List

**Question:**
Use list comprehension to filter odd numbers from a comma-separated input list.

**Example:**
```
Input:  1,2,3,4,5,6,7,8,9
Output: 1,3,5,7,9
```

<details>
<summary>💡 View Solution</summary>

```python
values = input()
numbers = [x for x in values.split(",") if int(x) % 2 != 0]
print(",".join(numbers))
```
</details>

---

### Q17 — Bank Account Transaction Log

**Question:**
Compute the net balance of a bank account from a transaction log. `D` = Deposit, `W` = Withdrawal.

**Example:**
```
Input:  D 300
        D 300
        W 200
        D 100
Output: 500
```

<details>
<summary>💡 View Solution</summary>

```python
netAmount = 0
while True:
    s = input()
    if not s:
        break
    values = s.split(" ")
    operation = values[0]
    amount = int(values[1])
    if operation == "D":
        netAmount += amount
    elif operation == "W":
        netAmount -= amount

print(netAmount)
```
</details>

---

## 🔴 Level 3 — Advanced

---

### Q18 — Password Validator

**Question:**
Check the validity of passwords from a comma-separated sequence. Valid passwords must:
1. Contain at least one lowercase letter `[a-z]`
2. Contain at least one digit `[0-9]`
3. Contain at least one uppercase letter `[A-Z]`
4. Contain at least one special character `[$#@]`
5. Be between 6 and 12 characters long

**Example:**
```
Input:  ABd1234@1,a F1#,2w3E*,2We3345
Output: ABd1234@1
```

<details>
<summary>💡 View Solution</summary>

```python
import re

value = []
items = [x for x in input().split(',')]
for p in items:
    if len(p) < 6 or len(p) > 12:
        continue
    if not re.search("[a-z]", p):
        continue
    elif not re.search("[0-9]", p):
        continue
    elif not re.search("[A-Z]", p):
        continue
    elif not re.search("[$#@]", p):
        continue
    elif re.search("\s", p):
        continue
    value.append(p)

print(",".join(value))
```
</details>

---

### Q19 — Sort Tuples by Multiple Keys

**Question:**
Sort `(name, age, height)` tuples by name first, then age, then height.

**Example:**
```
Input:  Tom,19,80 / John,20,90 / Jony,17,91 / Jony,17,93 / Json,21,85
Output: [('John', '20', '90'), ('Jony', '17', '91'), ('Jony', '17', '93'), ('Json', '21', '85'), ('Tom', '19', '80')]
```

**Hints:**
- Use `itemgetter` for multiple sort keys

<details>
<summary>💡 View Solution</summary>

```python
from operator import itemgetter

l = []
while True:
    s = input()
    if not s:
        break
    l.append(tuple(s.split(",")))

print(sorted(l, key=itemgetter(0, 1, 2)))
```
</details>

---

### Q20 — Generator for Multiples of 7

**Question:**
Define a generator that yields numbers divisible by 7 between 0 and n.

**Hints:**
- Use `yield`

<details>
<summary>💡 View Solution</summary>

```python
def putNumbers(n):
    i = 0
    while i < n:
        j = i
        i += 1
        if j % 7 == 0:
            yield j

for i in putNumbers(100):
    print(i)
```
</details>

---

### Q21 — Robot Distance from Origin

**Question:**
A robot starts at `(0,0)` and moves based on commands (UP, DOWN, LEFT, RIGHT with steps). Compute the distance from origin after all moves. Print the nearest integer if result is a float.

**Example:**
```
Input:  UP 5 / DOWN 3 / LEFT 3 / RIGHT 2
Output: 2
```

<details>
<summary>💡 View Solution</summary>

```python
import math

pos = [0, 0]
while True:
    s = input()
    if not s:
        break
    movement = s.split(" ")
    direction = movement[0]
    steps = int(movement[1])
    if direction == "UP":
        pos[0] += steps
    elif direction == "DOWN":
        pos[0] -= steps
    elif direction == "LEFT":
        pos[1] -= steps
    elif direction == "RIGHT":
        pos[1] += steps

print(int(round(math.sqrt(pos[1] ** 2 + pos[0] ** 2))))
```
</details>

---

### Q22 — Word Frequency Counter

**Question:**
Compute the frequency of words from input and print sorted alphanumerically.

**Example:**
```
Input:  New to Python or choosing between Python 2 and Python 3? Read Python 2 or Python 3.
Output: 2:2 / 3.:1 / 3?:1 / New:1 / Python:5 / Read:1 / and:1 / ...
```

<details>
<summary>💡 View Solution</summary>

```python
freq = {}
line = input()
for word in line.split():
    freq[word] = freq.get(word, 0) + 1

words = sorted(freq.keys())
for w in words:
    print("%s:%d" % (w, freq[w]))
```
</details>

---

## 🔧 Functions & Classes

---

### Compute Sum of Two Numbers

**Question:** Define a function that computes the sum of two numbers.

<details>
<summary>💡 View Solution</summary>

```python
def SumFunction(number1, number2):
    return number1 + number2

print(SumFunction(1, 2))
```
</details>

---

### Convert Integer to String

**Question:** Define a function that converts an integer to a string and prints it.

<details>
<summary>💡 View Solution</summary>

```python
def printValue(n):
    print(str(n))

printValue(3)
```
</details>

---

### Sum of Two String Integers

**Question:** Define a function that receives two numbers as strings, computes their sum, and prints it.

<details>
<summary>💡 View Solution</summary>

```python
def printValue(s1, s2):
    print(int(s1) + int(s2))

printValue("3", "4")  # Output: 7
```
</details>

---

### Concatenate Two Strings

**Question:** Define a function that concatenates two strings and prints the result.

<details>
<summary>💡 View Solution</summary>

```python
def printValue(s1, s2):
    print(s1 + s2)

printValue("Hello", " World")  # Output: Hello World
```
</details>

---

### Print Longest String

**Question:** Define a function that prints the longer of two strings. If equal length, print both.

<details>
<summary>💡 View Solution</summary>

```python
def printValue(s1, s2):
    if len(s1) > len(s2):
        print(s1)
    elif len(s2) > len(s1):
        print(s2)
    else:
        print(s1)
        print(s2)

printValue("one", "three")
```
</details>

---

### Even or Odd Checker

**Question:** Define a function that prints whether a number is even or odd.

<details>
<summary>💡 View Solution</summary>

```python
def checkValue(n):
    if n % 2 == 0:
        print("It is an even number")
    else:
        print("It is an odd number")

checkValue(7)
```
</details>

---

### Dictionary with Squared Keys (1–3)

**Question:** Print a dictionary where keys are 1–3 and values are their squares.

<details>
<summary>💡 View Solution</summary>

```python
def printDict():
    d = dict()
    d[1] = 1
    d[2] = 2 ** 2
    d[3] = 3 ** 2
    print(d)

printDict()
```
</details>

---

### Dictionary with Squared Keys (1–20)

**Question:** Print a dictionary where keys are 1–20 and values are their squares.

<details>
<summary>💡 View Solution</summary>

```python
def printDict():
    d = dict()
    for i in range(1, 21):
        d[i] = i ** 2
    print(d)

printDict()
```
</details>

---

### Print Only Values from Squared Dict

**Question:** Generate a squared dictionary (keys 1–20) and print only the values.

<details>
<summary>💡 View Solution</summary>

```python
def printDict():
    d = dict()
    for i in range(1, 21):
        d[i] = i ** 2
    for (k, v) in d.items():
        print(v)

printDict()
```
</details>

---

### Print Only Keys from Squared Dict

**Question:** Generate a squared dictionary (keys 1–20) and print only the keys.

<details>
<summary>💡 View Solution</summary>

```python
def printDict():
    d = dict()
    for i in range(1, 21):
        d[i] = i ** 2
    for k in d.keys():
        print(k)

printDict()
```
</details>

---

### List of Squares (1–20)

**Question:** Generate and print a list of squares from 1 to 20.

<details>
<summary>💡 View Solution</summary>

```python
def printList():
    li = list()
    for i in range(1, 21):
        li.append(i ** 2)
    print(li)

printList()
```
</details>

---

### First 5 Elements of Squared List

**Question:** Generate squares from 1–20 and print only the first 5 elements.

<details>
<summary>💡 View Solution</summary>

```python
def printList():
    li = list()
    for i in range(1, 21):
        li.append(i ** 2)
    print(li[:5])

printList()
```
</details>

---

### Last 5 Elements of Squared List

**Question:** Generate squares from 1–20 and print only the last 5 elements.

<details>
<summary>💡 View Solution</summary>

```python
def printList():
    li = list()
    for i in range(1, 21):
        li.append(i ** 2)
    print(li[-5:])

printList()
```
</details>

---

### All Except First 5 Elements

**Question:** Generate squares from 1–20 and print all except the first 5 elements.

<details>
<summary>💡 View Solution</summary>

```python
def printList():
    li = list()
    for i in range(1, 21):
        li.append(i ** 2)
    print(li[5:])

printList()
```
</details>

---

### Tuple of Squares (1–20)

**Question:** Generate and print a tuple of squares from 1 to 20.

<details>
<summary>💡 View Solution</summary>

```python
def printTuple():
    li = list()
    for i in range(1, 21):
        li.append(i ** 2)
    print(tuple(li))

printTuple()
```
</details>

---

## 🗂️ Data Structures

---

### Tuple — First and Last Half

**Question:** With `(1,2,3,4,5,6,7,8,9,10)`, print the first half on one line and the last half on another.

<details>
<summary>💡 View Solution</summary>

```python
tp = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
tp1 = tp[:5]
tp2 = tp[5:]
print(tp1)
print(tp2)
```
</details>

---

### Tuple — Even Numbers Only

**Question:** From `(1,2,3,4,5,6,7,8,9,10)`, generate a new tuple with only even numbers.

<details>
<summary>💡 View Solution</summary>

```python
tp = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
li = [x for x in tp if x % 2 == 0]
tp2 = tuple(li)
print(tp2)
```
</details>

---

### Yes/No String Check

**Question:** Accept a string and print "Yes" if it equals "yes", "YES", or "Yes", otherwise print "No".

<details>
<summary>💡 View Solution</summary>

```python
s = input()
if s in ("yes", "YES", "Yes"):
    print("Yes")
else:
    print("No")
```
</details>

---

### Shuffle a List

**Question:** Shuffle and print the list `[3, 6, 7, 8]`.

**Hints:** Use `shuffle()` from the `random` module.

<details>
<summary>💡 View Solution</summary>

```python
from random import shuffle

li = [3, 6, 7, 8]
shuffle(li)
print(li)
```
</details>

---

### Generate All Sentences (Subjects × Verbs × Objects)

**Question:** Generate all sentences where subject ∈ `["I", "You"]`, verb ∈ `["Play", "Love"]`, object ∈ `["Hockey", "Football"]`.

<details>
<summary>💡 View Solution</summary>

```python
subjects = ["I", "You"]
verbs = ["Play", "Love"]
objects = ["Hockey", "Football"]
for i in range(len(subjects)):
    for j in range(len(verbs)):
        for k in range(len(objects)):
            sentence = "%s %s %s." % (subjects[i], verbs[j], objects[k])
            print(sentence)
```
</details>

---

### Remove Even Numbers from List

**Question:** Print `[5, 6, 77, 45, 22, 12, 24]` after removing all even numbers.

<details>
<summary>💡 View Solution</summary>

```python
li = [5, 6, 77, 45, 22, 12, 24]
li = [x for x in li if x % 2 != 0]
print(li)
```
</details>

---

### Remove Numbers Divisible by 5 and 7

**Question:** Print `[12,24,35,70,88,120,155]` after removing numbers divisible by both 5 and 7.

<details>
<summary>💡 View Solution</summary>

```python
li = [12, 24, 35, 70, 88, 120, 155]
li = [x for x in li if x % 5 != 0 and x % 7 != 0]
print(li)
```
</details>

---

### Remove Elements at Even Indexes

**Question:** Print `[12,24,35,70,88,120,155]` after removing elements at indexes 0, 2, 4, 6.

**Hints:** Use `enumerate()` to get index-value pairs.

<details>
<summary>💡 View Solution</summary>

```python
li = [12, 24, 35, 70, 88, 120, 155]
li = [x for (i, x) in enumerate(li) if i % 2 != 0]
print(li)
```
</details>

---

### 3D Array of Zeros

**Question:** Using list comprehension, generate a 3×5×8 3D array where every element is 0.

<details>
<summary>💡 View Solution</summary>

```python
array = [[[0 for col in range(8)] for col in range(5)] for row in range(3)]
print(array)
```
</details>

---

### Remove Specific Indexes

**Question:** Print `[12,24,35,70,88,120,155]` after removing elements at indexes 0, 4, and 5.

<details>
<summary>💡 View Solution</summary>

```python
li = [12, 24, 35, 70, 88, 120, 155]
li = [x for (i, x) in enumerate(li) if i not in (0, 4, 5)]
print(li)
```
</details>

---

### Remove a Specific Value

**Question:** Print `[12,24,35,24,88,120,155]` after removing all occurrences of the value 24.

<details>
<summary>💡 View Solution</summary>

```python
li = [12, 24, 35, 24, 88, 120, 155]
li = [x for x in li if x != 24]
print(li)
```
</details>

---

### Intersection of Two Lists

**Question:** Given `[1,3,6,78,35,55]` and `[12,24,35,24,88,120,155]`, create a list with their intersection.

**Hints:** Use `set()` and `&=` for intersection.

<details>
<summary>💡 View Solution</summary>

```python
set1 = set([1, 3, 6, 78, 35, 55])
set2 = set([12, 24, 35, 24, 88, 120, 155])
set1 &= set2
li = list(set1)
print(li)
```
</details>

---

### Remove Duplicates Preserving Order

**Question:** Print `[12,24,35,24,88,120,155,88,120,155]` after removing duplicate values while preserving original order.

<details>
<summary>💡 View Solution</summary>

```python
def removeDuplicate(li):
    newli = []
    seen = set()
    for item in li:
        if item not in seen:
            seen.add(item)
            newli.append(item)
    return newli

li = [12, 24, 35, 24, 88, 120, 155, 88, 120, 155]
print(removeDuplicate(li))
```
</details>

---

## 🏛️ Object-Oriented Programming

---

### Static Method

**Question:** Define a class `American` with a static method `printNationality`.

<details>
<summary>💡 View Solution</summary>

```python
class American(object):
    @staticmethod
    def printNationality():
        print("America")

anAmerican = American()
anAmerican.printNationality()
American.printNationality()
```
</details>

---

### Subclass — NewYorker

**Question:** Define a class `American` and its subclass `NewYorker`.

<details>
<summary>💡 View Solution</summary>

```python
class American(object):
    pass

class NewYorker(American):
    pass

anAmerican = American()
aNewYorker = NewYorker()
print(anAmerican)
print(aNewYorker)
```
</details>

---

### Circle Class with Area Method

**Question:** Define a `Circle` class that can be constructed with a radius and has a method to compute the area.

<details>
<summary>💡 View Solution</summary>

```python
class Circle(object):
    def __init__(self, r):
        self.radius = r

    def area(self):
        return self.radius ** 2 * 3.14

aCircle = Circle(2)
print(aCircle.area())
```
</details>

---

### Rectangle Class with Area Method

**Question:** Define a `Rectangle` class constructed with length and width, and compute the area.

<details>
<summary>💡 View Solution</summary>

```python
class Rectangle(object):
    def __init__(self, l, w):
        self.length = l
        self.width = w

    def area(self):
        return self.length * self.width

aRectangle = Rectangle(2, 10)
print(aRectangle.area())
```
</details>

---

### Shape and Square (Inheritance + Override)

**Question:** Define a `Shape` class with area=0 and a `Square` subclass that overrides area.

<details>
<summary>💡 View Solution</summary>

```python
class Shape(object):
    def __init__(self):
        pass

    def area(self):
        return 0

class Square(Shape):
    def __init__(self, l):
        Shape.__init__(self)
        self.length = l

    def area(self):
        return self.length * self.length

aSquare = Square(3)
print(aSquare.area())
```
</details>

---

### Person, Male, Female — getGender

**Question:** Define a `Person` class and child classes `Male` and `Female`, each with a `getGender()` method.

<details>
<summary>💡 View Solution</summary>

```python
class Person(object):
    def getGender(self):
        return "Unknown"

class Male(Person):
    def getGender(self):
        return "Male"

class Female(Person):
    def getGender(self):
        return "Female"

aMale = Male()
aFemale = Female()
print(aMale.getGender())
print(aFemale.getGender())
```
</details>

---

## ⚠️ Exception Handling

---

### Raise a RuntimeError

**Question:** Raise a `RuntimeError` exception with a message.

<details>
<summary>💡 View Solution</summary>

```python
raise RuntimeError('something wrong')
```
</details>

---

### Try/Except for Division by Zero

**Question:** Write a function to compute `5/0` and use try/except to catch the exception.

<details>
<summary>💡 View Solution</summary>

```python
def throws():
    return 5 / 0

try:
    throws()
except ZeroDivisionError:
    print("division by zero!")
except Exception as err:
    print('Caught an exception')
finally:
    print('In finally block for cleanup')
```
</details>

---

### Define a Custom Exception

**Question:** Define a custom exception class that accepts a string message.

<details>
<summary>💡 View Solution</summary>

```python
class MyError(Exception):
    """My own exception class.

    Attributes:
        msg -- explanation of the error
    """

    def __init__(self, msg):
        self.msg = msg

error = MyError("something wrong")
```
</details>

---

## 🔍 Regular Expressions

---

### Extract Email Username

**Question:** Extract and print the username from an email in `username@companyname.com` format.

**Example:**
```
Input:  john@google.com
Output: john
```

<details>
<summary>💡 View Solution</summary>

```python
import re

emailAddress = input()
pat2 = "(\w+)@((\w+\.)+(com))"
r2 = re.match(pat2, emailAddress)
print(r2.group(1))
```
</details>

---

### Extract Email Company Name

**Question:** Extract and print the company name from an email in `username@companyname.com` format.

**Example:**
```
Input:  john@google.com
Output: google
```

<details>
<summary>💡 View Solution</summary>

```python
import re

emailAddress = input()
pat2 = "(\w+)@(\w+)\.(com)"
r2 = re.match(pat2, emailAddress)
print(r2.group(2))
```
</details>

---

### Extract Digits from Sentence

**Question:** Print all words composed of digits only from a whitespace-separated sentence.

**Example:**
```
Input:  2 cats and 3 dogs.
Output: ['2', '3']
```

<details>
<summary>💡 View Solution</summary>

```python
import re

s = input()
print(re.findall("\d+", s))
```
</details>

---

### Character Frequency Counter

**Question:** Count and print the frequency of each character in a string.

**Example:**
```
Input:  abcdefgabc
Output: a,2 / b,2 / c,2 / d,1 / e,1 / f,1 / g,1
```

<details>
<summary>💡 View Solution</summary>

```python
dic = {}
s = input()
for c in s:
    dic[c] = dic.get(c, 0) + 1
print('\n'.join(['%s,%s' % (k, v) for k, v in dic.items()]))
```
</details>

---

### Reverse a String

**Question:** Accept a string and print it in reverse order.

**Example:**
```
Input:  rise to vote sir
Output: ris etov ot esir
```

<details>
<summary>💡 View Solution</summary>

```python
s = input()
s = s[::-1]
print(s)
```
</details>

---

### Print Even-Index Characters

**Question:** Accept a string and print only the characters at even indexes.

**Example:**
```
Input:  H1e2l3l4o5w6o7r8l9d
Output: Helloworld
```

<details>
<summary>💡 View Solution</summary>

```python
s = input()
s = s[::2]
print(s)
```
</details>

---

### Print All Permutations

**Question:** Print all permutations of `[1, 2, 3]`.

<details>
<summary>💡 View Solution</summary>

```python
import itertools

print(list(itertools.permutations([1, 2, 3])))
```
</details>

---

## ⚙️ Functional Programming

---

### Filter Even Numbers with filter()

**Question:** Use `filter()` to keep only even numbers from `[1,2,3,4,5,6,7,8,9,10]`.

<details>
<summary>💡 View Solution</summary>

```python
li = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evenNumbers = list(filter(lambda x: x % 2 == 0, li))
print(evenNumbers)
```
</details>

---

### Square Numbers with map()

**Question:** Use `map()` to square every element in `[1,2,3,4,5,6,7,8,9,10]`.

<details>
<summary>💡 View Solution</summary>

```python
li = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
squaredNumbers = list(map(lambda x: x ** 2, li))
print(squaredNumbers)
```
</details>

---

### Square of Even Numbers with map() + filter()

**Question:** Use `map()` and `filter()` to produce a list of squares of even numbers in `[1–10]`.

<details>
<summary>💡 View Solution</summary>

```python
li = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evenSquared = list(map(lambda x: x ** 2, filter(lambda x: x % 2 == 0, li)))
print(evenSquared)
```
</details>

---

### Even Numbers 1–20 with filter()

**Question:** Use `filter()` to generate a list of even numbers between 1 and 20.

<details>
<summary>💡 View Solution</summary>

```python
evenNumbers = list(filter(lambda x: x % 2 == 0, range(1, 21)))
print(evenNumbers)
```
</details>

---

### Squares 1–20 with map()

**Question:** Use `map()` to generate a list of squares for numbers 1 to 20.

<details>
<summary>💡 View Solution</summary>

```python
squaredNumbers = list(map(lambda x: x ** 2, range(1, 21)))
print(squaredNumbers)
```
</details>

---

## 🔄 Generators & Iterators

---

### Fibonacci Sequence — Recursive

**Question:** Compute `f(n)` using the Fibonacci formula recursively.

**Formula:**
```
f(0) = 0, f(1) = 1, f(n) = f(n-1) + f(n-2)
```

**Example:**
```
Input:  7
Output: 13
```

<details>
<summary>💡 View Solution</summary>

```python
def f(n):
    if n == 0: return 0
    elif n == 1: return 1
    else: return f(n - 1) + f(n - 2)

n = int(input())
print(f(n))
```
</details>

---

### Fibonacci Sequence — Comma Separated

**Question:** Print the Fibonacci sequence up to n in comma-separated form.

**Example:**
```
Input:  7
Output: 0,1,1,2,3,5,8,13
```

<details>
<summary>💡 View Solution</summary>

```python
def f(n):
    if n == 0: return 0
    elif n == 1: return 1
    else: return f(n - 1) + f(n - 2)

n = int(input())
values = [str(f(x)) for x in range(0, n + 1)]
print(",".join(values))
```
</details>

---

### Compute f(n) = f(n-1) + 100

**Question:** Compute `f(n) = f(n-1) + 100` with `f(0) = 0`.

**Example:**
```
Input:  5
Output: 500
```

<details>
<summary>💡 View Solution</summary>

```python
def f(n):
    if n == 0:
        return 0
    else:
        return f(n - 1) + 100

n = int(input())
print(f(n))
```
</details>

---

### Compute 1/2 + 2/3 + ... + n/(n+1)

**Question:** Compute the sum `1/2 + 2/3 + 3/4 + ... + n/(n+1)` for a given n.

**Example:**
```
Input:  5
Output: 3.55
```

<details>
<summary>💡 View Solution</summary>

```python
n = int(input())
total = 0.0
for i in range(1, n + 1):
    total += float(i) / (i + 1)
print(total)
```
</details>

---

### Even Number Generator

**Question:** Use a generator to print even numbers between 0 and n in comma-separated form.

**Example:**
```
Input:  10
Output: 0,2,4,6,8,10
```

<details>
<summary>💡 View Solution</summary>

```python
def EvenGenerator(n):
    i = 0
    while i <= n:
        if i % 2 == 0:
            yield i
        i += 1

n = int(input())
values = [str(i) for i in EvenGenerator(n)]
print(",".join(values))
```
</details>

---

### Generator — Divisible by 5 and 7

**Question:** Use a generator to print numbers divisible by both 5 and 7 between 0 and n.

**Example:**
```
Input:  100
Output: 0,35,70
```

<details>
<summary>💡 View Solution</summary>

```python
def NumGenerator(n):
    for i in range(n + 1):
        if i % 5 == 0 and i % 7 == 0:
            yield i

n = int(input())
values = [str(i) for i in NumGenerator(n)]
print(",".join(values))
```
</details>

---

### Assert All Even

**Question:** Write assert statements to verify that every number in `[2, 4, 6, 8]` is even.

<details>
<summary>💡 View Solution</summary>

```python
li = [2, 4, 6, 8]
for i in li:
    assert i % 2 == 0
```
</details>

---

## 🎲 Random & Math Modules

---

### Random Float between 10 and 100

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.random() * 100)
```
</details>

---

### Random Float between 5 and 95

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.random() * 90 + 5)
```
</details>

---

### Random Even Number (0–10)

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.choice([i for i in range(11) if i % 2 == 0]))
```
</details>

---

### Random Number Divisible by 5 and 7

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.choice([i for i in range(201) if i % 5 == 0 and i % 7 == 0]))
```
</details>

---

### List of 5 Random Numbers (100–200)

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.sample(range(100, 201), 5))
```
</details>

---

### List of 5 Random Even Numbers (100–200)

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.sample([i for i in range(100, 201) if i % 2 == 0], 5))
```
</details>

---

### List of 5 Numbers Divisible by 5 and 7 (1–1000)

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.sample([i for i in range(1, 1001) if i % 5 == 0 and i % 7 == 0], 5))
```
</details>

---

### Random Integer between 7 and 15

<details>
<summary>💡 View Solution</summary>

```python
import random
print(random.randrange(7, 16))
```
</details>

---

## 🔀 Miscellaneous

---

### Compress and Decompress a String

**Question:** Compress and decompress the string `"hello world!hello world!hello world!hello world!"`.

<details>
<summary>💡 View Solution</summary>

```python
import zlib

s = b'hello world!hello world!hello world!hello world!'
t = zlib.compress(s)
print(t)
print(zlib.decompress(t))
```
</details>

---

### Measure Execution Time

**Question:** Print the running time of executing `"1+1"` for 100 times.

<details>
<summary>💡 View Solution</summary>

```python
from timeit import Timer

t = Timer("for i in range(100): 1+1")
print(t.timeit())
```
</details>

---

### Evaluate a Math Expression

**Question:** Accept a basic math expression from console and print the result.

**Example:**
```
Input:  35+3
Output: 38
```

<details>
<summary>💡 View Solution</summary>

```python
expression = input()
print(eval(expression))
```
</details>

---

### Binary Search

**Question:** Write a binary search function that returns the index of an element in a sorted list, or `-1` if not found.

<details>
<summary>💡 View Solution</summary>

```python
import math

def bin_search(li, element):
    bottom = 0
    top = len(li) - 1
    index = -1
    while top >= bottom and index == -1:
        mid = int(math.floor((top + bottom) / 2.0))
        if li[mid] == element:
            index = mid
        elif li[mid] > element:
            top = mid - 1
        else:
            bottom = mid + 1
    return index

li = [2, 5, 7, 9, 11, 17, 222]
print(bin_search(li, 11))   # Output: 4
print(bin_search(li, 12))   # Output: -1
```
</details>

---

### Chickens and Rabbits Puzzle

**Question:** We count 35 heads and 94 legs among chickens and rabbits. How many of each?

<details>
<summary>💡 View Solution</summary>

```python
def solve(numheads, numlegs):
    ns = 'No solutions!'
    for i in range(numheads + 1):
        j = numheads - i
        if 2 * i + 4 * j == numlegs:
            return i, j
    return ns, ns

numheads = 35
numlegs = 94
print(solve(numheads, numlegs))  # Output: (23, 12) — 23 chickens, 12 rabbits
```
</details>

---

### Unicode — Print Unicode String

<details>
<summary>💡 View Solution</summary>

```python
unicodeString = "hello world!"
print(unicodeString)
```
</details>

---

### Unicode — Encoding Declaration

**Question:** Write a special comment to declare a Python source file as UTF-8 encoded.

<details>
<summary>💡 View Solution</summary>

```python
# -*- coding: utf-8 -*-
```
</details>

---

## 📝 Notes

> **Python Version:** The original exercises were written in Python 2. All solutions in this file have been updated to be **Python 3 compatible** (e.g., `print()` as a function, `input()` instead of `raw_input()`, `list()` wrappers around `filter()` and `map()`).

---

*Happy coding! 🚀*
