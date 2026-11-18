# Data Science Roadmap

This is a competency-based sequence, not a fixed deadline. Move forward when you can explain the concept and use it independently.

## Phase 1 — Python foundations
- Variables, types, operators, conditions, loops
- Functions, scope, comprehensions, iterators and generators
- Exceptions, modules, packages, virtual environments
- OOP fundamentals, files, JSON, CSV
- Type hints, testing basics, debugging and clean code

**Exit check:** Build a command-line program that loads a CSV/JSON file, validates it, summarizes it and writes a report.

## Phase 2 — NumPy
- `ndarray`, dimensions, shape, dtype, memory/layout basics
- Array creation, indexing, slicing, boolean/fancy indexing
- Reshaping, transposing, joining and splitting
- Broadcasting, vectorization, ufuncs
- Mathematical, statistical, sorting, searching and set operations
- Random sampling and linear algebra

**Exit check:** Solve array problems without Python loops where vectorized NumPy is clearer.

## Phase 3 — pandas
- Series and DataFrame construction, attributes and indexes
- Selection with `loc`, `iloc`, `at`, `iat`
- Filtering, sorting, ranking and conditional assignment
- Missing values, duplicates, type conversion and string/date operations
- Descriptive statistics, GroupBy, `agg`, `transform`, `apply`
- Merge, join, concat, pivot, melt and reshaping
- CSV, Excel, JSON, Parquet and SQL IO

**Exit check:** Clean a messy dataset, document decisions, perform grouped analysis and export a reproducible result.

## Phase 4 — Statistics
- Population/sample, variables and measurement scales
- Mean, median, mode, variance, standard deviation, quantiles
- Probability, conditional probability, Bayes' theorem
- Common distributions and sampling
- Confidence intervals, hypothesis tests, p-values and effect sizes
- Correlation, covariance and simple regression intuition

**Exit check:** Explain uncertainty and avoid treating correlation as causation.

## Phase 5 — Data collection and quality
- Local files, databases, APIs and JSON
- Data provenance, schemas, validation and reproducibility
- Missingness, duplicates, inconsistent categories, invalid values
- Outlier investigation and data-quality reports

**Exit check:** Create a documented data-ingestion and validation pipeline.

## Phase 6 — EDA and visualization
- Univariate, bivariate and multivariate analysis
- Matplotlib, Seaborn, Plotly
- Altair, Bokeh, Folium/GeoPandas and Streamlit
- Chart selection, accessibility, annotation and storytelling

**Exit check:** Deliver an EDA report with a question, evidence, chart, interpretation and caveat for every key finding.

## Phase 7 — Data preprocessing
- Train/validation/test splits
- Imputation, scaling, encoding and transformations
- Feature construction, leakage prevention and pipelines
- Class imbalance and reproducible preprocessing

**Exit check:** Prepare features without leaking information from validation/test data.

## Phase 8 — Portfolio
Complete at least three projects:
1. Business sales / retail EDA
2. Public health, sports or transport dataset analysis (respect data licenses and privacy)
3. Interactive dashboard with documented insights

Each project should contain a clear README, data source/license, reproducible environment, notebook/script, visualizations, conclusions and limitations.

## Readiness checklist
- [ ] I can explain the concept without reading the page.
- [ ] I can write a small example from memory.
- [ ] I can debug a common error.
- [ ] I can select the right tool for a problem.
- [ ] I can explain the result to a non-technical person.
- [ ] I can state assumptions and limitations.
