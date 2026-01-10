# NumPy-II Study Guide

This guide provides a structured summary of advanced NumPy operations, statistical functions, and array creation methods based on the sources.

---

### **1. Array Manipulation Operations**
NumPy provides several ways to change the structure and orientation of arrays without necessarily altering the underlying data.

*   **Transpose:** Turns rows into columns and vice versa.
    *   **Syntax:** `arr.transpose()` or the shorthand `arr.T`.
    *   **Note:** This creates a new array; the original remains unchanged.
*   **Reshaping:** Changes the dimensions of an array.
    *   **Syntax:** `arr.reshape(new_shape)`.
    *   **The -1 Trick:** Using `-1` in a dimension tells NumPy to automatically calculate that size based on the other dimensions.
    *   **Constraint:** The total number of elements must remain the same, or it will raise a `ValueError`.
*   **Concatenating:** Joins two or more arrays along a specified axis.
    *   **Syntax:** `np.concatenate((arr1, arr2), axis=0)`.
    *   **Requirement:** Arrays must have the same shape except in the dimension being concatenated. For example, to join along rows (axis 0), they must have the same number of columns.
*   **Splitting:** Breaks one array into multiple sub-arrays.
    *   **Syntax:** `np.split(array, parts, axis=0)`.

---

### **2. Sorting Arrays**
NumPy offers three primary ways to sort data:

| Function/Method | Description | Impact on Original |
| :--- | :--- | :--- |
| **`np.sort(arr)`** | Returns a **sorted copy** of the array. | No change. |
| **`arr.sort()`** | Sorts the array **in-place**. | Modifies original. |
| **`np.argsort(arr)`** | Returns the **indices** that would sort the array. | No change. |

**Axis Logic in Sorting:**
*   **Axis 0:** Sorts vertically down columns.
*   **Axis 1 / Axis -1:** Sorts horizontally across rows.

---

### **3. Statistical Operations**
These functions can be applied to the whole array or along specific axes (rows or columns).

*   **`np.mean()`**: Arithmetic mean.
*   **`np.median()`**: Median value.
*   **`np.std()`**: Standard deviation.
*   **`np.min()` / `np.max()`**: Minimum and maximum values.
*   **`np.sum()`**: Total sum of elements.

---

### **4. Advanced Array Creation**
Beyond `np.array()`, NumPy provides specialized functions for generating data:

*   **`np.zeros(shape)`**: Creates an array filled with 0.0 (float by default).
*   **`np.ones(shape)`**: Creates an array filled with 1.0.
*   **`np.full(shape, fill_value)`**: Fills an array with a specific value (e.g., 3.14).
*   **`np.eye(N, M, k)`**: Creates a 2D identity-like matrix with 1s on the k-th diagonal.
*   **`np.arange(start, stop, step)`**: Like Python’s `range()`, but returns an array.
*   **`np.random.random(shape)`**: Generates random floats between 0 and 1.
*   **`np.linspace(start, stop, num)`**: Generates a specific number of evenly spaced points between two values.

---

### **5. Python Lists vs. NumPy Arrays**
A comparison of the two data structures is summarized below:

| Feature | Python List | NumPy Array |
| :--- | :--- | :--- |
| **Data Type** | Can be mixed. | **Must be the same**. |
| **Operations** | No direct element-wise math; requires loops. | **Supports element-wise math** (e.g., `arr / 3`). |
| **Functions** | Limited math support. | **Extensive math/stats library**. |
| **Usage** | General purpose. | **Scientific computing**. |

---

### **💡 Additional Insights (Missing from Sources)**
*While not explicitly in the sources, these concepts often complete the understanding of the topics above:*
*   **Broadcasting:** This is the underlying mechanism that allows NumPy to perform element-wise operations on arrays of different (but compatible) shapes.
*   **Vectorization:** This is the practice of replacing explicit loops with array expressions, which is why NumPy arrays are significantly faster than Python lists.
*   **Memory Usage:** For future revision, remember that **`np.reshape()`** and **`arr.T`** often return a **"view"** of the data rather than a copy, meaning they don't consume extra memory for the data itself. In contrast, **`np.concatenate()`** always creates a new copy in memory.