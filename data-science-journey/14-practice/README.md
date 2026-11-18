# Practice Problems

Solve these in a notebook and commit your solutions. Use small synthetic data first, then a public dataset.

## NumPy
1. Create arrays of dimensions 1, 2 and 3; inspect shape, dtype and size.
2. Reshape 24 values into `(2, 3, 4)` and explain axis meaning.
3. Use boolean masks to replace negative values.
4. Demonstrate broadcasting between `(5, 1)` and `(1, 4)`.
5. Compare `mean`, `median`, `std`, `percentile` and NaN-aware variants.
6. Use `argsort` to find top-N indexes.
7. Simulate dice rolls with `default_rng`.
8. Solve a linear system with `np.linalg.solve`.

## pandas
1. Create Series from list, dict and NumPy array.
2. Create DataFrames from records and dictionaries.
3. Select with `loc`, `iloc`, `at`, `iat`.
4. Filter rows using multiple conditions and `.query`.
5. Convert mixed strings to numeric with invalid values handled.
6. Count and visualize missingness.
7. Fill numeric and categorical missing values with documented rules.
8. Find duplicates using full rows and business keys.
9. Group by two columns and aggregate multiple metrics.
10. Compare `agg`, `transform` and `apply`.
11. Perform inner, left, right and outer merges; inspect row counts.
12. Concatenate monthly extracts with source keys.
13. Reshape wide to long with `melt`; create a pivot table.
14. Calculate rolling averages and period-over-period change.

## Statistics and EDA
1. Compare mean and median for a skewed distribution.
2. Explain an IQR outlier flag without automatically deleting it.
3. Simulate a binomial process and compare theoretical and observed results.
4. Explain a confidence interval in plain language.
5. Interpret correlation and list plausible confounders.
6. Write five insights with evidence and caveats.

## Visualization
1. Match 15 analytical questions to chart types.
2. Recreate the chart gallery in Matplotlib.
3. Use Seaborn `hue`, `col` and `row`.
4. Build a Plotly chart with hover fields and facets.
5. Create a heatmap with a meaningful color center.
6. Create an interactive Folium map using public coordinates.
7. Build a Streamlit CSV explorer.

## Preprocessing
1. Split data before fitting imputation/scaling.
2. Compare StandardScaler, MinMaxScaler and RobustScaler.
3. One-hot encode categories and handle unseen values.
4. Build a ColumnTransformer and Pipeline.
5. Identify leakage in five scenarios.
