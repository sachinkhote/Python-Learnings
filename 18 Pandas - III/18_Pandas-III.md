

#  Detailed Summary: Pandas-III 

## 1. Focus On
- Handling **missing values**.
- Performing **statistical operations** (mean, median, mode, max, min, sum, count).
- Conducting **frequency analysis**.
- Using **data aggregations**.
- Sorting DataFrames with `sort_values`.
- Applying **idxmax** to locate maximum values.
- Using **GROUP BY** functions for aggregation.
- Altering the **index** with `set_index` and `reset_index`.
- Exporting DataFrames to CSV/Excel (covered later in practice).

---

## 2. Statistical Operations
Statistical operations summarize and describe data patterns.

### A) Mean
- `df.mean()` → average of numeric columns.  
- Non-numeric columns (like dates) may give nonsensical results.  
- **Best practice**: filter numeric columns first.  
  ```python
  numeric_cols = df.select_dtypes(include=['number'])
  mean_values = numeric_cols.mean()
  ```
- Example: `df_purchases['paid'].mean()` → `548.87`.

⚠️ **Tip**: Applying mean on non-numeric columns raises `TypeError`.

---

### B) Median
- `df.median()` → middle value of numeric columns.  
- Non-numeric columns (like dates) may produce meaningless results.  
- Example:  
  ```python
  median_values = df_purchases.select_dtypes(include=['number']).median()
  ```

---

### C) Mode
- `df.mode()` → most frequent value(s).  
- Useful for categorical data (e.g., gender, city).  
- If multiple values share the same frequency, multiple rows with NaN appear.

---

### D) Maximum & Minimum
- `df.max(numeric_only=True)` → highest values.  
- `df.min(numeric_only=True)` → lowest values.  
- Pandas often returns float64 → convert back to int if needed:  
  ```python
  max_values = df.max(numeric_only=True).astype(int)
  ```

---

### E) Sum
- `df.sum(numeric_only=True)` → sum of numeric columns.  
- ⚠️ Summing IDs or unique identifiers is usually meaningless.

---

### F) Count
- `df.count()` → counts non-null values per column.  
- Example: `Products.count()` → shows how many non-null entries each column has.

---

## 3. Frequency Analysis
- `value_counts()` → frequency distribution of categorical data.  
- Example:  
  ```python
  company_counts = df_products['company'].value_counts()
  gender_counts = df_customers['gender'].value_counts()
  ```
- Output:  
  - Male: 528  
  - Female: 472  

💡 **Notebook Tip**: Frequency analysis is great for categorical distributions.

---

## 4. Data Aggregations
- `aggregate()` → apply one or multiple functions.  
- Example:  
  ```python
  df_purchases.aggregate('max')
  df_products['cost'].aggregate(['max','min'])
  ```
- Multiple functions: `['mean','median','std','count']`.

---

## 5. Sorting a DataFrame
- `sort_values(by='column')` → ascending order.  
- `sort_values(by='column', ascending=False)` → descending order.  
- Multiple columns:  
  ```python
  df.sort_values(by=['company','cost'], ascending=[True,False])
  ```

Examples:
- Sort purchases by `amount`.
- Sort products by `company`.
- Sort customers by `first_name` descending.

---

## 6. idxmax Function
- `idxmax()` → index of first occurrence of maximum value.  
- Example:  
  ```python
  index_max_paid = df_purchases['paid'].idxmax()
  ```
- Useful for locating the row with the highest value.

---

## 7. GROUP BY Functions
Grouping involves:
- **Splitting** data into groups.
- **Applying** functions (sum, mean, count).
- **Combining** results.

Examples:
```python
grouped_by_company = df_products.groupby('company')
average_cost = grouped_by_company['cost'].mean()
total_products = grouped_by_company['product'].count()
```

Other examples:
- Group purchases by `purch_date` → total paid per date.
- Group purchases by `product_num` → average amount per product.

💡 **Notebook Tip**: You can chain `aggregate` with groupby for multiple stats.

---

## 8. Altering the Index
- `set_index('column')` → set a column as index.  
- `reset_index()` → revert to default integer index.  
- Example:  
  ```python
  df_customers.set_index('id', inplace=True)
  df_customers.reset_index(inplace=True)
  ```

You can also set non-numeric columns (like `email`) as index for unique identification.

---

## 9. Pivot Tables (Notebook Extension)
Pivot tables allow multi-dimensional summaries:
```python
pd.pivot_table(data=df_purchases,
               values='amount',
               index='purch_date',
               columns='product_num',
               aggfunc='sum',
               fill_value=0)
```
- Index → rows (e.g., purchase date).
- Columns → categories (e.g., product number).
- Values → aggregated metric (e.g., sum of amount).

---

## 10. Key Takeaways
- **Statistical ops**: mean, median, mode, max, min, sum, count → summarize data.
- **Frequency analysis**: `value_counts` → categorical distributions.
- **Aggregations**: `aggregate` + `groupby` → powerful summaries.
- **Sorting**: organize data for analysis.
- **idxmax**: locate maximum efficiently.
- **Indexing**: customize DataFrame structure.
- **Pivot tables**: advanced summarization across dimensions.

---

## 11. Why This Matters
- These operations are **core to data wrangling** in Pandas.  
- They allow analysts to **summarize, clean, and structure data** before deeper analysis.  
- Jupyter Notebook examples provide **real coding context** with warnings, tips, and best practices.  
- Together, they form the **foundation for advanced analytics** like joins, merges, and visualizations.

---