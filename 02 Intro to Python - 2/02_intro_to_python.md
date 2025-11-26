# Chapter 2: Python Basics - Syntax, Variables, and Data Types

This chapter covers the "how" of Python, focusing on the fundamental syntax, storing information in variables, and understanding the different types of data you'll be working with.

---

## Python's Basic Syntax 

These are the foundational commands and rules for writing Python code.

### The `print()` Function

The `print()` function is used to display output on the screen[cite: 110].

* You can print multiple items by separating them with a comma[cite: 114].
* **`end` parameter**: By default, `print()` adds a new line at the end[cite: 131]. You can change this with the `end` parameter to specify what should be printed at the end of the output[cite: 128, 137]. For example, `end=' '` will add a space instead of a new line[cite: 139, 142].
* **`sep` parameter**: This allows you to specify a separator for multiple values passed to the `print()` function, like `sep=','`[cite: 150, 152, 154].

### The `input()` Function

The `input()` function pauses your program and waits to accept input from the user via the keyboard[cite: 159].

* **Important**: The `input()` function always reads the user's input as a **string** data type by default, even if they type numbers[cite: 161].

> #### Pro-Tip
> A very common error for beginners is trying to do math with a value from `input()`. You must first convert the input string to a number before performing calculations. We'll cover this in "Type Conversion" below.

### Comments

Comments are used to explain what code does, making it easier to understand[cite: 178]. They are ignored by Python[cite: 181].

* **Single-line comments**: Start with a `#` symbol[cite: 181].
* **Multi-line comments**: Are enclosed in triple quotes (`"""..."""` or `'''...'''`)[cite: 184].

### Indentation

Indentation refers to the spaces at the beginning of a code line. In Python, it's a strict rule used to define the structure of code blocks[cite: 191]. Other languages might use curly braces `{}` for this, but Python uses indentation[cite: 192].

> #### Pro-Tip
> The standard and most recommended convention for indentation is **four spaces**. Consistent indentation is mandatory to avoid errors and is a key part of what makes Python code so readable.

---

## Variables 

Variables are like containers used to store data or information in your program that can be accessed and manipulated later[cite: 204].

### Declaring and Assigning Variables

In Python, a variable is created the moment you first assign a value to it [cite: 215]; there is no separate command for declaring variables[cite: 213].

```python
# The variable 'user_name' is created and assigned the value "John"
user_name = "John" # [cite: 225]

# The variable 'score' is created and assigned the value 42
score = 42 # [cite: 216].  
```

## Data Types (Complete Details)

Data types define the nature of the data a variable can hold[cite: 313]. You can check a variable's type using the `type()` function.

---  

### Numbers

Python supports several types of numbers:
* **Integers (`int`)**: Whole numbers without a decimal point[cite: 320]. Example: `x = 10`[cite: 324].
* **Floating Point Numbers (`float`)**: Real numbers that have a decimal point[cite: 320]. Example: `y = 3.14`[cite: 325].
* **Complex Numbers (`complex`)**: Numbers with both a real and an imaginary part[cite: 321]. Example: `z = 2 + 3j`[cite: 326].

---

### Strings (`str`)

Strings are sequences of characters enclosed in quotes[cite: 328]. They are **immutable**, meaning they cannot be changed after they are created[cite: 329].

#### Handling Quotes in Strings

You can run into errors if you use the same type of quote inside a string as you do to enclose it[cite: 333, 336]. Here are the solutions:

1.  **Use Different Outer Quotes**: If your string contains single quotes, enclose it in double quotes, and vice-versa[cite: 337].
    `print("She is Ana's sister")` [cite: 338]
2.  **Use the Backslash (`\`) Escape**: The backslash tells Python that the quote following it is part of the string, not the end of it[cite: 343].
    `print('She is Ana\'s sister')` [cite: 344]
3.  **Use Triple Quotes (`"""..."""`)**: These are useful for multi-line strings and allow you to use both single and double quotes inside without needing a backslash[cite: 350, 354].
    `print("""She is Ana's sister. She said "Hi!".""")`

#### Escape Characters

These are special characters used to format strings:
* **`\n` (Newline)**: Inserts a line break, moving the subsequent text to a new line[cite: 356].
* **`\t` (Tab)**: Inserts a tab character, which is useful for aligning text into columns[cite: 364, 365].

---

### Booleans (`bool`)

Booleans represent one of two values: `True` or `False`[cite: 379].

The `bool()` function can be used to evaluate any value[cite: 382]:
* **Empty values evaluate to `False`**: Examples include `0`, an empty string `""`[cite: 383].
* **Non-empty values evaluate to `True`**: Examples include any number other than 0 or any non-empty string like `"Hello"`[cite: 384].

---

### Collection Data Types

The PDF also mentions other data types that are used to store multiple items in a single variable. These will be covered in detail later in your course[cite: 392]:
* List
* Tuple
* Set
* Dictionary