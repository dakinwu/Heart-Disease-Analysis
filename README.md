# Heart Disease Analysis

An R-based analysis project that explores heart disease data, examines diagnostic factors, and compares statistical and machine learning models.

## Overview

This project uses a heart disease dataset to investigate relationships between patient measurements and the recorded outcome.

The analysis combines data cleaning, visualization, feature interpretation, and predictive modeling. It examines variables such as age, chest pain type, blood pressure, cholesterol, and exercise-related measurements.

The goal is to understand which recorded factors are informative and how different modeling approaches behave on the same dataset.

## Models

| Model | Description |
| --- | --- |
| Logistic regression | Estimates the probability of a binary outcome. |
| Naive Bayes | Uses class probabilities under a simplifying assumption that predictors are conditionally independent. |
| K-nearest neighbors (KNN) | Predicts an observation's class from nearby examples. |
| Group Lasso | Regularizes related features together, allowing groups of coefficients to be reduced to zero. |
| Random forest | Combines predictions from multiple decision trees. |
| XGBoost | Builds successive decision trees to improve earlier predictions. |

## Analysis Workflow

1. Load `heart.csv`.
2. Filter selected coded values and prepare categorical variables.
3. Explore numerical and categorical relationships with the outcome.
4. Apply Principal Component Analysis (PCA), which summarizes numerical variation using fewer dimensions.
5. Split the data into training and test portions.
6. Fit and compare the models.
7. Examine coefficients, feature importance, and SHAP values (estimates of how individual features contribute to model predictions).

For example, feature importance can help identify whether a recorded measurement contributes strongly to predictions, but it does not establish that the measurement causes heart disease.

## Dataset

The original project describes the data as a Kaggle heart disease dataset. A copy is included as `heart.csv`.

The script uses the following fields:

```text
age, sex, cp, trestbps, chol, fbs, restecg,
thalach, exang, oldpeak, slope, ca, thal, target
```

Check the original dataset definitions before interpreting categorical codes or the positive class. The script recodes several variables and the outcome.

## Repository Contents

| File | Description |
| --- | --- |
| `Heart Disease Analysis.R` | Main analysis script. |
| `heart.csv` | Dataset used by the script. |
| `心臟病分析.pdf` | Detailed project report in Chinese. |

## Tools

- R for statistical analysis and modeling
- `ggplot2` and related packages for visualization
- `caret` for data splitting and evaluation utilities
- `e1071` and `class` for classification methods
- `gglasso` for Group Lasso
- `randomForest` and `ranger` for tree-based models
- `xgboost` for boosted decision trees
- `ROCit` for ROC/AUC analysis

The script also uses additional plotting functions and SHAP helpers.

## Getting Started

1. Obtain the repository files.
2. Keep `heart.csv` accessible from the R working directory.
3. Open `Heart Disease Analysis.R` in RStudio or another R environment.
4. Install and load the packages required by the functions used in each section.
5. Review the variable recoding and positive-class definition.
6. Run the script section by section to inspect intermediate data, plots, and model outputs.

The script assumes several packages and helper functions are already available in the R session.

## Evaluation and Reproducibility

Evaluation code includes:

- Accuracy: the proportion of correct predictions.
- Sensitivity: the proportion of positive cases identified.
- Specificity: the proportion of negative cases identified.
- ROC/AUC: measures describing class separation across prediction thresholds.

Some model and threshold choices use the test data. For a new performance study, use a separate validation process for tuning and retain an untouched final test set.

Package versions are not pinned. The repository documents an exploratory modeling study; clinical performance has not been established.
