# pandas DataFrame: Creation and Inspection

## 1. Introduction and definition
A DataFrame is a two-dimensional labeled table with row and column axes. Columns can have different dtypes.

## 2. Why we need this
Most tabular datasets—CSV files, database query results and spreadsheets—are represented as DataFrames.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``pd.DataFrame`` | Construct a DataFrame from dicts, lists, arrays or records. |
| ``pd.read_csv`, `read_excel`, `read_json`, `read_parquet`` | Load common data formats. |
| ``.head`, `.tail`, `.sample`` | Preview rows. |
| ``.info`` | Show column types and non-null counts. |
| ``.describe`` | Generate descriptive summaries. |
| ``.shape`, `.size`, `.ndim`` | Inspect dimensions and element count. |
| ``.columns`, `.index`, `.dtypes`` | Inspect labels and column types. |
| ``.memory_usage`` | Estimate memory use. |
| ``.select_dtypes`` | Select columns by dtype. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"name": ["Asha", "Ravi"], "score": [91, 84]})
print(df.shape)       # (2, 2)
print(df.columns.tolist())
print(df.head())
```

## 5. Advanced examples
```python
numeric = df.select_dtypes(include="number")
summary = numeric.describe().T
print(summary)
```

## 6. Practical real-world applications
Load, inspect and profile a dataset before cleaning or analysis.

## 7. Common mistakes
Trusting inferred dtypes without checking; loading huge files without considering `usecols`, `dtype` or chunking; confusing rows with columns in `shape`.

## 8. Practice questions
Build a DataFrame from records; inspect dtypes; select numeric columns; estimate memory usage.

## 9. Interview questions
Difference between Series and DataFrame? What does `info()` show? Why inspect dtypes before analysis?

## 10. Related functions and concepts
IO, dtype conversion, selection, missingness and data profiling.
