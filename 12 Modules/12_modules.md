
# Study Guide: Python Modules and File Handling

## 1. Understanding Python Modules
A **module** in Python is simply a **file with a `.py` extension** that contains Python code, such as variables and functions. 

### The Purpose of Modules
*   **Organisation:** They allow you to break down complex programs into smaller, more manageable parts.
*   **Reusability:** Code defined in a module can be reused across multiple programs or different parts of the same program without rewriting it from scratch.
*   **Toolbox Analogy:** Think of a Python module as a **specialised tool in a toolbox**. Just as you use a hammer for nails or a wrench for bolts, a module like `math` contains related functions for specific mathematical tasks.

---

## 2. Creating and Using Custom Modules
### Steps to Create and Use a Module
1.  **Create a `.py` file:** For example, save a file named `my_module.py`.
2.  **Define Code:** Inside that file, write your functions or variables (e.g., `def greeting(name): print("Hello, " + name)`).
3.  **Importing:** In your main script or Jupyter Notebook, use the **`import` statement**: `import my_module`.
4.  **Accessing Components:** Use the module name as a prefix to call its functions: `my_module.greeting("Alice")`.

> **Note:** While you can define modules directly within a Jupyter Notebook, it is generally recommended to create **separate `.py` files** to promote better organisation and reusability.

---

## 3. Importing Techniques
Python provides several ways to bring module functionality into your script:

| Syntax | Description | Example |
| :--- | :--- | :--- |
| **`import module`** | Imports the whole module. Components must be prefixed with the module name. | `import math_utils`<br>`math_utils.square(5)` |
| **`from module import function`** | Imports a **specific function**. You can use the function directly without the prefix. | `from math_operations import add`<br>`add(5, 3)` |
| **`from module import *`** | Imports **all functions** from a module. Use them directly without prefixes. | `from math_utils import *`<br>`print(add(2, 3))` |

---

## 4. Renaming and Aliasing
You can give a module or a function an **alias** using the `as` keyword.

*   **Renaming Modules:** `import calculator as calc`. This creates an alias but does **not** change the actual filename of the module.
*   **Renaming Functions:** `from math_operations import add as addition`.
*   **Benefits:**
    *   Improves **readability** by providing more meaningful or concise names.
    *   Avoids **naming conflicts** when two different directories have modules with the same name (e.g., `import dir1.utils as utils1` and `import dir2.utils as utils2`).
    *   Handles **long or cryptic** third-party module names efficiently.

---

## 5. Essential Built-in Modules
### A. The `platform` Module
Provides information about the **system and Python interpreter**.
*   **`system()`**: Returns the OS name (Windows, Linux, Java, etc.).
*   **`version()` / `release()`**: Detailed OS information.
*   **`machine()` / `processor()`**: Architecture and hardware details.
*   **`python_version()`**: Returns the version of Python currently running.

### B. The `datetime` Module
Used for manipulating dates and times.
*   **`datetime.now()`**: Returns the current local date and time.
*   **`strftime(format)`**: Formats a date object into a **readable string**.
    *   `%B`: Full month name (e.g., "June").
    *   `%Y`: Full year (e.g., "2018").
    *   `%A`: Full weekday name.
*   **`strptime(string, format)`**: Parses a **string into a datetime object** based on a specific format.
*   **`timedelta`**: Used for **date arithmetic**, such as calculating the date for "tomorrow".

### C. The `math` Module
Provides mathematical constants and functions.
*   **Basic Stats:** `min()` and `max()` find the lowest/highest values; `abs()` returns the absolute value.
*   **Arithmetic:** `sqrt(x)` (square root), `ceil(x)` (rounds up), `floor(x)` (rounds down), and `factorial(x)`.
*   **Constants:** `math.pi` (3.14...) and `math.e` (2.71...).
*   **Trigonometry:** `sin()`, `cos()`, `tan()` (using radians).
*   **Logarithms:** `log(x, base)` and `exp(x)`.

### D. The `random` Module
Generates random numbers and performs random selections.
*   **`random()`**: Float between 0.0 and 1.0.
*   **`randint(a, b)`**: Random integer between `a` and `b` (inclusive).
*   **`choice(seq)`**: Returns one random element from a sequence.
*   **`sample(population, k)`**: Returns `k` unique random elements.
*   **`shuffle(x)`**: Shuffles a list **in place**.
*   **`seed(a)`**: Initialises the generator to ensure **reproducibility**.

### E. The `os` Module
Interacts with the operating system and file system.
*   **Directory Management:** `getcwd()` (get current directory), `listdir()` (list files), `mkdir()` (create directory), and `rmdir()` (remove empty directory).
*   **File Management:** `remove(path)` (deletes a file) and `rename(src, dst)`.
*   **`os.name`**: Identifies the OS type ('nt' for Windows, 'posix' for Linux/macOS).

---

## 6. File Handling in Python
File handling allows for creating, reading, updating, and deleting files on the system.

### Opening Files with `open()`
**Syntax:** `file_object = open(file_name, mode)`.

**Common Modes:**
*   **`'r'`**: Read (Default). Opens for reading.
*   **`'w'`**: Write. Creates the file or overwrites it if it exists.
*   **`'a'`**: Append. Adds data to the end of the file; creates it if it doesn't exist.
*   **`'x'`**: Create. Returns an error if the file already exists.

### The `with open()` Statement
This is the **preferred method** because it automatically closes the file once the block of code finishes, even if an exception occurs. It removes the need for calling `file.close()` explicitly.

**Syntax:**
```python
with open('file_path', 'r') as file:
    # Perform operations
    pass
```

---

**Analogy for Modules:**
Think of **modules** as **apps on a smartphone**. You don't build a camera, a calculator, or a map from scratch; you just open the relevant app (import the module) to use the features someone else already built. If you need a custom feature, you can build your own app (custom module) and save it to your phone (project directory) for later use.