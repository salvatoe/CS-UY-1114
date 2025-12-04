# **Basic Operators and Expressions**

## What Are Operators and Expressions?

In Python, an **expression** is any combination of values, variables, or operations that produces a result.
Operators allow Python to **evaluate mathematical, logical, and comparison operations**.
This lecture introduces essential tools that let your programs *compute*, *compare*, and *interact* with user input.

---

# **Data Type Conversion**

Python provides several *built-in functions* that convert one data type into another
(slide page 3). 

### **Common Conversion Functions**

* `float(x)` – converts `x` to a floating-point number
* `int(x)` – converts `x` to an integer

  * Important: this **truncates** the decimal part
* `str(x)` – converts `x` to a string
* `round(x)` – rounds to the nearest whole number (ties go to even)

### **Examples (from slide page 4)**



```python
float(17)        # 17.0
str(17)          # '17'

int(17.75)       # 17
str(17.75)       # '17.75'

int("17")        # 17
float("17")      # 17.0

round(17.1)      # 17
round(17.6)      # 18
round(17.5)      # 18   # rounds to even
round(18.5)      # 18   # rounds to even
```

---

# **Arithmetic Operations**

Python supports standard arithmetic operators (slide page 5). 

| Operator | Meaning        | Example      | Result |
| -------- | -------------- | ------------ | ------ |
| `+`      | Addition       | `34 + 1`     | `35`   |
| `-`      | Subtraction    | `34.0 - 0.1` | `33.9` |
| `*`      | Multiplication | `300 * 30`   | `9000` |
| `/`      | Float division | `1 / 2`      | `0.5`  |
| `//`     | Floor division | `7 // 3`     | `2`    |
| `%`      | Remainder      | `20 % 3`     | `2`    |
| `**`     | Exponentiation | `4 ** 0.5`   | `2.0`  |

---

## **Integer (Floor) Division**

Floor division **rounds down** to the nearest integer (slide page 6).


```python
7 // 3     # 2
10 // 3    # 3
-7 // 3    # -3   # rounds DOWN
```

---

## **Modulo Operator (%)**

The modulo operator gives the **remainder** (slide page 7).


The key identity:

```
x == (x // y) * y + (x % y)
```

---

# **Input from the User**

To get input from a user, Python uses the `input()` function (slide page 8).


* `input()` always returns a **string**
* You must convert the input to `int` or `float` before doing arithmetic

Example:

```python
height = float(input("Enter height in inches: "))
weight = float(input("Enter weight in pounds: "))
```

---

## **Example Program: BMI Calculator**

Slides 9–10 describe a program to compute **Body Mass Index** (BMI).


Template code:

```python
"""
A program that asks the user for their height and 
weight in inches and pounds. Calculates and displays BMI.
"""
def main():
    # Get height and weight from user.
    # Compute and display initial BMI using formula
    # from wikipedia.org/wiki/Body_mass_index.

    # Convert BMI result to a real number
    # with only the tenths place.

main()
```

---

# **Augmented Assignment Statements**

Python provides shorthand operators (slide page 11).


| Expression | Equivalent To |
| ---------- | ------------- |
| `i += j`   | `i = i + j`   |
| `i -= j`   | `i = i - j`   |
| `i *= j`   | `i = i * j`   |
| `i /= j`   | `i = i / j`   |
| `i //= j`  | `i = i // j`  |
| `i %= j`   | `i = i % j`   |
| `i **= j`  | `i = i ** j`  |

Example (slide page 12):


```python
x = 2.4
x *= 3.7
print(x)     # 8.88
```

---

# **Mixed-Type Expressions**

Python automatically determines result types (slide page 13).


* `float + float` → float
* `int + int` → int (except `/`, which yields float)
* `int + float` → float

Examples (slide page 14):


```python
5 * 3 - 4 * 6         # -9
4.2 * 3 - 1.2         # 11.400000000000002
5 // 2 + 4            # 6
5 / 2 + 4             # 6.5
```

---

# **Special Assignment Statements**

Slides 15 describe three useful forms.


### **Simultaneous Assignment**

```python
m, n = 2, 3
```

### **Swapping Variables**

```python
i, j = j, i
```

### **Chained Assignment**

```python
i = j = k = 1
```

---

# **Booleans**

A **Boolean** represents truth values: `True` and `False` (slide 16).

Boolean expressions evaluate to a Boolean.

### Examples (slide page 17)



```python
bool(1)     # True
bool(0)     # False
bool("")    # False
bool("hi")  # True
```

## **Booleans Stored as Integers**

Internally: `True` → `1`, `False` → `0` (slide 18).


---

# **Boolean Context**

In any Boolean context (like an `if` statement):
(slide page 19) 

* `False`, `0`, `""`, `None` → treated as **False**
* Everything else → **True**

---

# **Comparison Operators**

Python supports the following comparison operators (slide page 20).


| Operator | Meaning               |
| -------- | --------------------- |
| `<`      | Less than             |
| `<=`     | Less than or equal    |
| `>`      | Greater than          |
| `>=`     | Greater than or equal |
| `==`     | Equal to              |
| `!=`     | Not equal to          |

Each expression evaluates to a Boolean value.

---

# **Float Comparison Caution**

Due to floating-point precision limits, exact comparison may fail
(slide page 21). 

Example:

```python
(1.1 * 3 == 3.3)   # False
1.1 * 3            # 3.3000000000000003
```

