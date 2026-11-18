# pandas: GroupBy, Aggregation, Apply and Transform

## 1. Introduction and definition
GroupBy follows split-apply-combine: split rows into groups, compute within groups, then combine results.

## 2. Why we need this
It answers business questions such as revenue by month, average score by class and top product by region.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.groupby`` | Create grouped operations using one or more keys. |
| ``.agg` / `.aggregate`` | Compute one or multiple summaries. |
| ``.transform`` | Return group-level calculations aligned to original rows. |
| ``.apply`` | Apply a custom function; use built-in operations when possible. |
| ``.filter`` | Keep or discard entire groups. |
| ``.get_group`` | Retrieve one named group. |
| ``.size`, `.count`` | Count rows or non-null values within groups. |
| ``.value_counts`` | Frequency table, optionally normalized. |
| ``.rolling`, `.expanding`` | Window calculations. |
| ``.resample`` | Time-based grouping for datetime indexes. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"team": ["A", "A", "B", "B"], "runs": [10, 20, 15, 25]})
print(df.groupby("team")["runs"].mean())
# A 15.0; B 20.0
```

## 5. Advanced examples
```python
df["team_mean"] = df.groupby("team")["runs"].transform("mean")
summary = df.groupby("team").agg(
    total_runs=("runs", "sum"),
    average_runs=("runs", "mean"),
    highest_runs=("runs", "max")
)
print(summary)
```

## 6. Practical real-world applications
Create monthly revenue reports, compare teams, compute within-group rankings and calculate rolling metrics.

## 7. Common mistakes
Using `apply` when `agg` or `transform` is clearer/faster; forgetting `as_index`; assuming group order; confusing `size` and `count`; using a non-datetime index with `resample`.

## 8. Practice questions
Find mean by genre; count rows per team; add group mean to each row; calculate monthly revenue; retain groups with at least five rows.

## 9. Interview questions
Explain split-apply-combine. Difference between `agg`, `transform` and `apply`? What does `as_index` do?

## 10. Related functions and concepts
Joins, pivot tables, window functions, SQL GROUP BY and time series.
