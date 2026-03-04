# 🐍 Python Learnings

> A structured, self-paced Python learning repository — from absolute basics to data science and beyond.

---

## 📚 Table of Contents

| # | Chapter | Topics Covered |
|---|---------|----------------|
| 01 | [Intro To Python - 1](https://github.com/sachinkhote/Python-Learnings/tree/main/01%20Intro%20To%20Python%20-%201) | Setup, syntax, variables, data types, input/output |
| 02 | [Intro To Python - 2](https://github.com/sachinkhote/Python-Learnings/tree/main/02%20Intro%20to%20Python%20-%202) | Type casting, comments, keywords, naming conventions |
| 03 | [Operators](https://github.com/sachinkhote/Python-Learnings/tree/main/03%20Operators) | Arithmetic, comparison, logical, bitwise, assignment operators |
| 04 | [Strings](https://github.com/sachinkhote/Python-Learnings/tree/main/04%20Strings) | String methods, slicing, formatting, indexing |
| 05 | [Data Structures - 1](https://github.com/sachinkhote/Python-Learnings/tree/main/05%20Data%20Structures%20-%201) | Lists, Tuples — creation, indexing, methods |
| 06 | [Data Structures - 2](https://github.com/sachinkhote/Python-Learnings/tree/main/06%20Data%20Structures%20-%202) | Sets, Dictionaries — operations and methods |
| 07 | [Conditional STMT](https://github.com/sachinkhote/Python-Learnings/tree/main/07%20Conditional%20STMT) | if, elif, else, nested conditions |
| 08 | [Looping Stmt](https://github.com/sachinkhote/Python-Learnings/tree/main/08%20Looping%20Stmt) | for loop, while loop, nested loops |
| 09 | [Control Transfer Stmts](https://github.com/sachinkhote/Python-Learnings/tree/main/09%20Control%20Transfer%20Stmts) | break, continue, pass |
| 10 | [Functions](https://github.com/sachinkhote/Python-Learnings/tree/main/10%20Functions) | def, return, *args, **kwargs, lambda, recursion |
| 11 | [Exception Handling](https://github.com/sachinkhote/Python-Learnings/tree/main/11%20Exception%20Handling) | try, except, finally, raise, custom exceptions |
| 12 | [Modules](https://github.com/sachinkhote/Python-Learnings/tree/main/12%20Modules) | import, built-in modules, custom modules, packages |
| 13 | [File Handling](#13-file-handling) | Read, write, append files; context managers |
| 14 | [NumPy - I](#14-numpy---i) | Arrays, array operations, indexing, slicing |
| 15 | [NumPy - II](#15-numpy---ii) | Mathematical ops, broadcasting, reshaping, aggregations |
| 16 | [Pandas - I](#16-pandas---i) | Series, DataFrames, reading CSV/Excel, basic operations |
| 17 | [Pandas - II](#17-pandas---ii) | Filtering, groupby, merging, joining DataFrames |
| 18 | [Pandas - III](#18-pandas---iii) | Data cleaning, handling nulls, apply, pivot tables |
| 19 | [Matplotlib & Seaborn](#19-matplotlib--seaborn) | Line, bar, pie, scatter plots; heatmaps, pairplots |
| 20 | [OOPs](#20-oops) | Classes, objects, inheritance, polymorphism, encapsulation |
| 21 | [Database Connectivity](#21-database-connectivity) | MySQL/SQLite connection, CRUD operations with Python |
| 🦠 | [Case Study — COVID](#-case-study--covid) | Real-world data analysis using COVID-19 dataset |
| 📝 | [Python Test](#-python-test) | Practice tests and assessments |
| 📅 | [Weekly](#-weekly) | Weekly exercises and revision tasks |


---

## 🛠️ Tools & Libraries Used

| Tool / Library | Purpose |
|----------------|---------|
| Python 3.x | Core language |
| Jupyter Notebook | Interactive coding environment |
| NumPy | Numerical computing |
| Pandas | Data manipulation |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| SQLite / MySQL | Database connectivity |

---

## 🗺️ Expanded Learning Path

### 🟢 Core Python — Chapters 01 to 13

---

#### 📘 Chapter 01 — Intro To Python - 1
- What is Python?
- Python Features (Simple, Interpreted, Open Source, Portable, etc.)
- Python vs Other Languages & Tools (Java, R, Excel, etc.)
- Python Applications — Web, Automation, AI/ML, Data Analytics
- Python's Role in Data Analytics & Data Science
- Installing Python & Setting Up the Environment (Anaconda / pip)
- Introduction to Jupyter Notebook
- Writing & Running Your First Python Program

---

#### 📘 Chapter 02 — Intro To Python - 2
- Variables — Declaration, Assignment, Naming Rules
- Python Data Types — `int`, `float`, `complex`, `str`, `bool`, `NoneType`
- `type()` and `isinstance()` functions
- Type Casting — `int()`, `float()`, `str()`, `bool()`
- `input()` and `print()` functions
- Python Keywords & Reserved Words
- Comments — Single-line (`#`) and Multi-line (`'''`)
- Naming Conventions & PEP 8 Basics
- Dynamic Typing in Python

---

#### 📘 Chapter 03 — Operators
- Arithmetic Operators — `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Comparison / Relational Operators — `==`, `!=`, `>`, `<`, `>=`, `<=`
- Logical Operators — `and`, `or`, `not`
- Assignment Operators — `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `**=`
- Bitwise Operators — `&`, `|`, `^`, `~`, `<<`, `>>`
- Identity Operators — `is`, `is not`
- Membership Operators — `in`, `not in`
- Operator Precedence & Associativity

---

#### 📘 Chapter 04 — Strings
- String Creation & Literals
- String Indexing (Positive & Negative)
- String Slicing — `str[start:stop:step]`
- String Immutability
- String Methods — `upper()`, `lower()`, `strip()`, `lstrip()`, `rstrip()`, `replace()`, `split()`, `join()`, `find()`, `count()`, `startswith()`, `endswith()`
- String Formatting — `f-strings`, `.format()`, `%` operator
- Escape Characters — `\n`, `\t`, `\\`
- Raw Strings — `r"..."`
- Multi-line Strings

---

#### 📘 Chapter 05 — Data Structures - 1
**Lists**
- Creating Lists, Nested Lists
- Indexing & Slicing
- List Methods — `append()`, `insert()`, `remove()`, `pop()`, `sort()`, `reverse()`, `copy()`, `extend()`, `count()`, `index()`
- List Comprehensions
- Mutable Nature of Lists

**Tuples**
- Creating Tuples, Single-element Tuples
- Indexing & Slicing
- Tuple Methods — `count()`, `index()`
- Tuple Unpacking / Packing
- Immutability — Why Tuples over Lists?

---

#### 📘 Chapter 06 — Data Structures - 2
**Sets**
- Creating Sets, Empty Sets
- Set Methods — `add()`, `remove()`, `discard()`, `pop()`, `clear()`
- Set Operations — Union (`|`), Intersection (`&`), Difference (`-`), Symmetric Difference (`^`)
- Frozensets

**Dictionaries**
- Creating Dictionaries, Nested Dictionaries
- Accessing & Modifying Values
- Dictionary Methods — `get()`, `update()`, `keys()`, `values()`, `items()`, `pop()`, `setdefault()`
- Dictionary Comprehensions
- Iterating Over Dictionaries

---

#### 📘 Chapter 07 — Conditional Statements
- `if` Statement
- `if-else` Statement
- `if-elif-else` Ladder
- Nested `if` Conditions
- Ternary / Inline Conditional Expressions — `x if condition else y`
- Truthiness & Falsy Values in Python
- Practical Examples — Grade system, eligibility checks, etc.

---

#### 📘 Chapter 08 — Looping Statements
- `for` Loop — Iterating over Lists, Strings, Tuples, Ranges
- `range()` Function — `start`, `stop`, `step`
- `while` Loop — Condition-based Iteration
- Nested Loops
- `enumerate()` — Loop with Index
- `zip()` — Iterate over Multiple Iterables
- Looping with Dictionaries

---

#### 📘 Chapter 09 — Control Transfer Statements
- `break` — Exit a Loop Prematurely
- `continue` — Skip to the Next Iteration
- `pass` — Placeholder / Empty Block
- `else` with Loops (for-else / while-else)
- Practical Use Cases and Examples

---

#### 📘 Chapter 10 — Functions
- Defining Functions with `def`
- Function Parameters & Return Values
- Default Arguments
- Keyword Arguments (`kwargs`)
- Variable-length Arguments — `*args` and `**kwargs`
- Lambda (Anonymous) Functions
- Recursive Functions
- Scope — Local, Global, `global` keyword
- `map()`, `filter()`, `reduce()`
- Docstrings & Function Documentation

---

#### 📘 Chapter 11 — Exception Handling
- Types of Errors — Syntax, Runtime, Logical
- `try` and `except` Blocks
- Handling Specific Exceptions — `ValueError`, `TypeError`, `ZeroDivisionError`, `FileNotFoundError`, `IndexError`, `KeyError`
- `else` Block in Exception Handling
- `finally` Block — Always Executes
- Raising Exceptions with `raise`
- Custom / User-Defined Exceptions
- Best Practices for Error Handling

---

#### 📘 Chapter 12 — Modules
- What is a Module?
- `import` Statement and `from...import`
- `import ... as` Aliasing
- Built-in Modules — `math`, `random`, `datetime`, `os`, `sys`, `time`
- Creating Custom Modules
- `__name__ == "__main__"` Pattern
- Python Packages & `__init__.py`
- Installing Third-party Packages with `pip`

---

#### 📘 Chapter 13 — File Handling
- Opening Files — `open()` function
- File Modes — `r`, `w`, `a`, `r+`, `rb`, `wb`
- Reading Files — `read()`, `readline()`, `readlines()`
- Writing & Appending to Files
- Context Manager — `with open(...) as f`
- Working with CSV Files using `csv` module
- File & Directory Operations with `os` module
- Handling File-related Exceptions

---

### 🔵 Data Science Libraries — Chapters 14 to 19

---

#### 📗 Chapter 14 — NumPy - I
- What is NumPy? Why use it over Python Lists?
- Installing & Importing NumPy
- Creating Arrays — `np.array()`, `np.zeros()`, `np.ones()`, `np.full()`, `np.arange()`, `np.linspace()`
- Array Attributes — `shape`, `dtype`, `ndim`, `size`, `itemsize`
- 1D, 2D, and 3D Arrays
- Array Indexing & Slicing
- Array Data Types & Type Conversion

---

#### 📗 Chapter 15 — NumPy - II
- Element-wise Arithmetic Operations
- Broadcasting — Rules and Examples
- Reshaping & Transposing — `reshape()`, `flatten()`, `.T`
- Stacking & Splitting — `hstack()`, `vstack()`, `split()`
- Mathematical Functions — `np.sqrt()`, `np.exp()`, `np.log()`
- Statistical Functions — `np.sum()`, `np.mean()`, `np.std()`, `np.min()`, `np.max()`, `np.median()`
- Boolean Masking & Fancy Indexing
- Sorting Arrays — `np.sort()`, `np.argsort()`
- Random Module — `np.random.rand()`, `np.random.randint()`, `np.random.seed()`

---

#### 📗 Chapter 16 — Pandas - I
- What is Pandas? Why use it?
- `Series` — Creation, Indexing, Operations
- `DataFrame` — Creation, Structure, Attributes
- Reading Data — `pd.read_csv()`, `pd.read_excel()`
- Exploring DataFrames — `head()`, `tail()`, `info()`, `describe()`, `shape`, `columns`, `dtypes`
- Selecting Columns — Single & Multiple
- Row Selection — `loc[]` and `iloc[]`
- Adding & Dropping Columns and Rows
- Sorting — `sort_values()`, `sort_index()`

---

#### 📗 Chapter 17 — Pandas - II
- Filtering Rows with Conditions
- Multiple Conditions — `&`, `|`, `~`
- `groupby()` — Grouping and Aggregation (`sum`, `mean`, `count`, `max`, `min`)
- Merging DataFrames — `pd.merge()` (inner, outer, left, right joins)
- Joining DataFrames — `join()`
- Concatenating — `pd.concat()` (axis 0 & 1)
- Pivot Tables — `pd.pivot_table()`
- Cross Tabulation — `pd.crosstab()`

---

#### 📗 Chapter 18 — Pandas - III
- Identifying Missing Values — `isnull()`, `notnull()`, `isna()`
- Handling Missing Values — `dropna()`, `fillna()`
- Removing Duplicates — `duplicated()`, `drop_duplicates()`
- Applying Functions — `apply()`, `map()`, `applymap()`
- String Operations on Columns — `str.upper()`, `str.contains()`, `str.replace()`, `str.split()`
- DateTime Handling — `pd.to_datetime()`, `dt` accessor
- Renaming Columns — `rename()`
- Changing Data Types — `astype()`
- Exporting Data — `to_csv()`, `to_excel()`

---

#### 📗 Chapter 19 — Matplotlib & Seaborn
**Matplotlib**
- Figure and Axes — `plt.figure()`, `plt.subplot()`
- Line Plot — `plt.plot()`
- Bar Chart — `plt.bar()`, `plt.barh()`
- Scatter Plot — `plt.scatter()`
- Histogram — `plt.hist()`
- Pie Chart — `plt.pie()`
- Titles, Labels, Legends, Grid — `plt.title()`, `plt.xlabel()`, `plt.legend()`
- Saving Figures — `plt.savefig()`

**Seaborn**
- `sns.heatmap()` — Correlation Matrix Visualization
- `sns.pairplot()` — Pairwise Relationships
- `sns.boxplot()` and `sns.violinplot()` — Distribution
- `sns.barplot()` and `sns.countplot()`
- `sns.histplot()` and `sns.kdeplot()`
- Seaborn Themes & Color Palettes

---

### 🟠 Advanced Python — Chapters 20 to 21

---

#### 📙 Chapter 20 — OOPs (Object-Oriented Programming)
- Introduction to OOP — Why OOP?
- Classes & Objects
- `__init__()` Constructor
- Instance Variables vs Class Variables
- Instance Methods, Class Methods (`@classmethod`), Static Methods (`@staticmethod`)
- **Inheritance** — Single, Multi-level, Multiple
- `super()` Function
- **Polymorphism** — Method Overriding, Duck Typing
- **Encapsulation** — Private (`__`) and Protected (`_`) Members
- **Abstraction** — `ABC` module
- Dunder / Magic Methods — `__str__()`, `__repr__()`, `__len__()`, `__add__()`

---

#### 📙 Chapter 21 — Database Connectivity
- Introduction to Databases — Relational DB Concepts
- Connecting Python to SQLite — `sqlite3` module
- Connecting Python to MySQL — `mysql-connector-python`
- Creating a Database & Tables
- **CRUD Operations:**
  - `INSERT` — Adding records
  - `SELECT` — Fetching records with conditions
  - `UPDATE` — Modifying records
  - `DELETE` — Removing records
- Using Cursors — `cursor.execute()`, `fetchall()`, `fetchone()`
- Commit & Rollback — Transaction Management
- Closing Connections Safely
- Parameterized Queries — Preventing SQL Injection

---

### 🔴 Applied Projects

---

#### 🦠 Case Study — COVID Data Analysis
- Loading the COVID-19 Dataset
- Data Exploration & Understanding
- Cleaning & Preprocessing with Pandas
- Country-wise / Date-wise Analysis
- Trend Visualization using Matplotlib & Seaborn
- Key Insights & Conclusions

---

#### 📝 Python Test
- Chapter-wise Assessments
- Coding Challenges
- MCQ-style Revision Questions

---

#### 📅 Weekly
- Weekly Practice Problems
- Revision Notebooks
- Progressive Difficulty Exercises

---

## 🚀 How to Use This Repo

1. **Clone the repository**
   ```bash
   git clone https://github.com/sachinkhote/Python-Learnings.git
   cd Python-Learnings
   ```

2. **Open any chapter** in Jupyter Notebook
   ```bash
   jupyter notebook
   ```

3. **Follow chapters in order** — especially for the first 13 chapters (core Python)

4. **Libraries chapters (14–19)** can be explored independently once core Python is done

---

## 📌 Learning Path Recommendation

```
Basics          → Chapters 01–04
Data Structures → Chapters 05–06
Control Flow    → Chapters 07–09
Functions       → Chapter 10
Error Handling  → Chapter 11
Utilities       → Chapters 12–13
─────────────────────────────────
Data Science    → Chapters 14–19
OOP             → Chapter 20
Databases       → Chapter 21
─────────────────────────────────
Apply It All    → COVID Case Study
```

---

*This repository is dedicated to personal learning. Happy coding! 🎯*
