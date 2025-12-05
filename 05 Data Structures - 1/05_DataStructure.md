# Summary: Data Structures I (Lists and Tuples)

This document summarizes the definitions, usage, operations, and constraints of basic data structures in Python, specifically focusing on Lists and Tuples.

## 1. Data Structures Overview

Data structures are systematic ways to organize and store data in a computer, enabling efficient use and manipulation.

### 1.1. Why We Use Data Structures:
*   **Organization:** Helps arrange data neatly, making it easier to find and work with.
*   **Efficiency:** Using the correct structure can make programs run faster and smoother.
*   **Memory Management:** Ensures effective use of computer memory, preventing waste.
*   **Flexibility & Abstraction:** Allows programs to be versatile by handling various data types and hiding complicated storage details.
*   **Scalability:** Enables programs to handle increasing amounts of data without slowing down.

### 1.2. Common Python Data Structures:
Python has four common built-in data structures:
1.  **Lists:** Ordered, mutable collections of items.
2.  **Tuples:** Ordered, **immutable** collections of items.
3.  **Sets:** Unordered collections of unique items (mutable).
4.  **Dictionaries:** Unordered collections of key-value pairs (mutable).

---

## 2. Lists

Lists are one of the most versatile and commonly used data structures in Python. They can store a collection of items of different data types in a single variable.

### 2.1. List Characteristics:
*   **Ordered:** Items have a defined order that will not change; new items are placed at the end.
*   **Changeable (Mutable):** Items can be changed, added, or removed after creation.
*   **Allow Duplicates:** Lists can contain items with the same value.
*   **Creation:** Created using square brackets `[]`. The `list()` constructor can also convert other iterables (like tuples or strings) into a list.
*   **Nested Lists:** A list can contain another list as an element.

### 2.2. Accessing and Modifying Lists:

| Operation | Method / Technique | Description | Source |
| :--- | :--- | :--- | :--- |
| **Access Items** | Indexing or Slicing (`my_list[index]`, `my_list[start:end:step]`) | Uses zero-based or negative indexing. | |
| **Get Length** | `len(my_list)` | Returns the total count of elements. | |
| **Change Value** | Direct assignment (`my_list[index] = new_value`) | Assigns a new value to a specific index. | |
| **Change Range** | Slicing assignment (`thislist[1:3] = ["new_values"]`) | Changes the value of items within a range. | |
| **Add Single Item** | `list.append(item)` | Adds a single element to the end. | |
| **Add Multiple Items** | `list.extend(list1)` | Adds the contents of another iterable to the end of the list. | |
| **Insert at Index** | `list.insert(index, item)` | Inserts a single element at a specified position. | |
| **Concatenation** | `new_list = list1 + list2` | Joins two lists, creating a new list. | |
| **Replication** | `list1 * 3` | Repeats the list a specified number of times. | |

### 2.3. Removing List Items:

| Method | Behavior | Effect on List | Source |
| :--- | :--- | :--- | :--- |
| **`remove(value)`** | Removes the **first occurrence** of the specified value. | Modifies the list in place. | |
| **`pop([index])`** | Removes and returns the element at the specified index. If no index is given, it removes the last item. | Modifies the list in place. | |
| **`del` Statement** | Removes the element(s) at the specified index or range. `del list` removes the entire list object. | If used on the entire list, results in a `NameError` upon subsequent access. | |
| **`clear()`** | Empties the list. The list object remains but has no content. | Modifies the list in place. | |

### 2.4. Other Essential List Methods:

| Method | Description | Source |
| :--- | :--- | :--- |
| **`sort()`** | Sorts the list alphanumerically and ascending by default. Use `reverse=True` for descending order. Case-sensitive by default. | |
| **`reverse()`** | Reverses the order of elements in the list. | |
| **`count(element)`** | Determines how many times a specific element appears in the list. | |
| **`index(element)`** | Returns the index of the **first occurrence** of the element. Raises `ValueError` if the element is not found. | |
| **`copy()`** | Creates a shallow copy of the list. | |
| **Slicing Copy** | `copied_list = original_list[:]` also creates a shallow copy. | |

---

## 3. Tuples

A tuple is an ordered collection of elements similar to a list, but they are **immutable**.

