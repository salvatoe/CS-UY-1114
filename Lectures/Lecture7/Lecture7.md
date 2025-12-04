# **Iterative Statements: The `for` Loop**

Up to this point, we’ve seen **condition-controlled loops**, where repetition continues until a Boolean expression becomes false.
Now we introduce the second major category of repetition: **count-controlled loops**.

Many programs need to repeat an action a *specific* number of times.
This is where Python’s `for` loop shines.

---

# **What Is a Count-Controlled Loop?**

A count-controlled loop repeats its body **once for each item** in a sequence.
This makes it ideal when:

* The exact number of repetitions is known in advance
* You want to iterate over a collection of values
* You want to generate structured output like tables, grids, or sequences

Structure:

```python
for variable in sequence:
    statements
```

On each iteration:

* Python assigns the next element of the sequence to the loop variable
* Executes the loop body once
* Moves on to the next element

The loop stops automatically when the sequence ends.

---

# **Example: Iterating Through a Simple List**

```python
for num in [1, 2, 3, 4]:
    print(num)
```

The loop runs **four times**, once for each value in the list.
The variable `num` becomes:

* 1 during the first iteration
* 2 during the second
* 3 during the third
* 4 during the fourth

Once the sequence ends, the loop ends.

This is the essence of the `for` loop:
**One iteration per item in the sequence.**

---

# **What Is a Sequence?**

A **sequence** is an ordered collection of values.
Examples include:

* Lists: `[2, 3, 5, 7, 11]`
* Strings: `"hello"`
* The output of the `range()` function

Python’s `for` loop works naturally with any sequence, making it a powerful tool for structured repetition.

---

# **The `range()` Function**

`range()` is the most common way to generate sequences for counting.

### Forms of `range()`:

1. **`range(end)`**
   Values: 0, 1, 2, …, end−1

2. **`range(start, end)`**
   Values: start, start+1, …, end−1

3. **`range(start, end, step)`**
   Values: start, start+step, start+2·step, …
   Stops before reaching end

Examples:

```python
for i in range(3, 6):     # 3 4 5
for i in range(3):        # 0 1 2
for i in range(0, 11, 3): # 0 3 6 9
for i in range(11, 0, -3):# 11 8 5 2
```

**Key point:** The ending value is *not* included.

---

# **`range()` and Iteration Count**

Because `range()` produces a predictable sequence of integers, it is perfect for loops where you know in advance how many times you need to run something.

Example:

```python
for i in range(10):  # runs 10 times
    print("Iteration:", i)
```

---

# **Example: Powers Table**

```python
def main():
    base = int(input("Enter the base: "))
    max_power = int(input("Enter the maximum power: "))

    for power in range(0, max_power + 1):
        print(base, "to the", power, "is", base ** power)

main()
```

We use `range(max_power + 1)` because exponent 0 is included, and we want to go *through* `max_power`.

---

# **Nested Loops**

A loop can contain any statements — including **another loop**.
Nested loops allow us to generate combinations of values, grids, tables, or multi-dimensional patterns.

### Real-world uses:

* Multiplication tables
* Reading multi-row datasets
* Drawing graphics
* Simulating combinations of parameters

---

# **Example: BMI Table Generation**

```python
def main():
    # Heights: 54 to 82 inches, step 2
    # Weights: 85 to 350 pounds, step 5

    for height in range(54, 83, 2):
        print("*** BMI's for height =", height, "***")

        for weight in range(85, 351, 5):
            bmi = 703 * weight / (height ** 2)
            print("height =", height,
                  "weight =", weight,
                  ">>> BMI =", round(bmi, 2))

main()
```

Here, for **each** height, the program loops through a full range of weights.
The result is a table that can be used for analysis or visualization.

Nested loops multiply behavior:

* Outer loop: number of heights
* Inner loop: number of weights
* Total iterations = product of both ranges

---

# **Infinite Loops in `for` Loops?**

Although rare, `for` loops *can* be infinite if the sequence itself is infinite.

For example:

```python
for x in iter(int, 1):  # intentionally strange
    print(x)
```

But under normal usage — especially with lists or `range()` — **`for` loops cannot accidentally become infinite.**

This is one of their biggest advantages over `while` loops.

