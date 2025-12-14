
## Python Looping Statements: Interview Revision Guide

### I. Looping Overview (Automation and Repetition)

Looping statements are fundamental to Python programming, enabling a block of code to be executed repeatedly **until a specific condition is met**. This automation is crucial, as it prevents the need for manual repetition, which would be "extremely tedious and time-consuming" for batch processes.

Python provides two primary looping structures:
1.  **`for` loops**
2.  **`while` loops**

***

### II. For Loops: Iterating Over Sequences

The `for` loop is used to iterate over iterable objects, such as lists, tuples, strings, or ranges. It acts like a process that takes each item from a sequence one by one. The loop executes a set of statements once for each item in the sequence. Importantly, the `for` loop **does not require an indexing variable to be set beforehand**.

#### 1. Standard For Loop Syntax and Iteration

| Concept | Syntax/Code Example | Output & Explanation |
| :--- | :--- | :--- |
| **Basic Syntax** | `for item in sequence:`<br>` # code block` | The loop variable (`item`) is assigned the current element in each iteration. |
| **Iterating a List** | `fruits = ["apple", "banana", "cherry"]`<br>`for fruit in fruits:`<br>` print(fruit)` | `apple`<br>`banana`<br>`cherry` |
| **Iterating a String** | `greeting = "Hello, World!"`<br>`for char in greeting:`<br>` print(char)` | Prints each character of the string vertically. |
| **Conditional Logic** | `numbers = [1, 2, ..., 10]`<br>`for num in numbers:`<br>` if num % 2 == 0: print(f"{num} is even")`<br>` else: print(f"{num} is odd")` | `1 is odd`, `2 is even`, etc.. The loop checks the condition for *each* item. |
| **List Manipulation** | `my_list = []`<br>`items =`<br>`for item in items: my_list.append(item)` | ``. Demonstrates appending elements from one list to another. |
| **Algorithm Example** | *Find largest element:*<br>`numbers =`<br>`max_element = numbers`<br>`for num in numbers:`<br>` if num > max_element: max_element = num` | `Largest element: 40`. |
| **Algorithm Example** | *Remove duplicates from string:*<br>`input_string = "AABBBBCCCCDDDD"`<br>`unique_chars = ""`<br>`for char in input_string:`<br>` if char not in unique_chars: unique_chars += char` | `String with duplicates removed: ABCD`. |

#### 2. The `range()` Function

The `range()` function is used to loop a specified number of times. It returns a sequence of numbers, starting at 0 by default, and stopping **before** the specified end number.

| Function Signature | Code Example | Output & Explanation |
| :--- | :--- | :--- |
| `range(stop)` | `for i in range(5): print(i)` | `0, 1, 2, 3, 4` (Starts at 0, increments by 1). |
| `range(start, stop)` | `for i in range(2, 5): print(i)` | `2, 3, 4` (Starts at 2, stops before 5). |
| `range(start, stop, step)` | `for i in range(2, 10, 2): print(i)` | `2, 4, 6, 8` (Increments by 2). |
| **Descending Order** | `for i in range(5, 2, -1): print(i)` | `5, 4, 3` (Requires a **negative step value**). |

#### 3. Advanced For Loop Features

| Feature | Code Example | Explanation |
| :--- | :--- | :--- |
| **`enumerate()`** | `fruits = ["apple", "banana", "cherry"]`<br>`for index, fruit in enumerate(fruits):`<br>` print(index, fruit)` | Output: `0 apple`, `1 banana`, `2 cherry`. Used to retrieve **both the index and the value** during iteration. |
| **`else` Clause** | `for x in range(6): print(x)`<br>`else: print("Finished!")` | The `else` block executes **only after the loop completes normally** (after all iterations finish). |
| **Nested For Loops** | `for i in range(1, 6):`<br>` for j in range(1, 11): print(i * j, end="\t")` | Used for multi-dimensional data. The **inner loop completes all its iterations** for every single iteration of the outer loop. |
| **Matrix Traversal** | `matrix = [,]`<br>`for row in matrix:`<br>` for element in row: print(element)` | Iterates over rows first (outer loop), then elements within each row (inner loop). |

