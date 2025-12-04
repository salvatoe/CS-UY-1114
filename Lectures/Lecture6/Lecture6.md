# **Repetition Structures**

Programming is not just about making decisions — it’s also about performing actions repeatedly.
Whenever a task must be repeated, loops give the computer its real power.
A program might repeat something two times, ten times, or millions of times.
Loops let us express that repetition clearly and efficiently.

---

# **Why Do We Need Loops?**

Many problems require doing the *same kind of work* several times:

* Checking each item in a list
* Counting up or down
* Searching for something
* Running a process until a condition changes

Without loops, we would have to **copy and paste code** — which is:

* Hard to read
* Error-prone
* Wasteful
* Difficult to maintain

Loops solve all of these issues by giving us a reusable, controlled repetition structure.

---

# **Types of Loop Control**

Python provides two major ways to control repetition:

1. **Condition-controlled loops** — continue as long as a condition remains true
2. **Count-controlled loops** — repeat a fixed number of times (introduced next lecture)

In this lecture, we focus on the **condition-controlled** `while` loop.

---

# **The `while` Loop**

A `while` loop repeats its body *as long as* a given condition is `True`.

Structure:

```python
while condition:
    statements
```

Important characteristics:

* The condition is checked **before every iteration**
* If the condition starts out False, the loop body never runs
* Indentation defines the loop body
* Something inside the loop must eventually **change** the condition

One execution of the loop’s body is called an **iteration**.

---

# **Stopping a Loop**

To ensure a loop eventually stops, something must happen inside the loop to make the loop’s condition become False.

Example of intended repetition:

```python
i = 0
while i < 10:
    print(i)
    i += 1
```

If we forget the update (`i += 1`), the loop will never end.

---

# **Infinite Loops**

An infinite loop occurs when nothing causes the loop’s condition to become False.

This usually happens due to a missing update, incorrect condition, or logic error.

Example of a potential infinite loop:

```python
i = 0
while i < 500:
    print("Hello")
    # missing i += 1
```

Once the loop starts, it will never terminate on its own.

---

# **Example: Repeating a Message Multiple Times**

```python
COUNT = 500
MESSAGE = "I will not throw paper airplanes in class."
i = 0

while i < COUNT:
    print(i, MESSAGE)
    i += 1
```

If the update `i += 1` is removed, this becomes an infinite loop.

---

# **Testing for Primality**

A prime number is:

* Greater than 1, and
* Divisible only by 1 and itself

To determine whether a number `n` is prime, a simple approach is:

1. Start with a potential divisor (2)
2. Check if it divides evenly
3. Continue testing divisors until you find one that works or exhaust all possibilities

### **Basic version**

```python
number = int(input("Enter a number >= 2: "))
prime = True
divisor = 2

while divisor < number and prime:
    prime = (number % divisor != 0)
    divisor += 1

if prime:
    print(number, "is prime.")
else:
    print(number, "is not prime.")
```

This works but can be inefficient for large numbers.

---

# **Improving Efficiency**

Mathematical insights make primality testing faster:

* You only need to test up to **√n**
* Even numbers beyond 2 can be skipped entirely

### Efficient Version

```python
import math

number = int(input("Enter a number >= 2: "))

prime = (number == 2 or number % 2 != 0)
divisor = 3
limit = math.sqrt(number)

while divisor <= limit and prime:
    prime = (number % divisor != 0)
    divisor += 2

if prime:
    print(number, "is prime.")
else:
    print(number, "is not prime.")
```

By skipping even numbers and reducing the divisor range, the loop becomes significantly more efficient.

---

# **Approximating a Square Root**

Loops are also essential for numerical algorithms.
One simple (but inefficient) way to approximate the square root of a number is:

1. Start with a small guess
2. Increase the guess gradually
3. Stop when the square of the guess meets or exceeds the target number

### Example

```python
number = int(input("Enter a positive integer: "))

while number < 0:
    print(number, "isn't a positive int")
    number = int(input("Enter a positive integer: "))

guess = 0.1
while guess**2 < number:
    guess += 0.1

print("The square root of", number, "is approximately", guess)
```

This method uses a loop to incrementally approach the correct answer.

---

# **Summary**

In this lecture we introduced:

* The **purpose** of repetition structures
* Why loops are critical in programming
* The **while loop** as a condition-controlled loop
* How to avoid infinite loops
* Examples of loops applied to real problems:

  * Testing primality
  * Approximating square roots

Loops allow programs to scale from a few operations to billions — enabling complex problem solving with compact code.

