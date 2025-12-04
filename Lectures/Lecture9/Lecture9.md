# **Strings as Sequences and Comparing Strings**

Strings are one of the most important data types in Python.
They are used for input, output, data processing, file formatting, and representing almost anything involving text.
To program effectively, you must understand how strings behave as **sequences**, how they can be compared, and how their built-in operations work.

---

# **Strings as Sequences**

A string literal is simply a sequence of characters.

```python
my_str = "Hello, World"
```

The variable `my_str` references a `str` object. Conceptually (Strings are tuples, which we dicuss in [Lecture 15](Lectures/Lecture15/Lecture15.md)):

```
('H', 'e', 'l', 'l', 'o', ',', ' ', 'W', 'o', 'r', 'l', 'd')
```

Every character has a position in the sequence.

Strings therefore support:

* **Indexing**
* **Iteration**
* **Slicing**
* The same sequence behavior as lists and ranges

Even a single character like `"H"` is a `str`.

---

# **Indexing**

Python uses **zero-based indexing**.

```python
s = "Hello, World"
print(s[7])
```

Output:

```
W
```

Negative indexing counts from the end:

```python
s[-1]    # 'd'
```

---

# **Strings Are Immutable**

You **cannot** change characters inside a string:

```python
s = "hi!"
s[0] = 'c'      # ERROR
```

Strings do not support item assignment.
To modify a string, you must create a **new** one.

---

# **String Comparison**

You can compare strings using:

```
==   !=   <   <=   >   >=
```

### Equality / Inequality

```python
"abc" == "abc"     # True
"abc" == "Abc"     # False
```

Two strings are equal if they have:

1. The same length
2. The same characters at each index

Case matters.

---

# **Lexicographic Ordering**

For `<` and `>`, Python compares strings lexicographically:

* Characters are compared **left to right**
* Comparison uses Unicode ordering
* **Uppercase** letters come before **lowercase** letters
* Shorter prefixes come before longer strings that extend them

Examples:

```python
"Apples" < "apples"    # True
"apples" < "berries"   # True
"app" < "apple"        # True
"Oranges" > "apples"   # True
```

---

# **The `in` Operator**

Checks whether one string occurs inside another:

```python
"sam" in "sampling"      # True
"sam" in "salmon"        # False
```

Negation:

```python
"sam" not in "salmon"    # True
```

---

# **Special (Escape) Characters**

Some characters require escape sequences:

* `\n` — newline
* `\t` — tab
* `\\` — backslash
* `\"` — double quote
* `\'` — single quote

Examples:

```python
print("He said \"Hello\"")
print("C:\\Users\\Student")
```

---

# **The `print()` Function and Formatting**

`print()` can take multiple values:

```python
print(a, b, c, sep=", ")
```

Change the ending:

```python
print("Hello", end="")   # no newline
```

Default `end` is `"\n"`.

---

# **Traversing a String**

Strings can be processed one character at a time:

```python
for char in "Tandon":
    print(char)
```

Example program:

```python
usr_str = input("Enter a string to transpose: ")
for char in usr_str:
    print(char)
```

---

# **Useful String Methods**

### `find()`

Returns the index of a substring, or -1 if not found.

```python
"food".find("oo")   # 1
"food".find("z")    # -1
```

### `replace()`

Returns a **new** string with replacements:

```python
"Mississippi".replace("ss", "zz")
"apple".replace("p", "X")
```

The original string is unchanged.

---

# **More on Immutability**

String methods like `.upper()` or `.lower()` return **new** strings:

```python
s = "hello"
t = s.upper()
# s is still "hello"
```

---

# **Length of a String**

`len()` returns the count of characters:

```python
len("pizza")      # 5
len(" ")          # 1
len("New York")   # 8
```

---

# **Concatenation and Multiplication**

### Concatenation (`+`)

```python
"New" + " " + "York"
```

### Multiplication (`*`)

```python
"ha" * 3   # "hahaha"
"-" * 10
```

Both produce new strings.

---

# **Slicing**

Extract a substring using:

```
string[start:end]
```

* `start` included
* `end` excluded

Examples:

```python
s = "Python Programming"
s[0:6]     # 'Python'
s[7:18]    # 'Programming'
```

---

# **Type Conversion Review**

Common conversions:

```python
int(x)
float(x)
str(x)
```

Examples:

```python
str(123)       # '123'
int("45")      # 45
float("3.14")  # 3.14
```

Mixing strings and integers incorrectly:

```python
"age: " + 20      # ERROR
"age: " + str(20) # OK
```


