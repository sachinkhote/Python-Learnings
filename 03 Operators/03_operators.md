# Summary: Operators in Python

This document summarizes the key concepts regarding operators in programming, focusing on their types, usage, order of operations, and related constraints.

## 1. Overview and Purpose

Operators are programming tools used to execute actions such as adding numbers, comparing values, or assigning values to variables. They are utilized for performing operations on both variables and values.

**Session Objectives:**
*   Understand what operators are and why they are used.
*   Understand the different types of operators.
*   Understand the order of operations followed in Python.
*   Understand constraints in programming language.

## 2. Types of Operators (7 Total)

There are seven main types of operators:
1. Arithmetic Operators
2. Comparison Operators
3. Logical Operators
4. Bitwise Operators
5. Assignment Operators
6. Membership Operators
7. Identity Operators

---

### 2.1. Arithmetic Operators

These are used for mathematical calculations.

| Operator | Description | Example (x=10, y=3) | Output | Source |
| :---: | :--- | :--- | :--- | :--- |
| `+` | Addition (combines two numbers) | `print(x + y)` | `13` | |
| `-` | Subtraction (finds the difference) | `print(x - y)` | `7` | |
| `*` | Multiplication | `print(x * y)` | `30` | |
| `/` | Division (floating-point division, quotient may include decimals) | `print(x / y)` | `3.333...` | |
| `%` | Modulus (gives the remainder) | `print(x % y)` | `1` | |
| `**` | Exponentiation (raises a number to a power) | `print(x ** y)` | `1000` | |
| `//` | Floor Division (divides and rounds down to the nearest whole number) | `print(x // y)` | `3` | |

### 2.2. Comparison Operators

These compare two values or expressions and return a Boolean value (`True` or `False`).

| Operator | Description | Example (x=5, y=10) | Output | Source |
| :---: | :--- | :--- | :--- | :--- |
| `==` | Equal to (checks if values are equal) | `print(x == y)` | `False` | |
| `!=` | Not equal to (checks if values are not equal) | `print(x != y)` | `True` | |
| `>` | Greater than | `print(x > y)` | `False` | |
| `<` | Less than | `print(x < y)` | `True` | |
| `>=` | Greater than or equal to | `print(x >= y)` | `False` | |
| `<=` | Less than or equal to | `print(x <= y)` | `True` | |

### 2.3. Logical Operators

These combine multiple conditional statements, allowing decisions based on the outcome of multiple conditions.

| Operator | Description | Example (x=5, y=10, z=15) | Output | Source |
| :---: | :--- | :--- | :--- | :--- |
| `and` | Returns `True` if **both** operands are `True` | `print(x < y and y < z)` | `True` | |
| `or` | Returns `True` if **at least one** operand is `True` | `print(x < y or x > z)` | `True` | |
| `not` | Returns the **opposite** Boolean value | `print(not(x < y))` | `False` | |

### 2.4. Bitwise Operators

These perform operations on individual binary digits (bits) of numbers.

| Operator | Description | Source |
| :---: | :--- | :--- |
| `&` | Bitwise AND (sets bit to 1 if both corresponding bits are 1) | |
| `|` | Bitwise OR (sets bit to 1 if at least one corresponding bit is 1) | |
| `^` | Bitwise XOR (sets bit to 1 if **only one** corresponding bit is 1) | |
| `~` | Bitwise NOT (flips the bits) | |
| `<<` | Left shift (shifts bits left, filling vacated positions with zeros) | |
| `>>` | Right shift (shifts bits right) | |

### 2.5. Assignment Operators

These are used to assign values to variables, often combining an operation with an assignment.

| Operator | Example | Same As | Source |
| :---: | :---: | :---: | :---: |
| `=` | `x = 5` | `x = 5` | |
| `+=` | `x += 2` | `x = x + 2` | |
| `-=` | `x -= 2` | `x = x - 2` | |
| `*=` | `x *= 2` | `x = x * 2` | |
| `/=` | `x /= 2` | `x = x / 2` | |
| `%=` | `x %= 2` | `x = x % 2` | |
| `//=` | `x //= 2` | `x = x // 2` | |
| `**=` | `x **= 2` | `x = x ** 2` | |

### 2.6. Membership Operators

