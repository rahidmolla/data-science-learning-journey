# NumPy: Broadcasting, Vectorization and Universal Functions

## 1. Introduction and definition
Broadcasting allows compatible shapes to participate in element-wise operations without manually copying data. Vectorization applies operations to whole arrays; ufuncs are optimized element-wise functions.

## 2. Why we need this
These ideas reduce Python loops, improve clarity and often improve performance.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Broadcasting rules` | Compare dimensions from the right; dimensions must match or one must be 1. |
| ``np.broadcast_to`` | Expose a broadcasted view with a target shape. |
| ``np.broadcast_arrays`` | Broadcast multiple arrays to a common shape. |
| ``np.vectorize`` | Convenience wrapper; generally not a performance optimization. |
| `Ufunc methods `.reduce`, `.accumulate`, `.outer`` | Apply reductions, cumulative operations or outer operations. |
| ``np.add`, `np.subtract`, `np.multiply`, `np.divide`` | Element-wise arithmetic ufuncs. |
| ``np.clip`` | Limit values to a range. |
| ``np.where`` | Perform vectorized conditional selection. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
prices = np.array([100, 200, 300])
tax_rates = np.array([0.05, 0.10])
total = prices[:, None] * (1 + tax_rates)
print(total)
# [[105. 110.]
#  [210. 220.]
#  [315. 330.]]
```

## 5. Advanced examples
```python
x = np.array([1, 2, 3, 4])
print(np.add.reduce(x))       # 10
print(np.add.accumulate(x))   # [ 1  3  6 10]
print(np.clip(x, 2, 3))       # [2 2 3 3]
```

## 6. Practical real-world applications
Calculate tax scenarios, normalize measurements, apply thresholds and compute transformations across millions of values.

## 7. Common mistakes
Assuming any two shapes broadcast; forgetting to add a new axis; using `np.vectorize` expecting compiled speed; creating huge intermediate arrays unnecessarily.

## 8. Practice questions
Explain why (3,1) and (1,4) broadcast; calculate pairwise combinations; replace all values below a threshold.

## 9. Interview questions
State the broadcasting rules. Why is vectorization useful? Is `np.vectorize` equivalent to a compiled ufunc?

## 10. Related functions and concepts
Shapes, axes, ufuncs, memory use and array operations.
