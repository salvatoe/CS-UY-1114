# **Introduction to Object-Oriented Programming**

In our Python experience, most programs are run **linearly**. In other words, execution begins at the top of the file and moves downward, one statement at a time. Each function is called explicitly, each variable is created when we reach its line, and the flow is generally straightforward and procedural.

Object-oriented programming (OOP) changes this model. Instead of focusing on *the order of statements*, OOP focuses on creating **objects**—bundles of data and behavior—that interact with each other. Objects know how to manage their own state and perform their own actions, allowing us to build programs that are more modular, reusable, and realistic.

---

## **A Quick Exercise: Thinking in Objects**

When designing a program using OOP, we often begin by identifying **nouns** in the problem.
Nouns usually become **classes**.

Some nouns we might encounter:

1. **State / Place**
2. **Car**
3. **Animal**

Let’s zoom in on **animals**, because categories of animals give us a natural way to think about *types*:

### **Types of Animals**

1. **Amphibians**
2. **Reptiles**
3. **Mammals**

Each of these is a *subcategory* of animals, which will later connect to the idea of **inheritance** in OOP.

---

## **Characteristics (Attributes)**

Every object has **attributes**—pieces of information that describe it.

For animals, common attributes might include:

1. **Name**
2. **Age**
3. **Endangered status** (yes or no)
4. **Weight**

Now, lets ee what its like in python.  

```python
class Animal:
    def __init__(self, name, age, endangered, weight):
        self.name = name
        self.age = age
        self.endangered = endangered   # True or False
        self.weight = weight           # in whatever units you choose

    def __str__(self):
        return (f"Animal(name={self.name}, age={self.age}, "
                f"endangered={self.endangered}, weight={self.weight})")
```

### Example of using it:

```python
a1 = Animal("Tiger", 4, True, 220)
a2 = Animal("Rabbit", 1, False, 4)

print(a1)
print(a2)
```

### Output:

```
Animal(name=Tiger, age=4, endangered=True, weight=220)
Animal(name=Rabbit, age=1, endangered=False, weight=4)
```
Sure — let’s slow down and **really break down** what the `Animal` class is doing, why we write it this way, and how it fits into object-oriented thinking.

---

# **Understanding the `Animal` Class**

When we create a class in Python, we are defining a **new type of object**.
Just like `int`, `str`, or `list` are types, `Animal` becomes a **custom type** that *you* define.

### **Why make a class?**

Because instead of storing information in separate variables like:

```python
name = "Tiger"
age = 4
endangered = True
weight = 220
```

…we want **one thing** that *contains* all of these related properties.

That “one thing” is an **object**, and we create it using a **class**.

---

# 1. **The Class Definition**

```python
class Animal:
```

This line tells Python:

> "Hey Python, I am creating a new blueprint called `Animal`."

A **class** is a *template*.
It describes what all Animals *should* look like, but it is **not** a real animal yet.

---

# 2. **The `__init__` Method (The Constructor)**

```python
def __init__(self, name, age, endangered, weight):
```

* `__init__` runs **automatically** every time you make an Animal.
* It’s called the **constructor** because it *constructs* the object.

### What does `self` mean?

* `self` refers to the **specific object being created**.
* It is similar to “this object” in other languages.

Think of `self` as the animal *itself*.

---

# 3. **Instance Variables**

Inside the constructor:

```python
self.name = name
self.age = age
self.endangered = endangered
self.weight = weight
```

These store data **inside the object**, so each Animal can have *its own* values:

```python
tiger = Animal("Tiger", 4, True, 220)
rabbit = Animal("Rabbit", 1, False, 4)
```

`tiger.age` is **4**,
but `rabbit.age` is **1** — they each carry their own information.

---

# 4. **The `__str__` Method**

```python
def __str__(self):
    return (f"Animal(name={self.name}, age={self.age}, "
            f"endangered={self.endangered}, weight={self.weight})")
```

This tells Python **how to print** an Animal cleanly.

Without it:

```
<__main__.Animal object at 0x00000123AF40>
```

With it:

```
Animal(name=Tiger, age=4, endangered=True, weight=220)
```

This makes your objects readable, which is extremely helpful when debugging or printing results. Instead of a memory address, you get a human-friendly description of the animal’s data.

---

# **Putting Everything Together**

The `Animal` class defines:

* **what information** each object should store (name, age, endangered, weight)
* **how to create** those objects (the `__init__` constructor)
* **how to display** them to the user (`__str__`)

Now you can create as many animals as you want, each with their own data:

```python
lion = Animal("Lion", 8, False, 420)
frog = Animal("Tree Frog", 2, True, 0.1)
bear = Animal("Black Bear", 5, False, 150)
```

Each of these is now a **real object**—not just raw data scattered across variables, but an organized unit that stores everything about that creature.
