# Data Cleaning: Quality Assessment and Validation

## 1. Introduction and definition
Data cleaning identifies and corrects inaccurate, incomplete, inconsistent, duplicated or irrelevant records.

## 2. Why we need this
Reliable analysis requires a documented quality process before calculating metrics or building models.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Completeness` | Are required values present? |
| `Validity` | Do values follow allowed formats/ranges? |
| `Consistency` | Do values agree across fields/sources? |
| `Uniqueness` | Are business keys unique where expected? |
| `Accuracy` | Do values reflect reality? |
| ``isna`, `duplicated`, `describe`` | Profile common quality problems. |
| `Assertions` | Check assumptions programmatically. |
| `Schema validation` | Check column names, types and constraints. |
| ``pd.to_numeric`, `to_datetime`` | Parse values safely. |
| `Validation report` | Summarize issues, actions and unresolved risk. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"id": [1, 2, 2], "age": [20, -4, 30]})
checks = {
    "duplicate_ids": int(df["id"].duplicated().sum()),
    "invalid_age": int((df["age"] < 0).sum()),
    "missing": int(df.isna().sum().sum())
}
print(checks)
```

## 5. Advanced examples
```python
assert df["id"].notna().all()
valid_age = df["age"].between(0, 120)
print(df.loc[~valid_age])
```

## 6. Practical real-world applications
Validate customer records, transaction logs, survey results and imported files before reporting.

## 7. Common mistakes
Deleting anomalies without investigation; confusing unusual with invalid; failing to preserve raw data; silently coercing values.

## 8. Practice questions
Create five quality checks; write a validation summary; define acceptable ranges for an age or price field.

## 9. Interview questions
What are dimensions of data quality? Why preserve raw data? What is a schema contract?

## 10. Related functions and concepts
Missing data, duplicates, outliers, type conversion and data governance.
