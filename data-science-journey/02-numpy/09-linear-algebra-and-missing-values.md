# NumPy: Linear Algebra, NaN and Numerical Safety

## 1. Introduction and definition
NumPy includes matrix operations and tools for representing and detecting missing or non-finite numerical values.

## 2. Why we need this
Linear algebra appears in regression and dimensionality reduction; NaN-aware logic is essential when data contains missing measurements.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``@`, `np.matmul`` | Matrix multiplication. |
| ``np.dot`` | Dot product / matrix product depending on dimensions. |
| ``np.linalg.solve`` | Solve a linear system. |
| ``np.linalg.inv`, `pinv`` | Matrix inverse and pseudoinverse. |
| ``np.linalg.det`, `matrix_rank`` | Determinant and rank. |
| ``np.linalg.eig`, `svd`, `qr`` | Eigen decomposition, singular value decomposition and QR. |
| ``np.isnan`, `np.isfinite`, `np.isinf`` | Detect NaN and infinite values. |
| ``np.nan_to_num`` | Replace non-finite values. |
| ``np.errstate`` | Control floating-point warning behavior. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
A = np.array([[3., 1.], [1., 2.]])
b = np.array([9., 8.])
print(np.linalg.solve(A, b))  # [2. 3.]
x = np.array([1.0, np.nan, np.inf])
print(np.isfinite(x))         # [ True False False]
```

## 5. Advanced examples
```python
data = np.array([10.0, np.nan, 30.0])
clean = np.where(np.isnan(data), np.nanmean(data), data)
print(clean)  # [10. 20. 30.]
```

## 6. Practical real-world applications
Solve systems, inspect matrix rank, build numerical models, and identify or handle invalid measurements.

## 7. Common mistakes
Using explicit matrix inverse when `solve` is more stable; ignoring singular matrices; treating infinity as NaN; assuming NaN equals itself.

## 8. Practice questions
Check finite values; solve a 2x2 linear system; calculate rank; replace NaN with column means in a 2D array.

## 9. Interview questions
What is SVD? Why prefer `solve` over inverse? Why is `NaN != NaN`? What is matrix rank?

## 10. Related functions and concepts
Missing data, statistics, broadcasting, numerical stability and machine learning foundations.
