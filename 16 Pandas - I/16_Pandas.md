Here is a brief, revision-focused markdown summary of the Pandas-I session.

---

# 🐼 Pandas-I: Revision Summary

## 1. Introduction to Pandas

* 
**Definition:** Pandas (Panel Data) is a high-level data manipulation tool built on top of NumPy and Matplotlib.


* **Key Features:**
* Simple, intuitive syntax for complex operations.


* Handles large datasets efficiently (leveraging NumPy).


* Supports various formats: CSV, Excel, SQL, JSON.


* Excellent for data preprocessing, cleaning, and transformation.





## 2. Installation & Import

* **Installation:**
```bash
pip install pandas
# OR
conda install pandas

```



Note: Python must be installed first.


* **Importing:**
```python
import pandas as pd

```



---

## 3. Data Structure: Series (1D)

A **Series** is a one-dimensional array-like structure that holds data of any type with associated unique labels (index).

Comparison: Series vs. NumPy Array 

| Feature | Pandas Series | NumPy Array |
| --- | --- | --- |
| **Indexing** | Custom labeled index (numbers or letters) | Integer position only |
| **Missing Data** | Generates `NaN` if not aligned | No concept of `NaN`; alignment fails |
| **Memory** | Occupies more memory | Occupies less memory |

Creating Series 

* 
**From Scalar:** `pd.Series(10, index=['a', 'b'])` (Repeats value).


* 
**From List:** `pd.Series([10, 20])` (Default index 0, 1...).


* 
**From NumPy Array:** `pd.Series(np_array)`.


* 
**From Dictionary:** `pd.Series({'a': 10, 'b': 20})` (Keys become index).



### Accessing & Slicing Series

* 
**Indexing:** Can use positional index `s[0]` or labeled index `s['a']`.


* **Slicing:**
* 
**Positional:** `s[1:4]` (End index is **exclusive**).


* 
**Labels:** `s['b':'d']` (End label is **inclusive**).





Key Attributes 

* `.index`: Returns labels.
* `.values`: Returns data array.
* `.shape`: Tuple of dimensions.
* `.size`: Total number of elements.
* `.hasnans`: Returns `True` if `NaN` exists.
* `.is_unique`: Returns `True` if all values are unique.

Key Methods 

* `.head(n)` / `.tail(n)`: View first/last  elements.
* `.describe()`: Generates descriptive statistics (count, mean, std, min, max, etc.).
* `.value_counts()`: Counts unique values.
* `.sort_values()` / `.sort_index()`: Sorts by data or labels.
* 
`.drop(label)`: Removes item (returns new Series unless `inplace=True`).


* `.isnull()` / `.notnull()`: Detects missing values.

Mathematical Operations 

* Operations align by **index**.
* Mismatched indices result in `NaN`.
* **Handling NaN:**
* 
`s.fillna(0)`: Replaces NaN with 0.


* 
`s.dropna()`: Removes NaN values.





---

## 4. Data Structure: DataFrame (2D)

A **DataFrame** is a two-dimensional labelled structure (like a SQL table or Excel sheet) with rows and columns.

### Creating DataFrames

* 
**Empty:** `pd.DataFrame()`.


* 
**From NumPy Array:** `pd.DataFrame(data, columns=['Age', 'City'])`.


* 
**From List of Dicts:** Keys become column names.


* **Loading Files:**
* 
**Excel:** `pd.read_excel("file.xlsx", sheet_name="sheet1")`.


* 
**CSV:** `pd.read_csv("file.csv")`.





---

5. Accessing & Indexing DataFrames 

### Column Access

* 
**Single Column:** `df['column_name']` (Returns a Series).


* 
**Multiple Columns:** `df[['col1', 'col2']]` (Returns a DataFrame).



Row/Cell Access: `.loc` vs `.iloc` 

| Method | Type | Syntax | Slicing Behavior |
| --- | --- | --- | --- |
| **.loc** | **Label**-based | `df.loc[row_label, col_label]` | End point is **Inclusive** 

 |
| **.iloc** | **Position**-based (Integer) | `df.iloc[row_pos, col_pos]` | End point is **Exclusive** 

 |

**Examples:**

* 
`df.loc[:, 'id']`: All rows, column labeled 'id'.


* 
`df.iloc[:, 0]`: All rows, first column (position 0).


* 
`df.loc[2:4, :]`: Rows with labels 2 through 4 (inclusive).


* 
`df.iloc[1:4, 1:3]`: Rows 1 to 3, Cols 1 to 2 (exclusive).



Boolean Indexing 

Filtering data based on conditions.

* **Syntax:** `df[condition]`
* 
**Example:** `df[df['gender'] == 'Male']`.


* **Complex Logic:** Use `&` (and), `|` (or), `~` (not).
* *Ex:* `df[(df['name'] == 'Tobit') | (df['name'] == 'Natale')[cite_start]]`.