# NumPy-I: Comprehensive Revision Guide

This guide provides a descriptive overview of **NumPy (Numerical Python)**, a fundamental library for scientific computing in Python, designed to support large, multi-dimensional arrays and matrices.

---

### 1. Introduction to NumPy
*   **Definition**: NumPy is the foundational library for performing **efficient numerical computations** and serves as the base for many other scientific libraries in Python,.
*   **Core Feature**: It is centered around the **array**, providing multi-dimensional structures and a vast collection of mathematical functions to operate on them.
*   **Functionality**: It includes statistical functions (mean, median, variance, etc.) to help understand data distributions and integrates seamlessly with **Matplotlib** for data visualisation.
*   **Installation & Setup**:
    *   Install via: `conda install numpy` or `pip install numpy`.
    *   Standard Import Convention: `import numpy as np` (shortened to `np` for better readability).

### 2. Understanding Arrays
*   **Definition**: An array is a data type that stores multiple values using a single identifier.
*   **Key Characteristics**:
    *   **Homogeneity**: Each element must be of the **same data type**.
    *   **Contiguous Memory**: Arrays are stored contiguously in memory, making operations significantly **faster** than standard Python lists.
    *   **Indexing**: Every element is identified by a unique integral index based on its position, starting from ****,.
*   **NumPy Array (`ndarray`)**: While Python has a built-in array structure, the NumPy `ndarray` is more versatile, efficient, and useful. It is mutable and used to store numerical data, vectors, and matrices.

---

### 3. Creating NumPy Arrays
Arrays can be created using the `np.array()` function by passing a list or tuple. **Note**: A common mistake is forgetting the square brackets inside the parentheses; `np.array()` is correct, whereas `np.array(1,2,3)` will cause a `TypeError`.

#### Dimensionality Overview:
*   **1-D Array (Vector)**: A single row of elements.
*   **2-D Array (Matrix)**: Elements organised into **rows (Axis 0)** and **columns (Axis 1)**,.
*   **3-D Array**: A collection of 2-D arrays stacked along a third axis.
    *   **Axis 0**: Matrices (slices).
    *   **Axis 1**: Rows within each matrix.
    *   **Axis 2**: Columns within each matrix.

---

### 4. Data Types and Upcasting
*   **Specifying Types**: You can use the `dtype` argument during creation (e.g., `dtype=float`) to force elements into a specific type.
*   **Upcasting**: Because all elements must be the same type, if you provide mixed data (e.g., integers and strings), NumPy will automatically "upcast" them to the most general type possible (like Unicode strings) to accommodate all elements,.
*   **Object Dtype**: If you must maintain original, mixed data types, you can specify `dtype=object`.

---

### 5. Essential Array Attributes
These attributes help you understand the structure and memory usage of your data:
1.  **`ndarray.ndim`**: Returns the number of dimensions (axes).
2.  **`ndarray.shape`**: Returns a tuple representing the size along each dimension (e.g., `(rows, columns)`).
3.  **`ndarray.size`**: The total number of elements in the array, calculated as the product of the shape tuple.
4.  **`ndarray.dtype`**: Describes the data type of the elements (e.g., `int32`, `float64`).
5.  **`ndarray.itemsize`**: The size in bytes of each individual element.
6.  **`ndarray.data`**: A buffer containing the actual raw data of the array.

---

### 6. Indexing and Slicing
#### A. Integer Indexing
*   Access individual elements using their positional index:
    *   **1-D**: `arr[index]`.
    *   **2-D**: `arr[row_index, column_index]`.
    *   **3-D**: `arr[matrix_index, row_index, column_index]`.

#### B. Boolean Indexing (Masking)
*   You can use an array of `True/False` values (a mask) of the same shape to select only the elements where the mask is `True`. 
*   The resulting output for multi-dimensional masks is often a **flattened** (one-dimensional) array,.

#### C. Slicing
*   Uses the syntax `start:stop:step`.
*   **Multi-dimensional Slicing**: You can slice across multiple dimensions by separating them with commas (e.g., `arr[1:3, 1:3]` selects a sub-block of rows and columns),.
*   **Ellipsis (`...`)**: Represents all remaining dimensions. For example, `arr[..., :]` selects all matrices and all their internal elements,.

---

### 7. Arithmetic Operations
NumPy performs **element-wise** operations, meaning the operation is applied to each corresponding pair of elements in the arrays.
*   Supported operations include addition (`+`), subtraction (`-`), multiplication (`*`), division (`/`), modulus (`%`), exponentiation (`**`), and floor division (`//`).
*   **Crucial Requirement**: For these operations, the arrays must generally have the **same shape**.

***

**Analogy for Future Revision**:
Think of a **Standard Python List** like a **shopping bag** filled with various items (fruit, milk, bread). It’s flexible but messy to search through. A **NumPy Array** is like an **egg carton**: every slot is exactly the same size, designed for the same type of item, and stacked in a perfectly organised grid. Because of this rigid structure, you can count, move, or process the entire "carton" much faster than the bag.