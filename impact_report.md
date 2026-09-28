# Feature Engineering Impact Report

## 1. Objective
The objective was to determine whether engineered features could improve a baseline regression model. The project used the UCI Wine Quality (Red Wine) dataset and Linear Regression.

## 2. Dataset
The dataset contains physicochemical measurements of red wine and a `quality` target. The target is treated as a regression value.

Source:
UCI Machine Learning Repository - Wine Quality:
https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-red.csv

## 3. Baseline
A Linear Regression pipeline was trained after a train/test split. Median imputation and standardization were included in the pipeline.

The baseline metrics are calculated automatically in the notebook:
- MAE
- RMSE
- R²

## 4. Polynomial Features
Degree-2 polynomial features were added with Scikit-Learn `PolynomialFeatures`. This creates squared terms and pairwise interaction terms.

Potential benefit: the linear model can represent some non-linear relationships.

Trade-off: the number of features increases substantially, making the model more complex and potentially more sensitive to overfitting.

## 5. Mathematical Transformation
The variables `residual sugar`, `free sulfur dioxide`, and `total sulfur dioxide` were transformed with `log1p`.

Reason:
- These variables can have right-skewed distributions.
- `log1p(x)` compresses large values.
- `log1p` is safe for zero values.

## 6. Performance Comparison
Run the notebook to populate the final comparison table. Compare:
- MAE: lower is better
- RMSE: lower is better
- R²: higher is better

The notebook compares:
1. Baseline Linear Regression
2. Polynomial Linear Regression
3. Polynomial + Log Transform

Do not assume that feature engineering always improves every metric. The actual test-set results from the completed notebook should be reported.

## 7. Interpretability
The baseline model is easier to explain because each original variable has one coefficient. Polynomial engineering adds squared and interaction terms, which makes the model harder to interpret but allows richer relationships.

Log-transformed variables are still understandable because the transformation has a clear mathematical meaning: a one-unit change in transformed space corresponds to a multiplicative change on the original scale.

## 8. Conclusion
Feature engineering provides additional ways for a simple linear model to capture non-linear structure. The final choice should consider both predictive metrics and model complexity. The completed notebook's test-set results are the evidence used for the final conclusion.
