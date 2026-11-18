# NumPy: Array Creation and Initialization

## 1. Introduction and definition
Array-creation routines build arrays from values, ranges, shapes, sampling rules or existing data.

## 2. Why we need this
Choosing the right constructor makes intent explicit and helps control shape, dtype and reproducibility.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``np.array`, `np.asarray`` | Build arrays from array-like objects. |
| ``np.zeros`, `np.ones`, `np.empty`` | Allocate initialized or uninitialized arrays. |
| ``np.full`` | Fill an array with a chosen constant. |
| ``np.arange`` | Create values over a half-open interval using a step. |
| ``np.linspace`` | Create a fixed number of evenly spaced values. |
| ``np.eye`, `np.identity`` | Create identity matrices. |
| ``np.diag`` | Create or extract a diagonal. |
| ``np.fromiter`, `np.fromfunction`` | Construct arrays from iterables or coordinate functions. |
| ``np.meshgrid`` | Create coordinate grids. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
print(np.zeros((2, 3)))
print(np.arange(0, 10, 2))       # [0 2 4 6 8]
print(np.linspace(0, 1, 5))      # [0.   0.25 0.5 0.75 1.  ]
```

## 5. Advanced examples
```python
grid_x, grid_y = np.meshgrid(np.arange(3), np.arange(2))
coords = np.stack([grid_x, grid_y], axis=-1)
print(coords.shape)  # (2, 3, 2)
```

## 6. Practical real-world applications
Initialize feature matrices, create time/measurement grids, generate test data and construct identity/diagonal matrices.

## 7. Common mistakes
`np.empty` contains arbitrary uninitialized memory; floating-point `arange` can produce surprising endpoints; confusing the step argument with number of samples (`linspace`).

## 8. Practice questions
Create a 5x5 identity matrix; create 100 evenly spaced values from -1 to 1; initialize a 4x3 array with -1.

## 9. Interview questions
When should `linspace` be preferred to `arange`? Why is `empty` potentially unsafe? What does `endpoint` do?

## 10. Related functions and concepts
Shapes, dtype, random generation, reshape and broadcasting.