### 3.1. Tuple Characteristics:
*   **Ordered:** Items have a defined order.
*   **Immutable (Unchangeable):** Elements cannot be modified, added, or removed after creation.
*   **Allow Duplicates:** Tuples can have items with the same value.
*   **Creation:** Created using parentheses `()` separated by commas, or simply by separating elements with commas without parentheses. The `tuple()` constructor can also be used.

### 3.2. Tuple Operations and Constraints:

| Operation | Method / Constraint | Result or Example | Source |
| :--- | :--- | :--- | :--- |
| **Single Item** | Requires a trailing comma. | `my_tuple = (1,)`. Without the comma, it is treated as the item's type (e.g., `str` or `int`). | |
| **Access Items** | Indexing or Slicing, similar to lists. | `_tuple[1:4]` returns a portion. | |
| **Immutability Workaround** | Convert to list, modify, then convert back to tuple. | `y = list(thistuple); y.append("orange"); thistuple = tuple(y)`. | |
| **Mutable Exception** | If a **list** is an element within a tuple, the list's contents can be modified. | `my_tuple = (1, 2,); my_tuple.append(5)`. | |
| **Replication** | Use the `*` operator. | `my_tuple * 3`. | |
| **Combining** | Use the `+` operator, which only works with other tuples. | Cannot directly add an integer to a tuple. | |
| **Unpacking** | Assigning elements to separate variables. An asterisk `*` gathers remaining values into a list variable. | `a, *b, c = my_tuple`. | |
| **Deletion** | Cannot delete individual elements (`del my_tuple[index]`), but `del my_tuple` deletes the entire tuple object. | |

---

## 4. Comparisons and Utility Functions

### 4.1. Lists vs. Tuples Comparison:

| Feature | Lists | Tuples | Source |
| :--- | :--- | :--- | :--- |
| **Mutability** | Mutable (Changeable). | Immutable (Unchangeable). | |
| **Syntax** | Square brackets `[ ]`. | Parentheses `( )`. | |
| **Performance** | Slightly slower due to mutability (requires more memory operations). | Generally faster due to fixed, constant elements. | |
| **Memory** | May consume more memory over time as elements are added/removed. | Fixed size, occupies a constant amount of memory. | |

### 4.2. Comparison Operators (`==`, `<`, etc.)
When comparing lists or tuples element-wise, comparison proceeds from left to right:
*   If corresponding elements are equal, Python checks the next pair.
*   If one list/tuple is a prefix of the other, the shorter one is considered less.
*   The comparison requires elements to have compatible types; for instance, `` is not equal to `['1', '2', '3']` because the types (integer vs. string) are different.

### 4.3. The `map()` Function
The `map()` function applies a given function to all items in an iterable (like a list or tuple) and returns a map object (an iterator).

*   **Syntax:** `map(function, iterable)`.
*   It is often used to convert string inputs into lists of numeric data types.

---

## 💡 Notes and Tips

### Data Type Specifics

*   **Boolean Values in Math:** When using `min()`, `max()`, or `sum()` on lists/tuples containing mixed numeric and boolean types, **`False` is equivalent to 0** and **`True` is equivalent to 1**.
*   **Non-Numeric Sum:** The `sum()` function can only be used with iterables that contain numeric types (integers or floats).
*   **Sorting Strings:** The `sort()` method on strings is case sensitive; capital letters are sorted before lowercase letters based on their character values. To enforce case-insensitivity, use the `key = str.lower` argument.

### Common Errors and Constraints

*   **List Slicing Constraint:** If the starting index in slicing comes after the ending index (e.g., `letters[-1:-3]`), Python returns an **empty list** `[]`.
*   **Tuple Immutability:** You cannot use `append()`, `remove()`, or `del` on individual elements of a tuple because they are immutable.
*   **Concatenation Type:** When combining lists or tuples using `+`, the operands **must be of the same iterable type** (e.g., tuple + tuple, or list + list). Attempting to concatenate a tuple and an integer raises a `TypeError`.
*   **Index Error:** The `index()` method for both lists and tuples raises a `ValueError` if the specified element is not found.

### Performance Tip

*   **Choose Tuples for Fixed Data:** If you have a collection of data that will **not** change throughout the program's execution (e.g., coordinates, constants), use a **tuple**. Tuples are generally faster and consume less memory than mutable lists, benefiting performance.

*To imagine the difference, think of a List like a whiteboard: you can erase and rewrite content anywhere, which is flexible but takes time and effort to manage the space. A Tuple is like a printed page: it is much faster to read and process because the contents are fixed and cannot be altered.*