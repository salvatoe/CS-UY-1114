# **Lecture 13 — File Input and Output (I/O)**

Files allow programs to store information permanently. In Python, we interact with files using built-in functions and methods that let us read data from files and write data to them.

---

## 1. Why Use Files?

Programs often need to store:

* input data
* output results
* logs or checkpoints

Unlike variables in memory, files **persist after the program ends**. Files live inside a computer’s **file system**, arranged into directories (folders). A file’s **path** describes where it is located.

---

## 2. Paths: Absolute and Relative

### Absolute Path

A full path from the root of the file system.

Examples:

* Windows:
  `C:\Users\student\Desktop\CS1114\project\data.txt`
* macOS / Linux:
  `/home/student/CS1114/project/data.txt`

### Relative Path

Interpreted from the program’s **current working directory**.

* `"data.txt"` means: “look for this file in the directory where the program is running.”

---

## 3. File Paths in Python

Windows uses backslashes `\`, which are also escape characters in Python strings.

Two solutions:

```python
"C:\\Users\\student\\data.txt"     # escape backslashes
r"C:\Users\student\data.txt"       # raw string literal
```

---

## 4. Raw Strings

Escape sequences like `\n` become literal text inside a raw string.

```python
print(r"abc\nxyz")
# prints: abc\nxyz
```

Prefix with `r` to make a raw string.

---

## 5. Viewing the Current Working Directory

```python
import os
print(os.getcwd())
```

Place your input files in this directory when testing.

---

## 6. Opening and Closing Files

To work with a file, Python must first open it.

```python
file_variable = open(filename, mode)
```

After opening a file, you may:

* read from it
* write to it

When finished, close it:

```python
file_variable.close()
```

Closing ensures:

* data is fully written
* other programs can access the file
* no resources are left hanging

---

## 7. File Modes

| Mode   | Meaning                          |
| ------ | -------------------------------- |
| `'r'`  | read (file must already exist)   |
| `'w'`  | write (erases file if it exists) |
| `'a'`  | append (adds new data at end)    |
| `'rb'` | read binary                      |
| `'wb'` | write binary                     |

In this course, we work with **text files**, not binary.

---

## 8. Using the `with` Statement

`with` automatically closes the file when the block ends.

```python
def demo_with(name):
    with open(name, 'r') as infile:
        for line in infile:
            print(line, end='')
```

This is the recommended way to open files.

---

## 9. Reading and Writing Methods

Given a file object `fn`:

| Method           | Description                           |
| ---------------- | ------------------------------------- |
| `fn.read()`      | reads entire file as one string       |
| `fn.read(k)`     | reads next `k` characters             |
| `fn.readline()`  | reads one line                        |
| `fn.readlines()` | reads all remaining lines into a list |
| `fn.write(str)`  | writes a string                       |

---

## 10. Testing Whether a File Exists

```python
import os.path

print(os.path.isfile("foo.txt"))
print(os.path.isfile("notes.txt"))
```

Useful when reading or copying files.

---

## 11. Example: Reading Lines With Line Numbers

```python
import os.path

def main():
    file_name = input("Enter file name: ").strip()

    if not os.path.isfile(file_name):
        print(file_name, "does not exist.")
    else:
        file = open(file_name, 'r')
        line = file.readline()
        line_number = 0

        while line != "":
            line_number += 1
            print(f"{line_number:4d}: {line.strip()}")
            line = file.readline()

        print("Found", line_number, "lines.")
        file.close()

main()
```

---

## 12. Example: Writing 10,000 Coin Flips

```python
import random

def main():
    num_flips = 10000
    per_line = 50
    out = open("flip_results.txt", "w")

    for i in range(1, num_flips + 1):
        side = "H" if random.random() < 0.5 else "T"
        out.write(side)
        if i % per_line == 0:
            out.write("\n")

    out.close()

main()
```

---

## 13. Copying One File Into Another

```python
import os.path

def copy_file():
    src = input("Source file: ").strip()
    dst = input("Target file: ").strip()

    if os.path.isfile(dst):
        print(dst, "already exists")
        return

    infile = open(src, 'r')
    outfile = open(dst, 'w')

    for line in infile:
        outfile.write(line)

    infile.close()
    outfile.close()

copy_file()
```

---

## 14. Writing Then Reading a File (Two-Step Process)

Python cannot read and write **the same file at the same time**, but you can write it, close it, then reopen it.

```python
import random

def write_to_file(name):
    out = open(name, 'w')
    for i in range(100):
        out.write(str(random.randint(0, 99)) + ' ')
    out.close()

def read_from_file(name):
    inp = open(name, 'r')
    nums = inp.read()
    print(nums, '\n')

    values = [int(x) for x in nums.split()]
    count = 0

    for n in values:
        print(n, end=' ')
        count += 1
        if count % 10 == 0:
            print()

    if count % 10 != 0:
        print()

    inp.close()

def main():
    write_to_file("random_nums.txt")
    read_from_file("random_nums.txt")

main()
```

---

## 15. Append Mode

Appending:

* keeps existing data
* adds new information at the end

```python
from datetime import datetime

def log_transaction(message):
    with open("transactions.log", "a") as f:
        timestamp = datetime.now().isoformat()
        f.write(timestamp + " - " + message + "\n")

log_transaction("User logged in.")
log_transaction("User transferred $200.")
```

