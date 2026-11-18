# Data Preprocessing: Splits, Leakage and Pipelines

## 1. Introduction and definition
Preprocessing transforms raw features into model-ready inputs. Data splitting separates training from evaluation; pipelines make transformations repeatable.

## 2. Why we need this
Correct split and pipeline design prevents overly optimistic evaluation and inconsistent production processing.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``train_test_split`` | Split data into random train/test subsets. |
| `Stratification` | Preserve class proportions in classification splits. |
| `Time-based split` | Respect chronological order for temporal data. |
| `Data leakage` | Information unavailable at prediction time enters training. |
| ``Pipeline`` | Chain transformers and estimator. |
| ``ColumnTransformer`` | Apply different transforms to different columns. |
| `Cross-validation` | Estimate performance across folds. |
| ``random_state`` | Make supported randomized operations reproducible. |
| `Fit vs transform` | Learn parameters on training data; apply them to new data. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
from sklearn.model_selection import train_test_split
X = [[1], [2], [3], [4], [5], [6]]
y = [0, 0, 0, 1, 1, 1]
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.33, random_state=42, stratify=y
)
print(len(X_train), len(X_test))
```

## 5. Advanced examples
```python
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
pipe = Pipeline([
    ("impute", SimpleImputer(strategy="median")),
    ("scale", StandardScaler()),
    ("model", LogisticRegression())
])
```

## 6. Practical real-world applications
Build repeatable model preparation, evaluate generalization and keep transformations consistent between training and inference.

## 7. Common mistakes
Scaling before splitting; using future information in time-series features; tuning on the test set; fitting preprocessing separately at prediction time.

## 8. Practice questions
Design a time-aware split; identify leakage in a scenario; build a pipeline with imputation and scaling.

## 9. Interview questions
What is data leakage? Difference between fit and transform? Why use a pipeline?

## 10. Related functions and concepts
Scaling, encoding, imputation, cross-validation and model evaluation.
