# **Control Flow, Booleans, and Expressions**

## Why Do Programs Need Control Flow?

Up to now, our programs have executed **top to bottom**, one line at a time.
But real programs need to *make decisions* — they react differently depending on user input, data, or conditions.

Control flow lets your program:

* Choose whether to run certain code
* Select between multiple alternatives
* Evaluate logical conditions
* Combine decisions using Boolean logic

The fundamental tool that makes all of this possible is the **if statement**.

---

# **The `if` Statement**

An `if` statement evaluates a **Boolean expression**.
If the expression is `True`, Python executes a block of code.
If it is `False`, Python skips that block entirely.

The structure:

```python
if condition:
    statements
```

Two important rules:

1. **Indentation matters** — indentation defines the block controlled by the `if`.
2. The condition must evaluate to a **Boolean value** (`True` or `False`).

### Example

```python
x = int(input("Enter an integer (0 to skip): "))

if x != 0:
    print("You entered:", x)
```

If the user enters `0`, nothing prints.

---

# **Adding an `else` Clause**

`else` allows the program to take an *alternative path* when the condition is False.

Structure:

```python
if condition:
    true_case
else:
    false_case
```

Python will always choose **exactly one** of the two branches.

### Example: Checking Radius Validity

```python
import math

radius = float(input("Enter the radius: "))

if radius >= 0:
    area = math.pi * radius**2
    print("Area =", area)
else:
    print("Negative radius entered.")
```

---

# **Combining Conditions with `elif`**

Some decisions require more than two options.
`elif` (“else if”) lets Python check multiple conditions sequentially.

Structure:

```python
if condition1:
    ...
elif condition2:
    ...
elif condition3:
    ...
else:
    ...
```

Python stops checking as soon as it finds the **first True** condition.

### A Classic Example: Tax Brackets

```python
income = int(input("Enter income: "))

if income <= 9875:
    bracket = "10%"
elif income <= 40125:
    bracket = "12%"
elif income <= 85525:
    bracket = "22%"
elif income <= 163300:
    bracket = "24%"
else:
    bracket = "32%"

print("Your tax bracket is:", bracket)
```

---

# **Booleans and Comparison Operators**

A **Boolean** is either `True` or `False`.
Most Booleans in programs come from **comparison operators**:

| Operator | Meaning               |
| -------- | --------------------- |
| `==`     | equal                 |
| `!=`     | not equal             |
| `<`      | less than             |
| `<=`     | less than or equal    |
| `>`      | greater than          |
| `>=`     | greater than or equal |

Example:

```python
x = 5
print(x >= 3)   # True
print(x == 10)  # False
```

---

# **Logical Operators: `and`, `or`, `not`**

Python combines Boolean expressions using:

* `and` → True only if *both* conditions are True
* `or` → True if *at least one* condition is True
* `not` → reverses a Boolean value

### Truth Tables

**AND**

| A | B | A and B |
| - | - | ------- |
| F | F | F       |
| F | T | F       |
| T | F | F       |
| T | T | T       |

**OR**

| A | B | A or B |
| - | - | ------ |
| F | F | F      |
| F | T | T      |
| T | F | T      |
| T | T | T      |

**NOT**

| A | not A |
| - | ----- |
| F | T     |
| T | F     |

---

# **Short-Circuit Evaluation**

Python evaluates logical expressions efficiently:

* In `A and B`, if `A` is False, **B is not evaluated**.
* In `A or B`, if `A` is True, **B is not evaluated**.

This behavior is useful for preventing errors.

Example:

```python
s = ""
if s != "" and s[0] == "A":
    print("Starts with A")
```

If `s` is empty, the second check is skipped, preventing an error.

---

# **Conditional Expressions (Ternary Operator)**

Python allows a compact way to choose between two values:

```python
value_if_true if condition else value_if_false
```

Example:

```python
num = int(input())
parity = "even" if num % 2 == 0 else "odd"
print(parity)
```

Equivalent to a longer if-else, but cleaner.

---

# **Operator Precedence**

Python follows specific rules for evaluating expressions.
From highest to lowest priority:

1. `**`
2. Unary `+` and `-`
3. `* / // %`
4. `+ -`
5. Comparisons
6. `== !=`
7. `not`
8. `and`
9. `or`

When in doubt, **use parentheses**.

Example:

```python
3 + 4 * (5 + 2)
```

The parentheses ensure `(5 + 2)` happens first.

---

# **Examples**

```python
-3 * 4          # -12
3 + 2**4        # 19
4 < 5 <= 17     # True (chained comparisons)
4 + (5 < 2) + 7 # 11, because (5 < 2) is False → 0
```

---

# **A Larger Boolean Example: Leap Years**

A year is a leap year if:

* divisible by 4
* not divisible by 100, **unless** also divisible by 400

Python version:

```python
year = int(input("Enter a year: "))

is_leap = (year % 4 == 0) and (not (year % 100 == 0) or (year % 400 == 0))

if is_leap:
    print(year, "is a leap year.")
else:
    print(year, "is not a leap year.")
```

