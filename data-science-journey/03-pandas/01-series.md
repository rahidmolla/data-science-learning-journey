# pandas Series

## 1. Introduction and definition
A Series is a one-dimensional labeled array. It contains values and an index, so data can be selected and aligned by labels.

## 2. Why we need this
Series is the basic pandas structure for a single variable such as sales, age, price or category.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``pd.Series`` | Construct a Series from list, array, dict or scalar. |
| ``.index`, `.values`, `.array`` | Inspect labels and underlying values/extension array. |
| ``.dtype`, `.shape`, `.size`, `.name`` | Inspect metadata. |
| ``.head`, `.tail`, `.sample`` | Preview or sample values. |
| ``.loc`, `.iloc`, `.at`, `.iat`` | Select by label, position or scalar access. |
| ``.astype`` | Convert dtype. |
| ``.to_list`, `.to_numpy`` | Export values. |
| ``.value_counts`, `.unique`, `.nunique`` | Explore distinct values and frequencies. |
| ``.map`, `.apply`, `.where`, `.mask`` | Transform or conditionally retain/replace values. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
scores = pd.Series([80, 92, 75], index=["Asha", "Ravi", "Mina"], name="score")
print(scores["Ravi"])       # 92
print(scores.mean())        # 82.333...
print(scores.index.tolist())
```

## 5. Advanced examples
```python
scores = pd.Series([80, 92, None, 75], index=["Asha", "Ravi", "Mina", "Mina2"])
print(scores.fillna(scores.median()))
print(scores[scores >= 80].sort_values(ascending=False))
```

## 6. Practical real-world applications
Represent a single column, inspect categories, calculate summaries and transform one variable before joining it to a DataFrame.

## 7. Common mistakes
Assuming integer indexing always means position; forgetting labels align during arithmetic; confusing `map` and `apply`; using chained assignment after selecting a view.

## 8. Practice questions
Create a Series from a dictionary; select by label and position; count categories; fill missing values with median.

## 9. Interview questions
What is a Series? How does its index work? Difference between `loc` and `iloc`? What happens when two Series with different indexes are added?

## 10. Related functions and concepts
DataFrame columns, Index objects, alignment, missing values and vectorized operations.
