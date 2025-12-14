
# Session 7: Conditional Statements in Python

This session provides an overview of control statements, focusing on conditional statements, nested structures, and shorthand notations, based on the material in the sources.

---

## 1. Control Statements Overview

Control statements in Python act like **traffic signals for your code**, determining which sections of the program should execute and when.

### Types of Control Statements
The sources identify three main types of control statements in Python:

1.  **Conditional Statements** (`if`, `elif`, `else`): Used to execute different code blocks depending on whether a specific condition is true or false.
2.  **Looping Statements** (`for`, `while`): Used to repeat a block of code.
3.  **Control Transfer Statements** (`break`, `continue`, `pass`): Used to alter the flow of execution, often within loops or conditional statements.

### Importance of Control Statements
Control statements are essential for effective programming because they enable several core functionalities:

*   **Making Decisions:** Statements like `if`, `else`, and `elif` allow the program to perform one action if a condition is true and a different action if it is false.
*   **Repeating Tasks:** Loops automate repetitive tasks or process large data amounts by allowing certain actions to be performed multiple times without redundant code.
*   **Handling Exceptions:** They help manage exceptional situations, such as errors or unexpected events, ensuring the program runs smoothly.
*   **Creating Algorithms:** Many problem-solving techniques and algorithms—like searching or sorting—depend on control statements to manage the execution flow and make step-by-step decisions.

---

## 2. Conditional Statements

Conditional statements execute different blocks of code based on conditions. The primary conditional statement is the `if` statement, which can be supplemented with `elif` and `else` for default actions and additional conditions. **Indentation (`:`)** is crucial in Python to define the structure of these code blocks.

### The `if` Statement
The `if` statement runs a code block only if a specified condition evaluates to **True**.

| Feature | Description |
| :--- | :--- |
| **Syntax** | `if condition:` or `if (condition):` |
| **Execution** | If the condition is true, the indented code block immediately following `if` is executed. If false, the block is skipped. |
| **Boolean Context** | The condition can be any expression resulting in `True` or `False`. In Python, any non-zero number is considered `True`, while **zero is considered `False`** in a boolean context. |

***Example of `if` skipping the block***:
```python
x = -5
if x > 0:
    print("x is positive")  # This line is skipped
print("This line is outside the if block")
# Output: This line is outside the if block
```
In this scenario, since the condition `x > 0` (i.e., -5 > 0) is false, the indented code block is skipped, and execution resumes outside the block.

***Syntax Errors to Avoid***:
*   **Missing Indentation:** Python raises an `IndentationError` if the code block following the `if` statement is not indented.
*   **Assignment Operator:** Using the assignment operator (`=`) instead of the comparison operator (`==`) will result in a `SyntaxError` because the `if` statement expects a boolean expression.

### The `if-else` Statement
The `else` statement is an optional part of the `if` structure, allowing a separate block of code to run when the `if` condition evaluates to **False**.

| Feature | Description |
| :--- | :--- |
| **Syntax** | `if condition: # True block else: # False block` |
| **Execution** | If the `if` condition is true, the `if` block executes. If false, the code block following the `else` statement executes. |

***Example***:
```python
x = 10
if x > 15:
    print("x is greater than 15")
else:
    print("x is not greater than 15")
# Output: x is not greater than 15
```
Since 10 is not greater than 15, the condition is false, and the code associated with the `else` statement runs.

### The `if-elif-else` Statement
The `elif` (short for "else if") statement allows evaluation of **multiple conditions sequentially** after the initial `if` statement.

| Feature | Description |
| :--- | :--- |
| **Purpose** | To evaluate multiple conditions and execute a code block based on the *first* condition that is true. |
| **Execution Flow** | The process checks the conditions sequentially until one evaluates to true. Once a condition is true, the corresponding code block is executed, and all subsequent `elif` and `else` blocks are skipped. If all conditions are false, the final `else` block (if present) is executed. |

***Syntax***:
```python
if condition1:
    # Code if condition1 is true
elif condition2:
    # Code if condition1 is false and condition2 is true
elif condition3:
    # Code if condition1 and condition2 are false and condition3 is true
...
else:
    # Code if all conditions are false
```

***Note***: Using `if` and `elif` without an `else` statement is valid if no default action is needed. However, an `elif` statement must always follow an `if` statement; using `elif` alone will result in a `SyntaxError`.

---

## 3. Nested Conditional Statements

Nested statements involve placing one control statement inside another, creating hierarchical conditional logic.

### Nested `if` Statements
A nested `if` statement is an `if` statement placed inside another `if` statement. The inner condition is only checked if the outer condition is true.

***Example***:
```python
x = 10
y = 5
if x > 0:
    print("x is positive")  # Outer condition is true
    if y > 0:
        print("y is positive") # Inner condition is checked and is true
        print("Both x and y are positive")
```

### Nested `if-else` Statements
These involve placing an `if-else` structure within either an outer `if` or an outer `else` block. This allows for further refinement of logic.

If the outer condition is true, the inner `if-else` structure is evaluated. If the outer condition is false, the outer `else` block executes, which may contain another nested `if-else` structure.

### Nested `if-elif-else` Statements
This structure allows for the organization of complex conditional logic.

***Execution Flow***: If the outer `condition1` is true, the inner `if-elif-else` structure is evaluated. If `condition1` is false, the flow moves to the next outer `elif` statement (`condition4`) or the final `else` block.

---

## 4. Shorthand Notations (Ternary Operators)

Shorthand notations are used to simplify conditional statement syntax, resulting in more concise code.

### Shorthand `if` Statement
If only one statement needs to be executed, it can be placed on the same line as the `if` statement.

**Syntax:** `if a > b: print("a is greater than b")`

### Shorthand `if-else` Statement (Ternary Operator)
This technique, also known as **Ternary Operators** or **Conditional Expressions**, is used to assign a value to a variable based on whether a condition is true or false.

**Syntax:** `result = value1 if condition else value2`

***Example***:
```python
x = 10
y = 20
result = x if x > y else y
# Output: result is 20
```
If `x > y` is true, `result` is assigned the value of `x`; otherwise, it is assigned the value of `y`.

### Shorthand `if-elif-else` Statement
While there is no direct shorthand for `if-elif-else`, a similar effect can be achieved using **nested shorthand `if-else` statements**. Python evaluates these expressions from left to right.

**Syntax Example (Conceptual):**
```python
grade = 'A' if score >= 90 else ('B' if score >= 80 else ('C' if score >= 70 else 'D'))
```
This structure checks the conditions sequentially: if `score >= 90` is false, it proceeds to the next nested check (`'B' if score >= 80 else...`).

Alternatively, a simpler nested structure can be written for comparing three variables:
```python
a = 330
b = 330
print("A") if a > b else print("=") if a == b else print("B")
# Output: =
```
This is equivalent to a nested `if-else` structure where the outer `else` contains the secondary `if-else` condition.
```