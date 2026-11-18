# NumPy: Reshaping, Transposing, Joining and Splitting

## 1. Introduction and definition
Shape operations reorganize elements without changing their values; joining and splitting combine or partition arrays.

## 2. Why we need this
Real datasets often arrive in a shape different from the one required by an algorithm or plotting routine.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.reshape` / `np.reshape`` | Change shape while preserving element order. |
| ``.ravel`` | Flatten, returning a view when possible. |
| ``.flatten`` | Flatten into a copy. |
| ``.squeeze` / `np.squeeze`` | Remove axes of length one. |
| ``np.expand_dims` / `np.newaxis`` | Insert a length-one axis. |
| ``np.transpose`, `.T`, `np.swapaxes`` | Reorder axes. |
| ``np.concatenate`` | Join arrays along an existing axis. |
| ``np.stack`, `hstack`, `vstack`, `dstack`` | Join arrays by creating or choosing axes. |
| ``np.split`, `array_split`, `hsplit`, `vsplit`` | Partition arrays. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
a = np.arange(6)
print(a.reshape(2, 3))
print(a[:, np.newaxis].shape)  # (6, 1)
print(a.reshape(-1))           # [0 1 2 3 4 5]
```

## 5. Advanced examples
```python
left = np.array([[1, 2], [3, 4]])
right = np.array([[5, 6]])
print(np.concatenate([left, right], axis=0))
# [[1 2]
#  [3 4]
#  [5 6]]
```

## 6. Practical real-world applications
Convert flattened image data to height-width-channel arrays, combine batches, and prepare matrices for numerical algorithms.

## 7. Common mistakes
Reshape requires a compatible element count; concatenation requires matching non-joined dimensions; `flatten` copies while `ravel` may return a view.

## 8. Practice questions
Convert 24 values into shape (2,3,4); stack two vectors; split an array into three parts.

## 9. Interview questions
Difference between `reshape`, `ravel` and `flatten`? What is the difference between `stack` and `concatenate`?

## 10. Related functions and concepts
ndarray shape, axes, indexing, views and broadcasting.
