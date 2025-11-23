# Parts of a Program, Variables, Basic Data Types

## What is Python?

### Python is a Multipurpose, Multiparadigm Programming Language

What does that mean?

**Multipurpose** simply means that it can be used in many situations. For example:

1. Python can be used for **Web Development** with frameworks such as *Django* and *Flask*.
2. Python is commonly used in **Data Science and Machine Learning**, thanks to libraries like *NumPy*, *Pandas*, *Matplotlib*, and *scikit-learn*.
3. Python can create **GUI Programs** using libraries such as *Tkinter*, *PyQt*, or *Kivy*.
4. Python is widely used for **Automation and Scripting**, such as renaming files, cleaning data, or automating repetitive tasks.
5. Python is used in **Cybersecurity** for writing tools, exploits, and scanners.
6. Python supports **Game Development** with libraries such as *Pygame*.
7. Python is used in **Networking**, **APIs**, and various **DevOps** workflows.

### Multiparadigm

Programming *paradigms* are different ways (or “styles”) of organizing code.
Python supports several paradigms, including:

* **Procedural Programming**
  Writing code step-by-step, top-to-bottom. This is the first style beginners learn.

* **Object-Oriented Programming (OOP)**
  Organizing code around *classes* and *objects*. Python fully supports OOP.

* **Functional Programming**
  Using ideas like pure functions, `lambda` expressions, `map`, `filter`, and immutability.

This flexibility is one of the reasons Python is so widely used.

### Interpreted vs. Compiled

Python is an **interpreted programming language**, meaning it is executed **line by line** by the Python interpreter.

This differs from languages such as **C**, which are **compiled**.
A compiled language is translated into machine code *all at once*, and then the machine code is executed.

Python is always translated into bytecode, which is a lower-level representation of your program. That bytecode is then interpreted by the Python Virtual Machine (PVM), which executes the instructions and produces the program’s output. In other words: 

<img width="709" height="153" alt="image" src="https://github.com/user-attachments/assets/f46e54df-876b-426d-b488-4702f9e9cdce" />

## Variables

In programing, it is epecailly useful to save data for later use.  one of the best ways to do this is with a variabvle.  Lets try declaring our first varibale:

```python
name = Salvatore
print(name)
```

