# pandas: Missing Values and Duplicate Records

## 1. Introduction and definition
Missing values represent absent or unknown data; duplicates represent repeated records that may or may not be valid.

## 2. Why we need this
Unresolved missingness and duplicate records can distort counts, averages, joins and model features.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.isna`, `.isnull`` | Detect missing values. |
| ``.notna`, `.notnull`` | Detect present values. |
| ``.dropna`` | Remove rows or columns with missing values. |
| ``.fillna`` | Replace missing values. |
| ``.ffill`, `.bfill`` | Propagate neighboring values. |
| ``.interpolate`` | Estimate values between observations. |
| ``.duplicated`` | Mark duplicate rows or selected keys. |
| ``.drop_duplicates`` | Remove duplicate rows. |
| ``.replace`` | Replace specified values or patterns. |
| ``.isna().sum()`` | Count missing values by column. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"age": [20, None, 30], "city": ["A", "B", None]})
print(df.isna().sum())
print(df["age"].fillna(df["age"].median()))
```

## 5. Advanced examples
```python
records = pd.DataFrame({"id": [1, 2, 2], "value": [10, 20, 20]})
print(records.duplicated().sum())
deduped = records.drop_duplicates(subset=["id"], keep="first")
print(deduped)
```

## 6. Practical real-world applications
Prepare reliable customer, transaction and sensor datasets while preserving meaningful records.

## 7. Common mistakes
Filling all columns with one statistic; dropping missing rows without measuring impact; deleting duplicates without defining a business key; forward-filling across unrelated entities.

## 8. Practice questions
Find missing values by column; impute numeric median and categorical mode; count duplicates; remove duplicates based on an ID.

## 9. Interview questions
What is the difference between `isna` and `notna`? When is interpolation appropriate? How do you decide which duplicate to keep?

## 10. Related functions and concepts
Data validation, outliers, GroupBy, imputation and preprocessing.
