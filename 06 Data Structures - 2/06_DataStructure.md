## Python Data Structures Summary: Sets and Dictionaries

### I. Session Overview

This session focuses on understanding sets and dictionaries, including their common methods and operations, and comparing them against lists and tuples.

### II. Sets

A set in Python is an unordered, changeable (mutable) collection that does not allow duplicate elements. It is unindexed and can store items of different data types in a single variable.

#### Key Properties of Sets

| Property | Description | Source |
| :--- | :--- | :--- |
| **Order** | Unordered: Sets do not maintain the order of elements as they are added. | |
| **Mutability** | Changeable (Mutable): Elements can be added or removed. **However**, the elements themselves must be immutable (e.g., lists cannot be elements of a set). | |
| **Indexing** | Unindexed: Cannot access elements using indices. | |
| **Duplicates** | Not Allowed: Only unique elements are maintained. Duplicate values are automatically removed during creation. | |

***Tip/Note: Duplicate Handling***
When creating sets, note that the boolean value `False` and the integer value `0` are considered the same, as they share the hash value of 0. Similarly, `True` and `1` are compared based on their numeric equivalents.

#### Creating Sets

Sets are created using curly braces `{}` with elements separated by commas, or by using the `set()` constructor.

| Method | Example | Source |
| :--- | :--- | :--- |
| Curly Braces | `set2 = {1, 2, 3}` | |
| Empty Set | `set1 = set()` (Note: `s = {}` creates an empty dictionary, not a set) | |
| Constructor | `my_set = set(my_list)` (Converts lists, tuples, or strings) | |

#### Common Set Methods and Operations

| Category | Method/Operator | Description | Source |
| :--- | :--- | :--- | :--- |
| **Access/Info** | `len()` | Determines the number of items. | |
| | `in`, `not in` | Membership operators used to check if an item exists. | |
| | `min()`, `max()`, `sum()` | Finds the minimum, maximum, or sum (for numeric elements). | |
| **Adding** | `add(element)` | Adds a single element. | |
| | `update(iterable)` | Adds multiple elements from an iterable (ignores duplicates). | |
| **Removing** | `remove(element)` | Removes the element; **raises `KeyError` if not found**. | |
| | `discard(element)` | Removes the element if present; **does nothing if not found**. | |
| | `pop()` | Removes and returns an arbitrary element (position is not guaranteed). | |
| | `clear()` | Removes all elements, resulting in an empty set. | |
| **Joining/Logic** | `union()` or `\|` | Returns a new set with all elements from both sets. | |
| | `intersection()` or `&` | Returns a new set with only common elements. | |
| | `difference()` or `-` | Returns a new set with elements present in the first set but not the second. | |
| | `symmetric_difference()` or `^` | Returns a new set with elements present in either set, but not both. | |
| **In-Place Updates** | `difference_update()` or `-=` | Removes items from the original set that are present in the specified set(s). | |
| | `intersection_update()` or `&=` | Keeps only items in the original set that are also present in the specified set(s). | |
| | `symmetric_difference_update()` or `^=` | Removes items present in both, and inserts items not present in both. | |
| | `update()` or `\|=` | Modifies the original set by inserting items from the other set(s). | |
| **Comparison** | `isdisjoint()` | Returns `True` if two sets have no common elements. | |
| | `issubset()` or `<=` | Returns `True` if all elements of the first set are in the second. | |
| | `issuperset()` or `>=` | Returns `True` if all elements of the second set are in the first. | |
| **Copying** | `copy()` or `set()` | Creates a shallow copy of the set. | |

***Notes: Returning vs. Updating Methods***
*   Original methods (e.g., `union()`, `difference()`) return a **new set** containing the result without modifying the original set.
*   Update methods (e.g., `difference_update()`) modify the **original set directly** to reflect the result of the operation.

### III. Dictionaries

A dictionary in Python is an unordered, changeable (mutable) collection of key-value pairs. Each key must be unique, although the values can be duplicated.

#### Key Properties of Dictionaries

| Property | Description | Source |
| :--- | :--- | :--- |
| **Order** | Unordered collection of items. | |
| **Mutability** | Mutable: Elements (values) can be modified, added, or removed after creation. | |
| **Keys** | Must be Unique: If duplicate keys are defined, only the last occurrence is stored. Keys must be immutable (e.g., tuples are valid keys). | |
| **Values** | Can be Duplicated. | |

