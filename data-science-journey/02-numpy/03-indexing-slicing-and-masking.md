# NumPy: Indexing, Slicing and Boolean Masks

## 1. Introduction and definition
Indexing selects individual elements or regions; boolean masks and fancy indexing select values based on conditions or integer positions.

## 2. Why we need this
Efficient selection is essential for filtering, feature extraction and conditional updates.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``a[i]`, `a[i, j]`` | Select elements by integer index. |
| ``a[start:stop:step]`` | Slice a range; basic slices usually create views. |
| ``a[mask]`` | Select values where a boolean mask is true. |
| ``a[[0, 2]]`` | Select positions using integer/fancy indexing. |
| ``np.where`` | Choose values or return matching coordinates. |
| ``np.take`` | Select along an axis by indices. |
| ``np.ix_`` | Build an open mesh for selecting cross-products of indexes. |
| ``np.nonzero`, `np.argwhere`` | Return coordinates of non-zero/true elements. |
| ``np.put`, `np.putmask`` | Update array positions using indices or masks. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
a = np.array([10, 20, 30, 40, 50])
print(a[1:4])          # [20 30 40]
print(a[a > 25])       # [30 40 50]
print(np.where(a > 25, 1, 0))
```

## 5. Advanced examples
```python
matrix = np.arange(1, 10).reshape(3, 3)
rows = np.array([0, 2])
cols = np.array([1, 2])
print(matrix[np.ix_(rows, cols)])
# [[2 3]
#  [8 9]]
```

## 6. Practical real-world applications
Filter sensor readings above a threshold, isolate rows with invalid measurements, select pixels or model features.

## 7. Common mistakes
Basic slices can be views and changes may affect the original; fancy indexing returns a copy; chained indexing can confuse updates; masks must align with the selected axis.

## 8. Practice questions
Select even values; replace negative values with zero; select rows 0 and 2 and columns 1 and 2 from a matrix.

## 9. Interview questions
Difference between slicing and fancy indexing? What does `where` return with one argument vs three? How do boolean masks work?

## 10. Related functions and concepts
Views/copies, broadcasting, conditional operations and array assignment.
