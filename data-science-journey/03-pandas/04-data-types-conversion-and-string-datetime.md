# pandas: Data Types, Strings and Datetimes

## 1. Introduction and definition
pandas supports numeric, boolean, string, categorical, datetime, timedelta and nullable extension dtypes.

## 2. Why we need this
Correct types reduce memory, enable valid operations and make dates/categories analyzable.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.astype`` | Convert a column or object to a dtype. |
| ``pd.to_numeric`` | Parse numeric values with error-handling options. |
| ``pd.to_datetime`` | Parse date/time values. |
| ``pd.to_timedelta`` | Parse durations. |
| ``.convert_dtypes`` | Convert to nullable dtypes where appropriate. |
| ``.str.strip`, `.str.lower`, `.str.upper`, `.str.replace`` | Clean text. |
| ``.str.contains`, `.str.startswith`, `.str.split`` | Search or split text. |
| ``.dt.year`, `.dt.month`, `.dt.day`, `.dt.dayofweek`` | Extract datetime components. |
| ``.cat.codes`, `.cat.categories`` | Inspect categorical values/codes. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
s = pd.Series([" 10 ", "20", "unknown"])
numbers = pd.to_numeric(s.str.strip(), errors="coerce")
print(numbers.tolist())  # [10.0, 20.0, nan]
dates = pd.to_datetime(["2026-01-02", "2026-02-03"])
print(dates.month.tolist())
```

## 5. Advanced examples
```python
df = pd.DataFrame({"joined": ["2024-01-10", "not-a-date"], "city": [" Delhi ", "MUMBAI"]})
df["joined"] = pd.to_datetime(df["joined"], errors="coerce")
df["city"] = df["city"].str.strip().str.title().astype("category")
print(df.dtypes)
```

## 6. Practical real-world applications
Clean inconsistent text, parse transaction dates, reduce categorical memory and make date-based analysis possible.

## 7. Common mistakes
Parsing invalid strings without `errors='coerce'` or explicit validation; treating dates as plain strings; assuming category codes have numeric meaning; timezone-naive vs timezone-aware confusion.

## 8. Practice questions
Convert currency strings to numeric; extract year/month; standardize city names; identify invalid dates.

## 9. Interview questions
When use `category`? What does `errors='coerce'` do? Difference between `.str` and `.dt` accessors?

## 10. Related functions and concepts
Missing values, data validation, groupby, resampling and memory optimization.