These test whether a value or variable is found within a sequence (like strings, lists, tuples, sets, or dictionaries).

| Operator | Description | Source |
| :---: | :--- | :--- |
| `in` | Returns `True` if the value exists in the sequence. | |
| `not in` | Returns `True` if the value does not exist in the sequence. | |

*Example:* `print('a' in 'banana')` outputs `True`.

### 2.7. Identity Operators

These compare the memory locations of two objects to check if they are the exact same object.

| Operator | Description | Source |
| :---: | :--- | :--- |
| `is` | Returns `True` if both operands point to the same object. | |
| `is not` | Returns `True` if both variables are not the same object. | |

*Tip: The `id()` function can be used to check the memory address of objects.*

## 3. Order of Operations in Python

Python follows the standard mathematical convention (PEMDAS or BODMAS). The precedence order, starting with the highest, is crucial for evaluating complex expressions.

| Precedence Rank | Operator | Description | Source |
| :---: | :--- | :--- | :--- |
| **Highest** | `()` | Parentheses/Brackets (evaluated first) | |
| **2** | `+x`, `-x`, `~x` | Unary plus, unary minus, and bitwise NOT | |
| **3** | `**` | Exponentiation | |
| **4** | `*`, `/`, `//`, `%` | Multiplication, division, floor division, and modulus (performed left to right) | |
| **5** | `+`, `-` | Addition and subtraction (performed left to right) | |
| **6** | `<<`, `>>` | Bitwise left and right shifts | |
| **7** | `&` | Bitwise AND | |
| **8** | `^` | Bitwise XOR | |
| **9** | `|` | Bitwise OR | |
| **10** | Comparison, Identity, Membership | `==`, `!=`, `>`, `>=`, `<`, `<=`, `is`, `is not`, `in`, `not in` (evaluated after arithmetic/bitwise operations) | |
| **11** | `not` | Logical NOT (highest logical precedence) | |
| **12** | `and` | Logical AND | |
| **Lowest** | `or` | Logical OR | |

## 4. Related Built-in Functions

Operators are used internally in some Python built-in functions:

1.  **`divmod(a, b)`:** Takes two numbers (`a`: dividend, `b`: divisor) and returns a tuple containing the quotient and the remainder.
    *   *Example:* `divmod(17, 3)` outputs `(5, 2)`.
2.  **`round(number, digits)`:** Rounds a floating-point number. If `digits` is not provided, it rounds to the nearest integer.
    *   *Example:* `round(12.5678, 2)` outputs `12.57`.

## 5. Constraints in Programming

Constraints are limitations or restrictions applied to variables, data structures, and data types. They are essential for solving problems, handling time constraints, and optimization.

*   **Variable Constraints:** Specify acceptable ranges for variable values (e.g., `1 <= num1 <= 100`).
*   **Data Structure Constraints:** Specify acceptable ranges for elements within a structure (e.g., `list` values must be in the range of -10^5 to 10^5).

---

## 💡 Notes and Tips

### General Tips

*   **Left-to-Right Evaluation:** When operations share the same precedence level (like Multiplication/Division or Addition/Subtraction), they are evaluated from left to right.
*   **Bitwise Operators:** While covered, bitwise operators are noted as not being extensively relevant in this session.

### Avoiding Errors (Type Coercion)

*   **Division Result:** The division operator (`/`) **always produces a floating-point number** as the result, even if both operands are integers.
*   **Incompatible Types:** Mixing incompatible data types (e.g., trying to add an `int` and a `str`) will result in a `TypeError`.
    *   *Example:* `10 + "20"` results in `TypeError`.
*   **String Limitations:** The subtraction operation (`-`) is explicitly **not defined for strings**, and attempting it will result in a `TypeError`.

### Understanding Logical Operators (`and`, `or`)

*   **Precedence:** Within logical operations, `not` has the highest precedence, followed by `and`, and then `or`.
*   **Truthiness in `and`:** In an expression like `2 and 3`, if both operands are non-zero (truthy), the result of the `and` operation is the **second operand** (3).
*   **Truthiness in `or`:** In an expression like `1 or 3`, the `or` operator returns the **first operand** if it evaluates to `True` (truthy), otherwise it returns the second operand. Since 1 is truthy, the result is 1.