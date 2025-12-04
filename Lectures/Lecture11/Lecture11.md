# **Lecture 11 — Functions**

Functions are one of the most important building blocks in programming.
They allow us to break large programs into smaller, manageable, reusable pieces.
In this lecture, we will learn how functions work, how to define them, how to call them, and how to use them to structure programs cleanly and effectively.


---

# **1. Why Functions? Motivating the Need**

Imagine writing a whole program as one long list of statements:

* Hard to read
* Hard to debug
* Hard to reuse
* Hard to collaborate on

A better strategy is to **divide the program into smaller tasks**, and write a function for each task.
This approach is called:

* **divide and conquer**
* **modular programming**

Each function performs one specific job, and the **main program coordinates the functions**.


---

# **2. What Is a Function?**

A **function** is a named group of statements that performs a specific task.

You *define* a function once, and then you *call* (or invoke) it whenever you want that task done.

Benefits:

* Makes code simpler and shorter
* Avoids repetition
* Helps isolate bugs
* Makes code easier to test
* Enables teamwork (different people write different functions)


---

# **3. Types of Functions**

Python has two primary categories of user-defined functions:

### **Void Functions**

* Perform a task
* Do **not** return a value
* Example: a function that prints something

### **Value-Returning Functions**

* Perform a task
* **Return** a value to the caller
* Examples: built-ins like `int()`, `float()`, `input()`


---

# **4. Defining a Simple Void Function**

General pattern:

```python
def function_name():
    <statements>
```

Example:

```python
def say_hello():
    print("Hello from inside a function!")
```

Nothing happens until you **call** the function:

```python
say_hello()
```



---

# **5. The `main()` Function Pattern**

Throughout CS-UY 1114, programs follow the structure:

```python
def main():
    # mainline logic
    say_hello()

def say_hello():
    print("Hello from inside a function!")

main()   # program starts here
```

* `main()` is the starting point
* `main()` calls other functions


---

# **6. How Function Calls Work**

When you write:

```python
main()
```

Python:

1. Jumps to the definition of `main()`
2. Executes its statements
3. If `main()` calls another function (e.g., `say_hello()`), Python jumps there
4. When the called function finishes, Python returns to the caller

The flow diagram on page 9 illustrates this clearly. 

---

# **7. Indentation and Blocks**

In Python, indentation defines **blocks** of code.

* All statements in the same block must share the same indentation
* Blocks follow headers ending with a colon (`:`)

  * `def`, `if`, `for`, `while`, etc.
* Blank lines inside a block are ignored

Incorrect indentation will cause syntax errors.


---

# **8. Local Variables and Scope**

A **local variable**:

* Is created inside a function
* Exists only while the function runs
* Cannot be used outside the function

Example:

```python
def show_message():
    message = "Hello!"   # local variable
    print(message)

def main():
    show_message()
    # print(message)  # ERROR: message not defined here

main()
```

The example on page 11 illustrates this exactly. 

---

# **9. Scope Across Functions**

Different functions can reuse the same variable name without conflict:

```python
def f():
    x = 10
    print("f:", x)

def g():
    x = 20
    print("g:", x)
```

Each `x` belongs to its own function.


---

# **10. Arguments and Parameters**

When calling a function, a value is passed **into** the function.

* **Argument**: the actual value sent
* **Parameter**: the variable in the function header that receives the value

Example:

```python
def show_double(number):   # number is the parameter
    print(number * 2)

value = 5
show_double(value)         # value is the argument
```

Inside the call, `number` holds the same value as `value`.


---

# **11. Multiple Parameters**

```python
def show_sum(a, b):
    print("The sum is", a + b)

show_sum(12, 45)
```

Arguments are matched **by position** unless keyword arguments are used.


---

# **12. Changing Parameters Inside a Function**

Changing a parameter **does not** change the variable in the caller.

See the example on page 16 showing:

```python
arg = 0
```

This affects only the **local** copy, not the original variable (`value` in `main()`).


---

# **13. Keyword Arguments**

Keyword arguments allow naming parameters explicitly:

```python
print_date(month=10, day=31, year=2025)
print_date(day=31, month=10, year=2025)
```

Rules:

* Positional arguments must come first
* Keyword arguments may appear in any order


---

# **14. Global Variables**

A **global variable** is created outside all functions.

All functions can *read* it, but modifying it requires declaring it:

```python
global counter
counter = counter + 1
```

Why avoid writable globals?

* Harder to debug
* Less reusable
* Makes program flow unpredictable

Global **constants**, however, are encouraged:

```python
SALES_TAX_RATE = 0.08875
```



---

# **15. Standard Library Functions & Modules**

Python provides many modules:

* Built-ins: `print`, `input`, `len`, `range`
* Additional modules: `random`, `math`

Use them via:

```python
import random
import math

value = random.randint(1, 6)
root = math.sqrt(25)
```

The module diagram on p.22 shows this pattern.


---

# **16. Random Module Examples**

### Random integer:

```python
number = random.randint(1, 100)
```

### Dice roll example:

Defined as a **value-returning function**:

```python
def roll_die():
    return random.randint(1, 6)
```

Shown visually on page 24.


---

# **17. Value-Returning Functions**

General form:

```python
def function_name(parameters):
    statements
    return expression
```

The `return` statement:

* Ends the function
* Sends a value back to the caller

Examples include `sum_two`, `full_name`, and others on pages 25–29.


---

# **18. Boolean Functions**

A function may return `True` or `False`:

```python
def is_even(n):
    return (n % 2) == 0
```

Useful inside conditionals and loops.


---

# **19. Returning Multiple Values**

Python allows returning more than one value (as a tuple):

```python
def divide_and_remainder(a, b):
    return a // b, a % b

q, r = divide_and_remainder(17, 5)
```



---

# **20. The `math` Module**

Provides:

* `math.sqrt`, `math.sin`, `math.cos`
* `math.exp`, `math.log`
* `math.floor`, `math.ceil`
* Constants: `math.pi`, `math.e`

Examples on p.32 show circle area and hypotenuse calculations.


---

# **21. Writing Your Own Modules**

A module is simply a `.py` file containing functions.

Example from pages 34–35:

**utils.py**

```python
def fahrenheit_to_celsius(f):
    return (f - 32) * 5/9
```

**weather.py**

```python
import utils
print(utils.fahrenheit_to_celsius(77))
```


