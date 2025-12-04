# **Selection Statements**

Programming often requires choosing different actions depending on conditions.
Up to now, our programs have run linearly — but real problems require branching logic.

Selection statements allow a program to:

* Perform an action only when a condition is true
* Choose between two possible actions
* Select from multiple options
* Build multi-level decision structures

The fundamental tool for all of this is the `if` statement.

---

# **One-Way `if` Statements**

Sometimes a program must perform an action **only if** a condition is true.
If the condition is false, Python simply moves on.

General structure:

```python
if condition:
    statements
```

Example:

```python
if y != 0:
    z = x / y
```

If `y` is zero, the division never executes — avoiding an error.

Key ideas:

* Conditions evaluate to Boolean values (`True` or `False`)
* Indentation determines which lines belong to the `if` block
* A one-way `if` is optional behavior: run it only when needed

---

# **Two-Way `if-else` Statements**

Sometimes the program must choose **exactly one of two paths**.
This is when we use an `else`.

Structure:

```python
if condition:
    true_case
else:
    false_case
```

Python evaluates the condition:

* If True → executes the first block
* If False → executes the `else` block

Example:

```python
if temperature > 32:
    print("Above freezing")
else:
    print("Freezing or below")
```

Both blocks are indented the same amount and are mutually exclusive.

---

# **Multiway `if-elif-else` Chains**

Many real-world decisions require more than two options.
Python handles this through the `elif` (“else if”) keyword.

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

Rules:

* Python checks conditions **top-down**
* The **first True** branch runs
* All remaining branches are skipped
* The final `else` is optional but catches anything unmatched

Example:

```python
if score >= 90:
    letter = "A"
elif score >= 80:
    letter = "B"
elif score >= 70:
    letter = "C"
else:
    letter = "D or below"
```

This is more readable than writing multiple nested `if` statements.

---

# **Nested `if` Statements**

A nested `if` is simply an `if` placed inside another `if` (or inside an `else`).
This allows **multi-level** decision making.

Structure:

```python
if condition1:
    if condition2:
        # both conditions true
    else:
        # condition1 true, condition2 false
else:
    # condition1 false
```

Nested logic is useful when a decision depends on the **result of a previous decision**.

### Example: Grading with an A+ cutoff

```python
grade = float(input("Enter grade: "))

if grade >= 90:
    if grade >= 98:
        print("A+")
    else:
        print("A")
elif grade >= 80:
    print("B")
else:
    print("C or below")
```

Here, we refine the decision only after determining the grade is at least 90.

---

# **Another Example: Age + ID Check**

```python
age = 20
has_id = True

if age >= 18:
    print("You are an adult.")
    if has_id:
        print("You can enter the club.")
    else:
        print("You need an ID to enter.")
else:
    print("You are a minor.")
```

Nested decisions help break a larger rule (“valid to enter”) into sub-rules.

---

# **Another Example: Username and Password**

```python
username = input("Enter your username: ")
password = input("Enter your password: ")

if username == "admin":
    if password == "1234":
        print("Welcome, admin!")
    else:
        print("Incorrect password for admin.")
else:
    print("Username not recognized.")
```

Nested decisions refine access control in stages.

---

# **Chained vs. Nested Conditions**

These two are equivalent:

```python
if side1 == side2 and side2 == side3:
    print("equilateral")
```

and

```python
if side1 == side2:
    if side2 == side3:
        print("equilateral")
```

Which should you use?

* A **single** condition is better when it remains readable.
* Nesting may improve clarity when conditions depend on each other.
* Avoid deep nesting when a clear `elif` chain would be simpler.

Clean code is about *choosing the clearest expression of your logic*.

