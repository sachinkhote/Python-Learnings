
#  Summary: Matplotlib & Seaborn

## 1. Focused On
- Concept of **data visualization**.
- Importance of **Matplotlib** for customizable plots.
- Integration with **NumPy** and **Pandas**.
- Importance of **Seaborn** for high-level, attractive statistical graphics.
- Common plot types: line, bar, scatter, pie, box, violin, heatmap, KDE.

---

## 2. Matplotlib Basics
- **Installation**:  
  ```bash
  pip install matplotlib
  conda install matplotlib
  ```
- **Import**:  
  ```python
  import matplotlib.pyplot as plt
  ```
- **Figure Components**:
  - Plotting area
  - Axis labels
  - Title
  - Legend
  - Ticks

### Example: Simple Line Plot
```python
x = [1,2,3,4,5]
y = [2,3,5,7,11]
plt.plot(x, y, label="Prime Numbers")
plt.title("Simple Line Plot")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.legend()
plt.show()
```

---

## 3. Customization in Matplotlib
- **Markers**: symbols like `o` (circle), `*` (star), `s` (square).
- **Colors**: abbreviations (`'r'`, `'g'`, `'b'`) or names (`'red'`, `'blue'`) or hex codes (`'#FF5733'`).
- **Line Style**: `'solid'`, `'dashed'`, `'dotted'`, `'dashdot'`.
- **Line Width**: default = 1 pixel, can be increased.

### Example: Weight vs Height
```python
plt.plot(weight, height, color='green', marker='*', markersize=10,
         linestyle='--', linewidth=2, label='Avg Weight vs Height')
plt.title("Average Weight vs Height")
plt.xlabel("Weight (kg)")
plt.ylabel("Height (cm)")
plt.legend()
plt.grid()
plt.show()
```

---

## 4. Integration with NumPy & Pandas
- **NumPy**: Efficient array handling for plotting.
  ```python
  import numpy as np
  x = np.array([0,1,2,3,4,5])
  y = x**2
  plt.plot(x, y, marker='o', linestyle=':', color='#FF5733')
  ```
- **Pandas**: Direct plotting from DataFrames.
  - Example: Gender distribution pie chart from `Customers.csv`.
  - Example: City-wise bar chart for top 10 cities.

---

## 5. Plot Types & Their Usage

### Line Plot
- **Purpose**: Show trends or changes over time/continuous variables.
- **Usage**: Monthly spending patterns, growth of sales, stock prices.
- **Example**:  
  ```python
  plt.plot(months, sales, marker='o')
  ```

---

### Bar Plot
- **Purpose**: Compare categories side by side.
- **Usage**: Top 10 cities by customers, average cost of products by company.
- **Example**:  
  ```python
  sns.barplot(x='day', y='tip', data=tips, estimator='mean')
  ```

---

### Pie Chart
- **Purpose**: Show proportions of categories in a whole.
- **Usage**: Gender distribution of customers, market share of companies.
- **Example**:  
  ```python
  plt.pie(gender_counts, labels=gender_counts.index, autopct='%1.1f%%')
  ```

---

### Scatter Plot
- **Purpose**: Show relationships between two continuous variables.
- **Usage**: Total bill vs tip, height vs weight.
- **Example**:  
  ```python
  sns.scatterplot(x='total_bill', y='tip', data=tips, hue='sex')
  ```

---

### Box Plot
- **Purpose**: Show distribution, median, quartiles, and outliers.
- **Usage**: Distribution of paid amounts, tips by day.
- **Example**:  
  ```python
  sns.boxplot(x='day', y='tip', data=tips)
  ```

---

### Violin Plot
- **Purpose**: Combines box plot + KDE (distribution + summary).
- **Usage**: Compare distributions of tips across days.
- **Example**:  
  ```python
  sns.violinplot(x='day', y='tip', data=tips)
  ```

---

### Heatmap
- **Purpose**: Show correlations or intensity values in a matrix.
- **Usage**: Correlation between numeric variables (e.g., total_bill, tip, size).
- **Example**:  
  ```python
  sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
  ```

---

### KDE Plot (Kernel Density Estimate)
- **Purpose**: Show smooth distribution curve of a variable.
- **Usage**: Distribution of total bill by time of day, compare density of continuous variables.
- **Example**:  
  ```python
  sns.kdeplot(x='total_bill', data=tips, hue='time', fill=True)
  ```

---

### Grouped Bar Plot
- **Purpose**: Compare multiple categories simultaneously.
- **Usage**: Average tip by day and time (Lunch vs Dinner).
- **Example**:  
  ```python
  sns.barplot(x='day', y='tip', hue='time', data=tips)
  ```

---

## 6. Key Takeaways
- **Matplotlib**: Flexible, customizable, integrates with NumPy/Pandas.
- **Seaborn**: High-level, aesthetically pleasing, simplifies complex plots.
- Use Matplotlib for **fine control**, Seaborn for **quick, attractive statistical graphics**.
- Together, they form the backbone of **Python data visualization**.
