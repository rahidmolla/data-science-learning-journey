# NumPy: ndarray Foundations and Attributes

## 1. Introduction and definition
NumPy is the core Python library for efficient numerical arrays. Its main object, `ndarray`, stores homogeneous, n-dimensional data and supports vectorized computation.

## 2. Why we need this
Arrays make numerical operations faster and more concise than manually looping over Python lists, especially for large numerical datasets.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``np.array`` | Create an ndarray from array-like data. |
| ``np.asarray`` | Convert input to an array, avoiding a copy when possible. |
| ``np.ndim`` | Return number of dimensions. |
| ``np.shape`` | Return dimensions along each axis. |
| ``np.size`` | Return total number of elements. |
| ``np.dtype`` | Describe the element data type. |
| ``.itemsize`, `.nbytes`` | Inspect element size and total array bytes. |
| ``.T`, `np.transpose`` | Transpose axes. |
| ``np.copy`` | Create an independent copy. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
a = np.array([[1, 2, 3], [4, 5, 6]], dtype=np.int64)
print(a.shape)   # (2, 3)
print(a.ndim)    # 2
print(a.size)    # 6
print(a.dtype)   # int64
```

## 5. Advanced examples
```python
b = np.asarray(a, dtype=np.float64)
c = a.T
print(c.shape)   # (3, 2)
print(a.nbytes)  # 48 for six int64 values
```

## 6. Practical real-world applications
Represent measurements, image pixels, feature matrices and numerical simulation data.

## 7. Common mistakes
Assuming arrays can freely mix arbitrary Python objects; confusing `shape` with `size`; assuming transpose always copies data; forgetting integer overflow or dtype conversion.

## 8. Practice questions
Create 1D, 2D and 3D arrays; inspect their attributes; compare memory usage for int32 and float64.

## 9. Interview questions
What is an ndarray? What does shape mean? What is the difference between `asarray` and `array`? What is a dtype?

## 10. Related functions and concepts
Array creation, indexing, views vs copies, broadcasting and vectorization.
