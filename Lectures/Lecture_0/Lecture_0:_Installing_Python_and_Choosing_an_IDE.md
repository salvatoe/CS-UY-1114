# Installing Python

When I say these notes are *introductory*, I really mean it!  
Most Linux systems come with Python already installed, and macOS used to ship with Python as well. However, the preinstalled versions are often outdated — usually **Python 2**, which was released in **2000** and is no longer maintained. Modern programming uses **Python 3** (originally released in 2008 and still actively updated).

To install the latest Python 3 version, download it directly from python.org:

- **macOS:**  
  [Download Python for Mac](https://www.python.org/ftp/python/3.14.0/python-3.14.0-macos11.pkg)

- **Windows:**  
  [Download Python for Windows](https://www.python.org/downloads/release/pymanager-250/)

After installation, open a terminal (macOS/Linux) or PowerShell (Windows) and run:

```bash
python3 --version
````

or on Windows:

```powershell
py --version
```

You should see a Python 3.x version number.
At the time of writing these notes, the version is 3.14, but versions do get updated periodicaly. The links above will be updated when python 3.15 is released, but any code from here will work with anything bakc to 3.9, so dont worry about constantly updating.  

# **How to Select an IDE**

Once you have Python installed, you need to install a **code editor** or **IDE** (Integrated Development Environment).
Python comes with **IDLE**, which is a very basic, bare-bones editor. I do **not** recommend using it for CS-UY 1114 or for any serious programming work.

The **Python Crash Course (3rd Edition)** book recommends **VS Code**, and that’s a great choice.
However, as an **NYU student**, you also get **free access to JetBrains IDEs** — which are some of the best professional editors available.

Each JetBrains IDE is optimized for a specific language:

* **PyCharm** — Python
* **IntelliJ IDEA** — Java
* **WebStorm** — JavaScript / Web Development
* **CLion** — C and C++
* **Rider** — C# / Unity
* **PhpStorm** — PHP
* **DataGrip** — SQL / Databases

For CS-UY 1114, the JetBrains option is **PyCharm**.

---

# **Thonny: Your Professor’s Recommendation**

Many CS-UY 1114 professors **strongly recommend Thonny**, especially for beginners.

**Thonny is:**

* Extremely simple
* Very clean
* Designed specifically for learning Python
* Has a built-in debugger that shows variables visually
* Easy to install and lightweight

It does *not* overwhelm you with extra windows or tools.
This is why many instructors choose it—it lets you focus entirely on learning Python, not on navigating an IDE.

If you want the easiest, least confusing start, **Thonny is the best beginner option**.

---

## **PyCharm: What to Expect**

When you first open PyCharm, it may look a bit cluttered or overwhelming:

![PyCharm Screenshot](https://github.com/user-attachments/assets/5b5825cb-0534-4c98-8984-efd8ca624997)

However, most panels and tools you see are **optional**. You don’t need to learn them all at once.

PyCharm provides:

* Automatic code formatting
* Real-time error checking
* Intelligent autocomplete
* A built-in debugger
* Virtual environment management
* Git integration
* Built-in terminals
* One-click run configurations

These features become very helpful once you start writing longer programs.

---

# **So Which Should You Use?**

Here’s a simple recommendation chart:

| Editor      | Best For                                         | Notes                                                             |
| ----------- | ------------------------------------------------ | ----------------------------------------------------------------- |
| **Thonny**  | Absolute beginners                               | Recommended by many CS-UY 1114 professors. Very clean and simple. |
| **PyCharm** | Students who want structure and powerful tools   | Great once you’re comfortable with Python basics.                 |
| **VS Code** | Students who want a lightweight, flexible editor | Good all-purpose editor, works for many languages.                |
| **IDLE**    | Avoid if possible                                | Too limited for real coursework.                                  |

Most students end up using **Thonny or PyCharm**, and both are fully acceptable for CS-UY 1114.


[Click here to downalad Pycharm for Mac](https://www.jetbrains.com/pycharm/download/download-thanks.html?platform=macM1)

[Click here to downalad Pycharm for Windows](https://www.jetbrains.com/pycharm/download/download-thanks.html?platform=windowsARM64)

[Click here to downalad Thonny for Mac](https://github.com/thonny/thonny/releases/download/v4.1.7/thonny-4.1.7.pkg)

[Click here to downalad Thonny for Windows](https://github.com/thonny/thonny/releases/download/v4.1.7/thonny-4.1.7.exe)

**Note** Some editors may require that you configure a debugger, or that you configure an interpeter.  See editor instructions for how to do that, since every editor is very different.  

# **Your First Program**

Now that you’ve installed Python and chosen an editor, it’s time to write your very first program.
This will confirm:

* Python is installed correctly
* Your editor is set up
* You know how to run a `.py` file

Even if you’ve coded before, follow these steps carefully — your environment must be configured the way **CS-UY 1114** expects.

---

# **1. Create a New Python File**

Depending on your editor:

### **If You’re Using Thonny**

1. Open Thonny
2. Click **File → New**
3. Type in the code below
4. Save it as **hello_world.py**

### **If You’re Using PyCharm**

1. Open PyCharm
2. Select **New Project** (or open an existing one)
3. Right-click the project folder → **New → Python File**
4. Name it:

   ```
   hello_world
   ```

You should now see an empty Python file open.

---

# **2. Type the Program**

In your new file, enter:

```python
print("Hello, world!")
```

This is the traditional first program in almost every language.
It demonstrates how Python outputs text to the screen.

---

# **3. Run the Program**

### **In Thonny**

Just click the **big green Run button** at the top.

### **In PyCharm**

You have two options:

#### **Option A: Run Button**

Click the **green ▶ button** next to the file name.

#### **Option B: Terminal**

Open PyCharm’s built-in terminal and run:

```bash
python3 hello_world.py
```

or on Windows:

```powershell
py hello_world.py
```

---

# **4. Expected Output**

You should see:

```
Hello, world!
```

If you see this, congratulations — your Python environment is working correctly.

---

# **5. If Something Goes Wrong**

Don’t panic — errors are a normal part of learning programming.

Here are the most common beginner issues and how to fix them:

| Error Message                                    | Meaning                          | How to Fix                                                   |
| ------------------------------------------------ | -------------------------------- | ------------------------------------------------------------ |
| `SyntaxError: EOL while scanning string literal` | Missing quote                    | Make sure your quotes match                                  |
| `NameError: name 'print' is not defined`         | You typed `prnit`, `pritn`, etc. | Fix the spelling                                             |
| `python3: command not found`                     | Python not added to PATH         | Reinstall Python (Windows) or use `py`                       |
| `ModuleNotFoundError`                            | Running the wrong file           | Check the filename and directory                             |
| Nothing happens                                  | You clicked the wrong run button | Make sure you're running **hello_world.py**, not the project |

If you can’t fix the error, **copy the full message** and bring it to lab or office hours — error messages are extremely informative once you learn how to read them.

