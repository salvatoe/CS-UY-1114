# **Lecture 10 — String Slicing, String Formatting, and f-Strings**

Strings are far more powerful than simple text containers.
With slicing, formatting, and interpolation tools, we can extract information and construct clean, professional output.
This lecture continues our exploration of strings as sequences and introduces Python’s core formatting mechanisms.

---

# **1. String Slicing (Review & Extension)**

A slice extracts a substring:

```python
string[start:end]
```

* `start` is **inclusive**
* `end` is **exclusive**
* If omitted, `start` defaults to `0` and `end` defaults to `len(string)`

Example:

```python
name = "James Smith"
first = name[0:5]     # 'James'
last  = name[6:11]    # 'Smith'
```

However, this approach only works when we already know the positions.
Real input varies — so we need a **general** solution.

---

# **2. Extracting First and Last Names**

Users may enter any full name:

```python
name = input("Please enter your full name: ")
```

We want:

* `first_name`
* `last_name`

But without relying on fixed indices.

---

## **Finding the Separator**

Most names contain a **space** between first and last name.
We can find the index of the first space using:

```python
sep_index = name.find(' ')
```

If the user enters `"James Smith"`:

* Characters 0–4 → `"James"`
* Character 5 → space
* Characters 6–10 → `"Smith"`

`find()` returns the index of the first occurrence, or `-1` if not found.

---

## **Using the Separator Index**

### First name:

```python
first_name = name[:sep_index]
```

### Last name:

```python
last_name = name[sep_index + 1:]
```

This works regardless of the lengths of the names.
As long as there is exactly one space, this method is robust.

A less common, but still occasionally useful alternative is the `index()` method.
`index()` is fundamentally similar to `find()`, but with one key difference:

* `find(sub)` → returns `-1` if `sub` is **not** found
* `index(sub)` → **raises a `ValueError`** if `sub` is **not** found

For example:

```python
name = "JamesSmith"

pos1 = name.find(" ")    # returns -1
pos2 = name.index(" ")   # raises ValueError: substring not found
```

Because of this, `find()` is usually safer for user input, while `index()` can be helpful when you *expect* the separator to be present. 

---

# **3. String Formatting**

Programs often need to construct strings with variables embedded inside them.
Python provides two major tools:

1. `str.format()`
2. f-strings (Python 3.6+)

Formatting lets you control:

* variable placement
* punctuation and spacing
* numeric precision
* alignment

---

# **4. Concatenation vs `format()`**

A naïve way to build a string is:

```python
last_line = city + ", " + state + " " + zip_code
```

This works, but is cluttered.

Using `format()`:

```python
last_line = "{}, {} {}".format(city, state, zip_code)
```

Each `{}` is a placeholder.
Arguments fill the placeholders in order.

---

# **5. Formatting Floating-Point Output**

Sometimes values need to be printed with controlled precision, especially prices.

Basic usage:

```python
"The sale price is ${}".format(price)
```

### Adding a format specification

Place a colon after the opening brace:

```python
"The sale price is ${:f}".format(price)
```

`f` → format as floating-point.

### Controlling decimal places

```python
"The sale price is ${:.2f}".format(price)
```

`.2f` → two digits after the decimal point.

---

# **6. Example: Sale Price Calculator**

```python
def main():
    """Prompts the user for an item's original price and discount percentage,
    then prints the sale price formatted to two decimals."""
    
    cost = float(input("Enter item cost: "))
    discount = float(input("Enter discount (percentage): "))
    
    discount = discount / 100     # convert percent → decimal
    reduction = cost * discount
    sale_price = cost - reduction
    
    print("\nThe sale price is ${:.2f}".format(sale_price))

main()
```

Output:

```
Enter item cost: 25
Enter discount (percentage): 8
The sale price is $23.00
```

---

# **7. f-Strings (Formatted String Literals)**

Python 3.6 introduced f-strings, a cleaner alternative to `format()`.

Begin the string with `f` and place expressions inside `{}`:

```python
name = "James"
age = 20
print(f"My name is {name} and I am {age} years old.")
```

No concatenation, no `.format()` — just Python expressions inside a string.

---

## **Expressions Inside f-Strings**

You may place *any valid expression* inside `{}`:

```python
x = 3
y = 4
print(f"{x}^2 + {y}^2 = {x**2 + y**2}")
```

Output:

```
3^2 + 4^2 = 25
```

---

## **Formatted Output in f-Strings**

The same formatting rules apply:

```python
total = 25.006
print(f"Total: ${total:.2f}")
```

Output:

```
Total: $25.01
```

---

## **Alignment Examples**

```python
x = 42
print(f"[{x:>5}]")   # right-align
print(f"[{x:^5}]")   # center-align
print(f"[{x:<5}]")   # left-align
```

---

## **Using Quotes Inside f-Strings**

```python
animal = "cat"
print(f'The "{animal}" is cute.')
```

The outer quotes determine which inner quotes are allowed safely.

---

# **8. When to Use Each Formatting Method**

### Use f-strings when:

* Writing new Python code
* Readability matters
* You want expressions evaluated inline
* You want concise formatting

### Use `format()` when:

* You are generating format templates dynamically
* You are passing format strings into functions
* You need older-version Python compatibility