#### 4. Shorthand: Comprehensions and Generators

While there is no specific "shorthand" syntax for the standard `for` loop, list comprehensions and generator expressions offer concise ways to create iterables.

| Type | Syntax Example | Output & Purpose |
| :--- | :--- | :--- |
| **List Comprehension** | `squares = [x ** 2 for x in range(1, 11)]` | Output: `[1, 4, 9, 16, 25, ... 100]`. Combines the `for` loop and an expression into a single, compact line to create a new list. |
| **List Comprehension w/ Condition** | `even_numbers = [x for x in range(1, 21) if x % 2 == 0]` | Output: `[2, 4, 6, ..., 20]`. The `if` condition filters the results. |
| **Generator Expression** | `squares_generator = (x**2 for x in range(5))` | Output: `<generator object ...>`. Uses parentheses `()`. Creates an **iterator** that generates values one by one (lazy execution). Generators are **more memory-efficient** for large datasets. **Note:** A generator can be consumed only once. |

***

### III. While Loops: Conditional Repetition

`While` loops are used to repeatedly execute a block of code **as long as a specified condition is true**. They are ideal for scenarios where the required number of iterations is **unknown beforehand**.

#### 1. While Loop Syntax and Mechanics

| Concept | Syntax/Code Example | Key Requirement & Explanation |
| :--- | :--- | :--- |
| **Basic Syntax** | `while condition:`<br>` # Code block` | The condition is evaluated *before* the code block executes. The loop terminates only when the condition becomes `False`. |
| **Basic Example** | `num = 1`<br>`while num <= 5:`<br>` print(num)`<br>` num += 1` | **Initialization (num = 1)** is essential for the loop condition to be evaluated. **Iteration Control (num += 1)** is necessary to ensure the condition eventually becomes false, preventing an **infinite loop**. |
| **Example Output** | (From above example) | `Current number is: 1` through `5`<br>`Loop finished!` |
| **Iterating with Index** | `iterable =`<br>`index = 0`<br>`while index < len(iterable):`<br>` print(iterable[index])`<br>` index += 1` | This demonstrates using a `while` loop to iterate over an iterable object using an explicit index. |
| **Counting Down** | `countdown = 10`<br>`while countdown >= 0:`<br>` print(countdown)`<br>` countdown -= 1` | Uses **decrementing** (`countdown -= 1`) to ensure the loop terminates when `countdown` falls below 0. |
| **`else` Clause** | `i = 1`<br>`while i < 6: print(i); i += 1`<br>`else: print("i is no longer less than 6")` | The `else` block executes **once** when the `while` loop's condition becomes false. |

#### 2. Potential Errors (Infinite Loops)

Failure to manage the control variable properly is the most common pitfall of `while` loops:

| Error Type | Example Scenario | Result |
| :--- | :--- | :--- |
| **Missing Initialization** | `while value < 5: ...` (if `value` is not defined) | **`NameError`**. Python cannot evaluate the condition. |
| **No Iteration Control** | `count = 0; while count < 5: print("Count is still less than 5")` | **Infinite Loop**. The condition never becomes false, consuming resources and making the program unresponsive. |
| **Incorrect Iteration Control** | `num = 5; while num >= 0: num += 1` | **Infinite Loop**. Since `num` starts at 5 and is incremented, it never decreases to terminate the loop. |

To stop a running infinite loop, you can use **Ctrl + C** (Keyboard Interrupt) in the terminal.

#### 3. Nested While Loops

Nested `while` loops involve one `while` loop inside another. The inner loop completes all its iterations for every single iteration of the outer loop.

| Concept | Code Example (Structure) | Explanation |
| :--- | :--- | :--- |
| **Nested Structure** | `outer_count = 0`<br>`while outer_count < 3:`<br>` print("Outer loop:", outer_count)`<br>` inner_count = 0`<br>` while inner_count < 2:`<br>`  print("Inner loop:", inner_count)`<br>`  inner_count += 1`<br>` outer_count += 1` | The inner loop (`inner_count < 2`) runs twice for each iteration of the outer loop (`outer_count < 3`). |