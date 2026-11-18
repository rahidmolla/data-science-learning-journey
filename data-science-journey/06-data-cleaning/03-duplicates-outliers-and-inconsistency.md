# Data Cleaning: Duplicates, Outliers and Inconsistencies

## 1. Introduction and definition
These problems include repeated records, extreme observations and inconsistent labels, units or formats.

## 2. Why we need this
Cleaning them improves metric reliability, but changes must be justified by business context.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.duplicated`, `.drop_duplicates`` | Identify/remove repeated rows or keys. |
| `IQR rule` | Flag observations outside quartile fences. |
| `Z-score` | Express distance from mean in standard deviations. |
| `Winsorization` | Cap values at chosen quantiles. |
| ``.replace`, `.str.strip`, `.str.lower`` | Normalize inconsistent labels. |
| `Unit conversion` | Standardize measurement units. |
| `Domain rules` | Check realistic ranges and cross-field constraints. |
| `Robust summaries` | Use median and IQR for skewed data. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"city": [" Delhi", "delhi", "MUMBAI"], "sales": [10, 12, 500]})
df["city"] = df["city"].str.strip().str.title()
q1, q3 = df["sales"].quantile([.25, .75])
iqr = q3 - q1
flags = (df["sales"] < q1 - 1.5*iqr) | (df["sales"] > q3 + 1.5*iqr)
print(df.assign(possible_outlier=flags))
```

## 5. Advanced examples
```python
deduped = df.drop_duplicates(subset=["city"], keep="last")
# Investigate flagged records before deciding to remove or cap them.
```

## 6. Practical real-world applications
Standardize location labels, detect duplicate orders, review extreme transaction values and harmonize units.

## 7. Common mistakes
Automatically deleting all outliers; deduplicating on the wrong key; lowercasing names where case matters; capping genuine high-value customers.

## 8. Practice questions
Normalize categories; identify duplicate IDs; compare IQR and z-score flags; propose a rule for impossible values.

## 9. Interview questions
Are outliers always errors? Difference between duplicate row and duplicate key? What is winsorization?

## 10. Related functions and concepts
EDA, robust statistics, data validation and domain knowledge.
