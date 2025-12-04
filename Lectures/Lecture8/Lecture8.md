# **Iterative Statements: Nested Loops**

Up to now, we have used loops to repeat a block of code.
But many real problems require repeating **one loop inside another**.
This is the idea of a **nested loop**, one of the most powerful tools in programming.

Nested loops allow us to explore combinations of values, generate tables, iterate over two-dimensional structures, and simulate real systems.

---

# **What Is a Nested Loop?**

A nested loop is simply a loop placed inside the body of another loop.

The essential idea:

* The **outer loop** runs first
* For **each iteration** of the outer loop, the **inner loop runs fully**
* When the inner loop finishes, the outer loop moves to its next iteration
* This repeats until the outer loop completes

A real-world analogy is an **analog clock**:

* The seconds hand completes **60 full cycles** for every 1 movement of the minutes hand
* The minutes hand completes **60 full cycles** for every 1 movement of the hours hand

This is exactly how nested loops behave.

---

# **Key Properties of Nested Loops**

### 1. The inner loop runs faster

It finishes all its iterations before the outer loop moves one step.

### 2. Total iterations multiply

If the outer loop runs `A` times and the inner loop runs `B` times,
then the total number of iterations is:

[
\text{Total} = A \times B
]

Add a third nested loop? Multiply again.

### 3. Either loop can serve as the outer or inner loop

The choice depends on which variable changes slower and which needs to repeat more frequently.

---

# **Practical Use Case: Generating BMI Values**

Consider a program that computes BMI for a variety of heights and weights.

We want:

* Heights from 54 to 82 inches, stepping by 2
* Weights from 85 to 350 pounds, stepping by 5

For each height, we compute BMI for **every** weight.
This structure naturally forms a nested loop.

```python
def main():
    """Generate BMI for various heights and weights."""

    for height in range(54, 83, 2):
        print("*** BMI's for height =", height, "***")

        for weight in range(85, 351, 5):
            bmi = 703 * weight / (height ** 2)
            print("height =", height,
                  "weight =", weight,
                  ">>>> BMI =", round(bmi, 2))

main()
```

Every height produces a full inner loop of weights.
This produces a two-dimensional grid of values — perfect for tables or visualizations.

---

# **Another Example: Digital Clock Simulation**

A digital clock counts:

* 24 possible hours
* 60 possible minutes
* 60 possible seconds

To generate every possible timestamp, three nested loops perfectly match the structure:

```python
for hour in range(24):
    for minute in range(60):
        for second in range(60):
            print("Time:", str(hour) + ":" +
                           str(minute) + ":" +
                           str(second))
```

This produces `24 × 60 × 60 = 86,400` timestamps — one for each second of a day.

---

# **How Nested Loops Grow**

Nested loops scale quickly:

* Two loops → rectangular grid of values
* Three loops → cube of possibilities
* Four or more → multidimensional simulation

Use them carefully — nested loops can grow computational cost much faster than single loops.
But when used appropriately, they give tremendous expressive power.

---

# **Common Uses of Nested Loops**

* Generating tables (multiplication tables, BMI tables, etc.)
* Simulating real systems (clocks, days/months/years, coordinate grids)
* Working with 2D arrays or matrices
* Building textual or graphical patterns
* Searching multi-dimensional data

