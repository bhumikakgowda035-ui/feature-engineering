# Feature Engineering Project

## Overview
This project demonstrates feature engineering for a regression problem using the **UCI Wine Quality - Red Wine** dataset.

Techniques implemented:
1. Initial data cleaning and baseline Linear Regression
2. Polynomial features and interaction terms using Scikit-Learn
3. Custom `log1p` mathematical transformations for skewed numerical variables
4. Retraining and comparison using MAE, RMSE and R²
5. Interpretation of model performance and complexity

## Dataset
UCI Machine Learning Repository - Wine Quality (Red Wine):
https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-red.csv

Target column: `quality`

## Project Structure
```text
feature_engineering_project/
├── README.md
├── requirements.txt
├── notebooks/
│   └── feature_engineering.ipynb
├── docs/
│   └── impact_report.md
└── data/
    └── raw_dataset_info.txt
```

## How to Run
### Google Colab
1. Upload `notebooks/feature_engineering.ipynb` to Google Colab.
2. Run the cells from top to bottom.
3. The notebook downloads the dataset automatically.
4. Check the final comparison table and plots.

### Local Python
Install dependencies:
```bash
pip install -r requirements.txt
```
Then open the notebook with Jupyter Notebook or VS Code.

## Expected Output
The notebook produces:
- dataset inspection and missing-value checks
- baseline regression metrics
- polynomial regression metrics
- polynomial + log-transform metrics
- RMSE and R² comparison plots
- interpretation notes

## Important
The test set is kept separate from model fitting to reduce data leakage. The log transformation is applied consistently to training and test data before the engineered model is evaluated.
