# NumPy: Sorting, Searching and Set Operations

## 1. Introduction and definition
These routines order values, locate insertion points, find matching indexes and perform set-like operations on arrays.

## 2. Why we need this
They are useful for ranking, thresholding, deduplication and efficient lookup.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``np.sort`, `.sort`` | Return a sorted copy or sort in place. |
| ``np.argsort`` | Return the indexes that would sort an array. |
| ``np.partition`, `np.argpartition`` | Place selected order statistics without fully sorting. |
| ``np.searchsorted`` | Find insertion positions in sorted data. |
| ``np.argmax`, `np.argmin`` | Find positions of extreme values. |
| ``np.unique`` | Return unique values and optional counts/indexes. |
| ``np.isin`` | Test membership in a set of values. |
| ``np.intersect1d`, `union1d`, `setdiff1d`` | Set operations on 1D arrays. |
| ``np.lexsort`` | Indirect stable sort by multiple keys. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
x = np.array([30, 10, 20, 10])
print(np.sort(x))                 # [10 10 20 30]
print(np.argsort(x))              # [1 3 2 0]
print(np.unique(x, return_counts=True))
```

## 5. Advanced examples
```python
sorted_x = np.array([10, 20, 30, 40])
print(np.searchsorted(sorted_x, [15, 35]))  # [1 3]
print(np.isin([10, 25, 40], sorted_x))      # [ True False  True]
```

## 6. Practical real-world applications
Rank top products, find percentile cutoffs, detect unique categories and match IDs.

## 7. Common mistakes
Using `searchsorted` on unsorted input; confusing sorted values with sort indexes; forgetting tie behavior; using set operations when row order matters.

## 8. Practice questions
Find indexes of the top three values; count unique categories; find values present in one array but not another.

## 9. Interview questions
Difference between `sort` and `argsort`? What does `partition` optimize? Why must input be sorted for `searchsorted`?

## 10. Related functions and concepts
Indexing, ranking, quantiles, categorical data and joins.
