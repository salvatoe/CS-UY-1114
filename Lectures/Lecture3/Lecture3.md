# **Python Modules, Random Numbers, and the Math Library**

## What Is a Module?

In Python, a **module** is simply a file containing Python code — usually functions, variables, or useful definitions.
Modules allow us to extend Python’s capabilities without writing everything ourselves.

### Why use modules?

* They organize code into reusable components.
* They give access to tools written by others.
* Many important features of Python live inside modules.

Examples of built-in modules include:

* `random` — for generating random numbers
* `math` — for mathematical functions
* `calendar`, `os`, `sys`, etc.

We can also create our own modules by writing Python files and importing them.

---

# **Importing Modules**

Before using anything inside a module, you must **import** it.
The simplest form:

```python
import moduleName
```

After importing, everything inside the module becomes accessible.

Example:

```python
import math
result = math.sqrt(25)
print(result)
```

Here, `math.sqrt` refers to the `sqrt` function inside the `math` module.

Python looks for modules in:

1. The current directory
2. A set of system directories where Python’s standard libraries live

---

# **Using Module Functions**

Once a module is imported, you access its functions using **dot notation**:

```
moduleName.functionName()
```

Examples:

```python
import random
random.random()

import math
math.cos(0)
math.pi
```

This helps avoid name collisions and keeps code organized.

---

# **Random Numbers in Python**

Many programs need randomness:

* Games
* Simulations
* Procedural generation
* Cryptography (though the `random` module is not cryptographically secure)

Computers do not generate true randomness — instead, they generate
**pseudo-random numbers**, produced by deterministic algorithms that *appear* random.

---

## **The Random Number Generator and Seeding**

The random module uses a **seed** value to start generating its sequence.
If the seed is the same, the sequence of numbers will always be the same.

By default, the seed is based on the current system time.

You can manually set a seed:

```python
import random

random.seed(10)
```

This guarantees reproducible output — useful for debugging and testing.

### Example

```python
import random

random.seed(1)
print(random.random())
print(random.random())
```

Running this program multiple times produces identical results.

---

# **Useful Functions in `random`**

Some of the most common random functions:

### **Random float in [0.0, 1.0)**

```python
random.random()
```

### **Random integer in inclusive range**

```python
random.randint(a, b)
```

Returns a number `N` such that `a <= N <= b`.

### **Random integer from a range (like range())**

```python
random.randrange(start, stop, step)
```

Returns a random integer `N` where `start <= N < stop`.

### Examples

```python
import random
random.seed(3)

print(random.randint(0, 10))
print(random.randint(2, 100))
print(random.randint(1, 5))
print(random.randint(5, 10))
```

And:

```python
random.randrange(2, 21, 4)
random.randrange(6)
```

---

# **The Math Module**

Python’s built-in arithmetic operators (`+ - * / // % **`) are only the beginning.
For more advanced mathematics, Python provides the **math module**, which includes:

* Trigonometric functions
* Logarithms
* Factorials
* Combinatorics
* Constants (`pi`, `e`, `tau`, `inf`, `nan`)

To use it:

```python
import math
```

---

## **Common math Functions**

Some widely used functions:

* `math.sqrt(x)` — square root
* `math.sin(x)`, `math.cos(x)`, `math.tan(x)` — trigonometric functions
* `math.log(x)`, `math.log10(x)`, `math.log2(x)` — logarithms
* `math.ceil(x)` — round *up*
* `math.floor(x)` — round *down*
* `math.factorial(n)` — n!
* `math.isclose(a, b)` — check whether two numbers are nearly equal

### Math constants

* `math.pi` — π
* `math.e` — Euler’s number
* `math.inf` — infinity
* `math.nan` — “not a number”

---

# **Using Math Functions: Example**

Suppose we want to compute:

[
x = \frac{a \cdot \sqrt{b^2 + c^2}}{2a}
]

Python code:

```python
import math

def main():
    a = 2
    b = 3
    c = 4

    sq_root = math.sqrt(b**2 + c**2)
    x = a * sq_root / (2 * a)
    print("Result:", x)

main()
```

This shows how modules bring powerful tools into your program with minimal effort.

---
