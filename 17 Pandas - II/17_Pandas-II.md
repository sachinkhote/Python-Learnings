

# 🐼 Pandas-II: Revision Summary

## 1. DataFrame Attributes

Attributes provide metadata about the DataFrame without performing operations.

* **`.index`**: Returns row labels.


* **`.shape`**: Returns a tuple `(rows, columns)`.


* `shape[0]` = number of rows.


* `shape[1]` = number of columns.




* **`.columns`**: Returns a list of column labels.


* **`.dtypes`**: Returns the data type of each column.


* **`.values`**: Returns a 2D NumPy array of the data.


* **`.size`**: Returns total number of elements (rows  columns).


* **`.empty`**: Returns `True` if the DataFrame is empty.


* **`.ndim`**: Returns number of dimensions (always 2 for DataFrames).



---

## 2. Basic Methods

* **`.info()`**: Provides a concise summary including data types, non-null counts, and memory usage.


* **`.head(n)`**: Returns first  rows (default 5).


* **`.tail(n)`**: Returns last  rows (default 5).


* **`.describe()`**: Generates descriptive statistics (count, mean, std, min, max, etc.).


* **`.transpose()`** (or `.T`): Swaps rows and columns.



---

## 3. Operations on Rows and Columns

### A. Adding Columns

* **Scalar Value:** Assigns the same value to all rows.
* `df['Country'] = 'USA'`.




* **From List:** List length must match DataFrame rows exactly.


* **From Calculation:** Combining existing columns.
* `df['Full_Name'] = df['First'] + ' ' + df['Last']`.





### B. Adding Rows

* **Using `.loc`:** Assign a list of values to a new index label.
* `df.loc['new_index'] = [val1, val2, ...]`.


* *Note:* Ensure the list length matches the column count.





### C. Deleting Data (`.drop`)

* **Rows:** `df.drop(index='label', inplace=True)`.


* **Columns:** `df.drop(columns=['col1', 'col2'], inplace=True)`.


* *Note:* `inplace=True` modifies the original DataFrame; otherwise, a new one is returned.



### D. Renaming

* **Rows:** `df.rename(index={old_label: new_label})`.


* **Columns:** `df.rename(columns={'old_name': 'new_name'})`.



### E. Unique Values

* **`.unique()`**: Returns array of unique values (includes NaN).


* **`.nunique()`**: Returns the **count** of unique non-null values (excludes NaN).



---

## 4. Type Conversion

* **`.astype()`**: Converts data types (e.g., to float, int).
* *Limitation:* Cannot convert columns with non-numeric characters (like '$') directly.




* **String Cleaning:** Must remove symbols before conversion.
* `df['price'] = df['price'].str.replace('[$,]', '', regex=True).astype(float)`.




* **`pd.to_datetime()`**: Converts strings to datetime objects.


* **`pd.to_numeric()`**: Converts to numbers. Use `errors='coerce'` to turn non-convertible values into `NaN` instead of erroring.



---

## 5. Combining DataFrames

There are three main methods to combine data: Concatenation, Merging, and Joining.

### A. Concatenation (`pd.concat`)

Combines DataFrames along an axis (stacking).

* **Row-wise (`axis=0`):** Stacks rows vertically (like SQL UNION).


* **Column-wise (`axis=1`):** Stacks columns horizontally.


* *Note:* Fills missing data with `NaN` if columns/indices don't align.



### B. Merging (`pd.merge`)

Combines based on common keys (columns), similar to SQL Joins.

* **Syntax:** `pd.merge(left, right, on='key', how='type')`.


* **Types of Joins (`how`):**
* **Inner:** Only matching rows.


* **Left:** All left rows, matching right rows.


* **Right:** All right rows, matching left rows.


* **Outer:** All rows from both.


* **Suffixes:** Used when non-key columns have identical names. `suffixes=('_left', '_right')`.



### C. Joining (`.join`)

Combines based on **index**.

* **Syntax:** `df1.join(df2)`.


* Useful when indices are the common keys.



### Comparison Table

| Feature | Concatenation | Merging | Joining |
| --- | --- | --- | --- |
| **Function** | `pd.concat()` | `pd.merge()` | `.join()` |
| **Purpose** | Stack DataFrames | Combine on Keys | Combine on Index |
| **Alignment** | Axis (0 or 1) | Key Columns | Index |

---

## 6. Handling Missing Values (NaN)

Missing values occur due to data collection errors or irrelevance.

### A. Detection

* **`.isnull()` / `.isna()**`: Returns Boolean DataFrame (True if missing).


* **`.any()`**: Returns True if *any* value in a column/row is missing.


* **`.sum()`**: Counts NaN values (True=1).



### B. Dropping (`.dropna`)

Used when missing data is small or insignificant.

* **Rows:** `df.dropna()` (drops row if *any* value is missing).


* **Columns:** `df.dropna(axis=1)`.



### C. Filling / Imputation (`.fillna`)

Used to estimate values to retain data.

* **Static Value:** `df.fillna(0)` or `df.fillna('Unknown')`.


* **Statistical:** Fill with Mean, Median, or Mode.


* *Example:* `df['col'].fillna(df['col'].mode()[0], inplace=True)`.




* **Propagation:**
* **Forward Fill (`ffill`):** Propagates last valid observation forward.


* **Backward Fill (`bfill`):** Propagates next valid observation backward.





---

## 7. Handling Duplicates

* **`.drop_duplicates()`**: Removes duplicate rows.


* **Parameters:**
* `subset`: Specify column(s) to check for uniqueness.


* `inplace`: Modify original DataFrame.


* *Example:* `df.drop_duplicates(subset='first_name')`.





---

## 8. Data Aggregation

Transforming data by computing summary values (sum, mean, max, etc.).

* **`.aggregate()` (or `.agg`)**: Apply one or multiple functions.
* *Single:* `df.agg('max')`.


* *Multiple:* `df['col'].agg(['min', 'max'])`.




* **`.groupby()`**: Groups data by a column before aggregating.
* *Example:* Group by date, then sum amounts.


```python
df.groupby('date').agg({'amount': 'sum', 'paid': 'sum'})

```