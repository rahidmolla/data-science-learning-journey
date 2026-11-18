# pandas: Merge, Join, Concat, Pivot and Reshape

## 1. Introduction and definition
Combining operations align datasets by keys, indexes or row/column position; reshaping changes the layout between wide and long forms.

## 2. Why we need this
Real analysis often combines customer, order, product and time tables or reshapes data for plotting.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``pd.merge` / `.merge`` | Database-style joins using columns or indexes. |
| ``.join`` | Join primarily on indexes. |
| ``pd.concat`` | Stack objects along rows or columns. |
| ``.pivot`` | Reshape unique index/column pairs. |
| ``.pivot_table`` | Pivot with aggregation for duplicate combinations. |
| ``.melt`` | Convert wide data to long format. |
| ``.stack`, `.unstack`` | Move levels between columns and index. |
| ``.explode`` | Expand list-like values into rows. |
| ``.crosstab`` | Frequency cross-tabulation. |
| ``.compare`` | Show differences between aligned DataFrames. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
customers = pd.DataFrame({"id": [1, 2], "name": ["A", "B"]})
orders = pd.DataFrame({"id": [1, 1, 3], "amount": [50, 70, 90]})
print(customers.merge(orders, on="id", how="left"))
```

## 5. Advanced examples
```python
wide = pd.DataFrame({"month": ["Jan", "Feb"], "A": [10, 12], "B": [8, 9]})
long = wide.melt(id_vars="month", var_name="team", value_name="sales")
print(long)
print(pd.crosstab(long["month"], long["team"], values=long["sales"], aggfunc="sum"))
```

## 6. Practical real-world applications
Combine sales with customer details, append monthly extracts, reshape survey results and prepare long-form chart data.

## 7. Common mistakes
Joining on non-unique keys can multiply rows; failing to validate join cardinality; confusing concat with merge; pivot fails when index/column pairs are duplicated; losing provenance when appending sources.

## 8. Practice questions
Perform inner/left/right/outer joins; concatenate two months with keys; convert wide to long; build a pivot table.

## 9. Interview questions
Difference between merge and concat? What does `validate` do in merge? When use pivot_table rather than pivot?

## 10. Related functions and concepts
SQL joins, GroupBy, indexes, data modeling and visualization.
