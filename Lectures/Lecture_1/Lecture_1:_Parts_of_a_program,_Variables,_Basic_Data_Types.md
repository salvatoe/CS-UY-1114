# Parts of a Program, Variables, Basic Data Types

## What is Python?

### Python is a Multipurpose, Multiparadigm Programming Language

What does that mean?

**Multipurpose** simply means that it can be used in many situations. For example:

1. Python can be used for **Web Development** with frameworks such as *Django* and *Flask*.
2. Python is commonly used in **Data Science and Machine Learning**, thanks to libraries like *NumPy*, *Pandas*, *Matplotlib*, and *scikit-learn*.
3. Python can create **GUI Programs** using libraries such as *Tkinter*, *PyQt*, or *Kivy*.
4. Python is widely used for **Automation and Scripting**, such as renaming files, cleaning data, or automating repetitive tasks.
5. Python is used in **Cybersecurity** for writing tools, exploits, and scanners.
6. Python supports **Game Development** with libraries such as *Pygame*.
7. Python is used in **Networking**, **APIs**, and various **DevOps** workflows.

### Multiparadigm

Programming *paradigms* are different ways (or “styles”) of organizing code.
Python supports several paradigms, including:

* **Procedural Programming**
  Writing code step-by-step, top-to-bottom. This is the first style beginners learn.

* **Object-Oriented Programming (OOP)**
  Organizing code around *classes* and *objects*. Python fully supports OOP.

* **Functional Programming**
  Using ideas like pure functions, `lambda` expressions, `map`, `filter`, and immutability.

This flexibility is one of the reasons Python is so widely used.

### Interpreted vs. Compiled

Python is an **interpreted programming language**, meaning it is executed **line by line** by the Python interpreter.

This differs from languages such as **C**, which are **compiled**.
A compiled language is translated into machine code *all at once*, and then the machine code is executed.

Python is always translated into bytecode, which is a lower-level representation of your program. That bytecode is then interpreted by the Python Virtual Machine (PVM), which executes the instructions and produces the program’s output. In other words: 

<img width="709" height="153" alt="image" src="https://github.com/user-attachments/assets/f46e54df-876b-426d-b488-4702f9e9cdce" />

# Variables

In programming, it is extremely useful to save data for later use.
One of the best ways to do this is with a **variable**.

Let’s try declaring our first variable:

```python
name = "Salvatore"
print(name)
```

Without the quotes Python would think `Salvatore` is a variable name, not text.
Strings must be written inside quotes (`"` or `'`).

---

## What Is a Variable?

A **variable** is a *named memory location* used to store a value.
Python variables themselves **do not** have types — the *values* do. 

For example:

```python
x = 17       # x now refers to an int
x = 5.3      # now x refers to a float
```

Python simply reassigns the name `x` to a new object in memory.

---

## Assignment Statements

The general form of an assignment is:

```
variable = <expression>
```

This evaluates the expression on the **right-hand side** and stores its result in the variable on the **left-hand side**.

Example: 

```python
x = 17.2
y =39
z = x * y 2
print(z)     #672.8
```

The equals sign (`=`) is *not* “equals” in math — it **assigns** a value.

---

## Variables and Reassignment

Variables can be rebound to any type of value — Python is *dynamically typed*. 

```python
x = 3
print(x)

x = "abc"
print(x)

x = 3.14
print(x)
```

Each time, `x` simply points to a new object.

---

## Naming Variables: Rules

Variable names:

✔ must start with a **letter** or **underscore**

✔ may contain letters, digits, and underscores

✔ are **case-sensitive**

✘ cannot use Python **keywords**

Examples of Python keywords:
1. and
2. as
3. assert
4. break
5. class
6. continue
7. def
8. del
9. elif
10. else
11. except
12. False
13. finallyf
14. for
15. from
16. global
17. if'
18. import
19. in
20. is
21. lambda
22. None
23. nonlocal
24. not
25. or
26. pass
27. raise
28. return
29. True
30. try
31. while
32. with
33. yield

✘ should *not* override built-in functions like `print`

1. abs
2. all
3. any
4. ascii
5. bin
6. bool
7. bytearray
8. bytes
9. callable
10. chr
11. classmethod
12. compile
13. complex
14. delattr
15. dict
16. dir
17. divmod
18. enumerate
19. eval
20. exec
21. filter
22. float
23. format
24. frozenset
25. getattr
26. globals
27. hasattr
28. hash
29. help
30. hex
31. id
32. input
33. int
34. isinstance
35. issubclass
36. iter
37. len
38. list
39. locals
40. map
41. max
42. min
43. next
44. object
45. oct
46. open
47. ord
48. pow
49. print
50. property
51. range
52. repr
53. reversed
54. round
55. set
56. setattr
57. slice
58. sorted
59. staticmethod
60. str
61. sum
62. super
63. tuple
64. type
65. vars
66. zip

Example of an error:

```python
print = 8
print("abc")   # ERROR — print is no longer a function
```

---

# Basic Data Types

A **data type** categorizes the *kind* of value stored.

Here are the most common ones we use in CS 1114:

## `int` — Integers

Whole numbers, positive or negative.
Unlimited size.
Examples:

```python
x = 42
y =7
```

## `float` — Floating-Point Numbers

Real numbers with decimals.
Examples:

```python
pi = 3.14159
temperature =9.3
```

They are approximate due to computer precision.

## `str` — Strings

Text enclosed in `" "` or `' '`.
Examples:

```python
name = "Salvatore"
greeting = "Hello, World!"
```

Strings are *immutable* — every modification creates a new string.

## `bool` — Boolean Values

Only two values:

```python
True
False
```

Used in decision-making (later when we learn `if` statements).

---

## Checking Types with `type()`

The `type()` function shows the data type of a value. 

```python
x = 17
print(type(x))    # <class 'int'>

y = 3.14
print(type(y))    # <class 'float'>
```

If a name doesn't exist:

```python
type(w)   # NameError
```

---

# Putting It All Together

Here is a small example program combining variables and basic types:

```python
def main():
    name = "Salvatore"
    age = 18
    gpa = 3.7
    is_student = True

    print("Name:", name)
    print("Age:", age)
    print("GPA:", gpa)
    print("Student:", is_student)

main()
```



