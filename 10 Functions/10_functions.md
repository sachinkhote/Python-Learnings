# Summary: Functions in Python

This document provides a comprehensive guide to Python functions, covering their definition, parameters, return statements, and the concepts of scope and namespaces.

## 1. Overview and Purpose

**Functions** are reusable blocks of code designed to perform a specific task. They allow programmers to organize code into manageable "chunks", making it easier to understand, debug, and maintain.

*   **Analogy:** Functions are like **recipes** in cooking. A recipe breaks down the process of making a dish into steps (inputs/parameters and actions). Once you have the recipe, you can reuse it multiple times without reinventing the steps.
*   **Key Benefit:** Functions promote code reusability and help avoid redundant repetition.

## 2. Types of Functions

| Type | Description | Examples | Source |
| :--- | :--- | :--- | :--- |
| **User-defined** | Created by the programmer to solve specific problems or modularize code. | Defined using the `def` keyword. | |
| **Built-in** | Pre-defined functions bundled with Python for common tasks. | `print()`, `len()`, `max()`, `min()`, `sum()`, `range()`, `int()`, etc. | |

**Note:** Built-in functions are generally faster and more efficient than user-defined ones because they are pre-existing and optimized for performance.

## 3. Defining and Calling Functions

To create a function, use the `def` keyword.

### Syntax
```python
def function_name(parameters):
    # Function body: Code to execute
    return value # Optional
```
*   **`def`**: Keyword that signals the beginning of a function definition.
*   **`function_name`**: Should follow Python's naming conventions.
*   **Parameters**: Optional placeholders for input data, defined within parentheses `()`.
*   **Colon (`:`)**: Denotes the start of the indented function body.
*   **`return`**: Optional keyword used to exit a function and pass a value back to the caller.
*   **`pass`**: If you must define an empty function for structure, use `pass` to avoid a `SyntaxError`.

### Example: Basic Function
```python
def my_function():
    print("Hello from a function")

my_function() # Calling the function
```

## 4. Parameters vs. Arguments

While often used interchangeably, they have distinct roles:
*   **Parameters**: The **placeholders** specified inside the parentheses in the function definition (e.g., `name` in `def greet(name):`).
*   **Arguments**: The **actual values** passed to the function when it is called (e.g., `"Alice"` in `greet("Alice")`).

### Argument Types and Handling

| Type | Description | Example | Source |
| :--- | :--- | :--- | :--- |
| **Positional** | Arguments must be passed in the correct order and count. | `my_func(fname, lname)` requires exactly two arguments. | |
| **Arbitrary (`*args`)** | Used when you don't know how many arguments will be passed. Receives a **tuple**. | `def my_func(*kids): print(kids)` | |
| **Keyword** | Sent using `key = value` syntax. Order of arguments does not matter. | `my_func(child1="Emil", child2="Tobias")` | |
| **Arbitrary Keyword (`**kwargs`)** | Used when you don't know how many keyword arguments will be passed. | Often shortened to `**kwargs` in docs. | |
| **Default** | Provides a fallback value if no argument is supplied. | `def my_func(country="Norway"):` | |

## 5. The Return Statement

The `return` statement is used to exit a function and give back a value to the caller.

*   **Default Value:** If a function has no `return` statement, it returns `None` by default.
*   **Multiple Values:** Functions can return multiple values separated by commas, which Python implicitly packages as a **tuple**.
    *   *Example:* `return sum_result, product_result` returns `(16, 60)`.

### `print()` vs. `return` (The "Cake" Analogy)
*   **`print()`** is like your friend **showing** you the cake they baked. You can see it, but you can't take it with you or use it later.
*   **`return`** is like your friend **giving** you the cake. You can take it, eat it, or use it for other purposes in your program.
*   Use `print()` to display intermediate messages; use `return` to pass the final result back to your program.

## 6. Scope and Namespaces

### Scope
Scope refers to the region where a variable is visible and accessible.

1.  **Global Scope**: Variables defined outside any function. Accessible from anywhere.
2.  **Local Scope**: Variables defined inside a function. Accessible **only** within that function.
    *   **Tip:** To change a global variable's value from inside a function, you must use the **`global` keyword**.

### Namespaces and the LEGB Rule
A namespace is a container where Python stores names (variables/functions) and their objects. To find a value, Python searches "boxes" in a specific order known as the **LEGB rule**:
1.  **L (Local)**: The current function's box.
2.  **E (Enclosing)**: The box of any enclosing (outer) functions if nested.
3.  **G (Global)**: The script's top-level box.
4.  **B (Built-in)**: The box containing Python's built-in names (e.g., `len`).

## 7. Higher-Order Functions
Python allows you to pass a **function as an argument** to another function.
*   *Example:* A `transform_list(func, values)` function can take a `double` function as an argument and apply it to every element in a list.

---

## 💡 Notes and Tips

### Avoid Common Errors
*   **`TypeError` (Argument Count)**: Calling a function with the wrong number of arguments (e.g., passing 1 argument when 2 are required) will crash your program.
*   **`SyntaxError` (Default Order)**: In a function definition, all parameters **without** default values must come **before** parameters **with** default values.
    *   *Wrong:* `def func(a, b=10, c):`
    *   *Correct:* `def func(a, c, b=10):`
*   **`NameError`**: Occurs if you try to access a local variable from the global scope or if you return a variable that hasn't been defined yet.
*   **Global vs Local**: If you define a variable inside a function with the same name as a global variable, the local one "shadows" the global one within that function.

### Nested Function Execution
*   When functions are nested, the **outer function is executed first** before the inner function.
*   Control returns to the outer function only after the inner function has completely finished.

### Performance Tip
Built-in functions like `sum()` or `len()` are pre-existing and optimized, making them faster than writing your own loop to perform the same task.