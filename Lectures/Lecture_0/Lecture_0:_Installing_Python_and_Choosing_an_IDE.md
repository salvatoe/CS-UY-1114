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

**Note** Some editors may require that you configure a debugger, or that you configure an interpeter.  See editor instructions for how to do that, since every editor is cery different.  