#### Creating Dictionaries

Dictionaries are defined using curly braces `{}`, with key-value pairs separated by colons `:`.

| Method | Example | Source |
| :--- | :--- | :--- |
| Curly Braces | `my_dict = {"name": "John", "age": 30}` | |
| Constructor | `thisdict = dict(name = "John", age = 36)` | |
| From Iterables | `dict(zip(keys, values))` (using the `zip()` function). | |
| Nested | A dictionary can contain dictionaries. | |

#### Common Dictionary Methods and Operations

| Category | Method/Operator | Description | Source |
| :--- | :--- | :--- | :--- |
| **Access/Info** | `len()` | Determines the number of items (key-value pairs). | |
| | `my_dict[key]` | Accesses value by key; **raises `KeyError` if key does not exist**. | |
| | `get(key, default)` | Accesses value by key; returns `None` or a custom default value if the key does not exist. | |
| | `keys()` | Returns a view object of all keys. | |
| | `values()` | Returns a view object of all values. | |
| | `items()` | Returns a view object displaying a list of tuples (key-value pairs). | |
| | `min()`, `max()`, `sum()` | Applied to `values()` to find min, max, or sum of numeric values. | |
| **Adding/Updating** | Direct Assignment | If key exists, updates value; if key doesn't exist, adds new key-value pair. | |
| | `update(iterable)` | Updates the dictionary with items from an iterable (or another dictionary); adds item if the key does not exist. | |
| | `setdefault(key, default)` | Retrieves the value if the key exists; if not, inserts the key with the default value (or `None`) and returns that value. | |
| | `fromkeys(iterable, value)` | Creates a new dictionary with keys from the iterable and all values set to the default value (defaulting to `None`). | |
| **Removing** | `del my_dict[key]` | Deletes the item with the specified key, or deletes the dictionary entirely. | |
| | `pop(key)` | Removes the item with the specified key and returns its value. **Requires a key argument**. | |
| | `popitem()` | Removes and returns the last inserted key-value pair as a tuple. | |
| | `clear()` | Removes all items from the dictionary. | |
| **Copying** | `copy()` or `dict()` | Creates a shallow copy. | |

***Tip/Note: Accessing Missing Keys***
Always use the `.get()` method for accessing dictionary elements if you are unsure if a key exists, as it prevents a `KeyError` exception.

### IV. Comparison of Data Structures

This table summarizes the core differences between Lists, Tuples, Sets, and Dictionaries.

| Feature | Lists | Tuples | Sets | Dictionaries | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Definition** | Ordered collection of items | Ordered collection of items | Unordered collection of unique items | Unordered collection of key-value pairs | |
| **Mutability** | Changeable (Mutable) | Unchangeable (Immutable) | Changeable (Mutable) | Changeable (Mutable) | |
| **Indexing** | Supports indexing and slicing | Supports indexing and slicing | Does not support indexing | Supports key-based access | |
| **Duplication** | Allowed | Allowed | Not Allowed | Keys must be unique; Values allowed | |
| **Syntax** | Square brackets `[]` | Parentheses `()` | Curly braces `{}` | Curly braces `{}` | |
| **Performance** | Slower than sets/dicts for lookups | Faster than lists for iteration; slower for lookups | Fastest for membership tests | Fast key-based access | |
| **Use Case** | When order matters | When data should not change | When uniqueness is required | When data needs to be stored with keys | |

***Tip/Note: Copying Mutability***
When copying data structures:
*   Using assignment (`copied = original`) for dictionaries results in a reference. Changes to the "copied" object affect the "original".
*   Use `copy()` or the constructor (`set()`, `dict()`) to create a shallow copy, ensuring that changes to the copy do not affect the original (unless nested mutable objects are involved).

***

**Analogy for Understanding Set Operations:**

Think of sets like circles in a **Venn Diagram**:
*   **Union** is pouring all contents of all circles into one big container.
*   **Intersection** is finding the specific overlapping area where all circles meet.
*   **Difference** is taking everything in Circle A, and physically cutting out any part that overlaps with Circle B.
*   **Symmetric Difference** is taking everything in all circles, but throwing away the parts where any of them overlap.