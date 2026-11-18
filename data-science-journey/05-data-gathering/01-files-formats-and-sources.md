# Data Gathering: Files, Formats and Sources

## 1. Introduction and definition
Data gathering is the process of acquiring raw observations from files, databases, APIs, surveys, sensors or public datasets.

## 2. Why we need this
Analysis quality depends on source reliability, coverage, definitions, collection time and licensing.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `CSV` | Simple delimited text; types are inferred. |
| `Excel` | Workbook with sheets, formulas and formatting. |
| `JSON` | Nested key-value and array structure. |
| `Parquet` | Columnar typed format with compression. |
| `SQL` | Query structured tables from a database. |
| `API` | Request data from a service over HTTP. |
| `Data dictionary` | Definitions, types, units and valid values. |
| `Data provenance` | Where data came from and how it changed. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
csv_df = pd.read_csv("input.csv")
json_df = pd.read_json("input.json")
print(csv_df.shape, json_df.shape)
```

## 5. Advanced examples
```python
# Example: inspect a source before analysis
print(csv_df.head())
print(csv_df.dtypes)
print(csv_df.isna().sum())
```

## 6. Practical real-world applications
Collect sales exports, public government datasets, sports statistics, web-service data and operational records.

## 7. Common mistakes
Using a dataset without checking its license; losing source metadata; assuming every CSV uses UTF-8/comma separators; ignoring time zones and units.

## 8. Practice questions
Write a data dictionary; compare CSV and Parquet; record provenance and license for a public dataset.

## 9. Interview questions
What is data provenance? Why use Parquet? What belongs in a data dictionary?

## 10. Related functions and concepts
APIs, SQL, data validation, cleaning and reproducibility.
