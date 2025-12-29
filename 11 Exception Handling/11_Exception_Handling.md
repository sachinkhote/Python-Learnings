

# Session Summary: Exception Handling, Recursion & Lambda Functions

This document serves as a study guide for understanding recursive logic, anonymous functions, and the robust handling of errors in Python.

---

## 1. Recursion Functions

**Recursion** is a programming concept where a function **calls itself** to solve a problem. It breaks a complex problem into smaller sub-problems of the same kind until a "base case" is reached.

### Key Mechanics of Recursion:
*   **Base Case:** A mandatory condition that stops the recursion and returns a value without a further function call. Without this, the function causes an infinite loop and a **stack overflow error**.
*   **Recursive Case:** The part of the function where it calls itself with a slightly different input that is closer to the base case.
*   **Unwinding:** Once the base case is reached, the recursive calls "unwind," and calculations are performed in reverse order to produce the final result.

**Example: Factorial Function**
```python
def factorial(n):
    # Base case: if n is 0 or 1, return 1
    if n == 0 or n == 1:
        return 1
    # Recursive case: call function with n-1
    else:
        return n * factorial(n - 1)

print(factorial(5)) # Output: 120
```

---

## 2. Lambda Functions

**Lambda functions** (also known as anonymous functions) are concise, one-line functions defined without the `def` keyword.

### Syntax and Characteristics:
*   **Syntax:** `lambda arguments: expression`.
*   They can take **any number of arguments** but can only have a **single expression**.
*   They return the value of the expression automatically.
*   Unlike regular functions, they cannot contain multiple statements or expressions.

### Examples:
| Type | Code Example | Output | Source |
| :--- | :--- | :--- | :--- |
| **Addition** | `add = lambda x, y: x + y`<br>`print(add(3, 5))` | `8` | |
| **Squaring** | `square = lambda x: x ** 2`<br>`print(square(5))` | `25` | |
| **Combined** | `def myfunc(n):`<br>` return lambda a : a * n`<br>`mydoubler = myfunc(2)`<br>`print(mydoubler(11))` | `22` | |

---

## 3. Exception Handling

**Exceptions** are unexpected events or errors that occur during program execution. Python normally stops and generates an error message when an exception occurs. **Exception handling** acts as a "safety net" to gracefully manage these errors and prevent crashes.

### Common Python Errors:
| Error Type | Definition | Source |
| :--- | :--- | :--- |
| **`SyntaxError`** | Incorrect code syntax (e.g., missing parentheses). | |
| **`IndentationError`** | Inconsistent or incorrect spacing of code blocks. | |
| **`TypeError`** | Operation applied to an inappropriate data type (e.g., string + int). | |
| **`NameError`** | Variable or function name is not defined in the current scope. | |
| **`ValueError`** | Right type but inappropriate value (e.g., `int("abc")`). | |
| **`IndexError`** | Accessing a sequence index that is out of range. | |
| **`KeyError`** | Accessing a dictionary with a non-existent key. | |
| **`AttributeError`** | Accessing a method or attribute that does not exist for an object. | |
| **`ZeroDivisionError`**| Attempting to divide a number by zero. | |

---

## 4. The `try-except-else-finally` Structure

Python provides four main blocks for handling exceptions:

| Block | Purpose | Source |
| :--- | :--- | :--- |
| **`try`** | Encloses code that **might** raise an exception. | |
| **`except`** | Code that **handles** a specific exception if one occurs. | |
| **`else`** | Optional code that runs **only if no exceptions** occurred. | |
| **`finally`** | Optional code that **always runs**, regardless of errors, for cleanup. | |

### Important Logic:
*   **Multiple `except` blocks:** You can catch different errors separately. Python checks them in the order they appear.
*   **Catching Multiple Errors:** You can handle several error types in one line: `except (ValueError, ZeroDivisionError):`.
*   **Nested `try-except`:** You can place a `try-except` block inside another `try` block for granular error handling.

---

## 5. The `raise` Keyword

The **`raise`** keyword is used by the programmer to **intentionally generate** an exception at a specific point.

*   **Syntax:** `raise ExceptionType("Custom Error Message")`.
*   **Usage:** Often used within `if` statements to enforce rules (e.g., raising a `ValueError` if a user's input is too high).

---

## 💡 Notes and Tips

*   **Avoid "Bare" Excepts:** Using a bare `except:` block (without a specific error type) is generally not recommended because it can catch unintended exceptions and hide bugs.
*   **Base Case Importance:** In recursion, always ensure your input moves closer to the base case; otherwise, the function will call itself indefinitely.
*   **`else` vs. `finally`:**
    *   **`else`** is for logic that should happen *after* success (skipped if an error occurs).
    *   **`finally`** is for cleanup (never skipped).
*   **Traceback:** When an exception is unhandled, Python prints a "traceback," showing exactly where the error occurred and the type of error.

***

**Analogy for Exception Handling:**
Think of a **Construction Worker** building a house.
*   The **Blueprint** is your `try` block: it is the normal plan you follow.
*   **Exceptions** are unexpected events like bad weather or running out of bricks.
*   **`Except` Blocks** are your contingency plans (e.g., "if it rains, cover the wood").
*   The **`Else` Block** is the final sign-off and celebration when the house is built perfectly without any accidents.
*   The **`Finally` Block** is the cleanup: regardless of whether you finished the house or had to stop due to a storm, you must always clean up the site and return your rented tools.