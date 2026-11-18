# pandas: File IO, Chunking and Performance

## 1. Introduction and definition
pandas reads and writes tabular data in common formats and offers options to control parsing, memory and output.

## 2. Why we need this
Efficient and reproducible IO is necessary when datasets are large or come from multiple sources.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``read_csv`, `to_csv`` | Read/write CSV files. |
| ``read_excel`, `to_excel`` | Read/write Excel workbooks. |
| ``read_json`, `to_json`` | Read/write JSON. |
| ``read_parquet`, `to_parquet`` | Read/write columnar Parquet. |
| ``read_sql`, `to_sql`` | Read from/write to SQL databases. |
| ``read_fwf`` | Read fixed-width formatted text. |
| ``read_pickle`, `to_pickle`` | Python-specific object serialization; use cautiously. |
| ``chunksize`` | Read large files in iterable chunks. |
| ``usecols`, `dtype`, `parse_dates`` | Control parsing and memory. |
| ``.memory_usage`, `category`` | Inspect and reduce memory usage. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.read_csv("sales.csv", usecols=["date", "amount"], parse_dates=["date"])
df.to_csv("clean_sales.csv", index=False)
```

## 5. Advanced examples
```python
total = 0
for chunk in pd.read_csv("large.csv", usecols=["amount"], chunksize=100_000):
    total += pd.to_numeric(chunk["amount"], errors="coerce").sum()
print(total)
```

## 6. Practical real-world applications
Load business exports, store analytical tables, process files larger than memory and exchange data with databases.

## 7. Common mistakes
Using pickle for untrusted files; forgetting `index=False` when exporting; loading unnecessary columns; treating CSV as a typed format; not documenting encoding and date parsing.

## 8. Practice questions
Read selected columns; write a clean CSV; read a large file in chunks; compare CSV and Parquet.

## 9. Interview questions
When use Parquet? How does `chunksize` help? Why specify dtypes? What are risks of pickle?

## 10. Related functions and concepts
Data gathering, validation, databases, memory optimization and reproducibility.
