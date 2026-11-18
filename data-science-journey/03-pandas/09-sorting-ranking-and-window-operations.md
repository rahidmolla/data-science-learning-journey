# pandas: Sorting, Ranking and Window Operations

## 1. Introduction and definition
These methods order data, assign ranks and compute summaries over moving or cumulative windows.

## 2. Why we need this
They are useful for leaderboards, top-N analysis, time trends and rolling business metrics.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.sort_values`, `.sort_index`` | Sort by values or labels. |
| ``.nlargest`, `.nsmallest`` | Select top/bottom rows efficiently. |
| ``.rank`` | Assign ranks with configurable tie handling. |
| ``.shift`, `.diff`` | Move values or calculate differences. |
| ``.pct_change`` | Calculate fractional change between periods. |
| ``.cumsum`, `.cummax`, `.cummin`` | Cumulative calculations. |
| ``.rolling`` | Fixed-size rolling window. |
| ``.expanding`` | Growing window from the start. |
| ``.ewm`` | Exponentially weighted calculations. |
| ``.pipe`` | Compose operations by passing an object into a function. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
s = pd.Series([100, 120, 90, 135])
print(s.pct_change().round(2).tolist())
print(s.rolling(2).mean().tolist())
```

## 5. Advanced examples
```python
df = pd.DataFrame({"date": pd.date_range("2026-01-01", periods=4), "sales": [10, 15, 12, 20]})
df["change"] = df["sales"].diff()
df["rolling_2"] = df["sales"].rolling(2, min_periods=1).mean()
print(df)
```

## 6. Practical real-world applications
Calculate daily revenue changes, moving averages, customer rankings and top-performing products.

## 7. Common mistakes
Calculating time windows before sorting by time; forgetting `min_periods`; interpreting `pct_change` as percent rather than fraction; confusing rank methods for ties.

## 8. Practice questions
Rank scores; calculate day-over-day changes; compute 7-day moving average; find top three products per category.

## 9. Interview questions
What is a rolling window? Difference between `shift` and `diff`? How does `ewm` differ from a simple moving average?

## 10. Related functions and concepts
Time series, GroupBy, sorting and statistical summaries.
