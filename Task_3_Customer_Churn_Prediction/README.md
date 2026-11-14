# Customer Churn Prediction

## Project Overview

This project focuses on predicting customer churn using machine learning classification algorithms. The goal is to identify customers who are likely to leave a telecommunications company and understand the factors that influence their decisions.

The project compares two machine learning models:

- Random Forest Classifier
- XGBoost Classifier

Both models are evaluated and optimized to achieve strong predictive performance, with ROC-AUC as the primary evaluation metric.

## Dataset

The project uses the IBM Telco Customer Churn dataset.

- **Total records:** 7,043 customers
- **Total original columns:** 21
- **Target variable:** `Churn`
- **Target classes:** Yes (customer churned) and No (customer stayed)

The dataset contains customer information, including tenure, contract type, internet services, payment methods, and monthly charges.

## Project Workflow

### 1. Data Exploration

- Examined dataset structure and statistical information.
- Analyzed the distribution of churn and non-churn customers.
- Checked for duplicate records and missing values.

### 2. Data Cleaning and Preprocessing

- Converted `TotalCharges` into numeric format.
- Handled 11 missing values in `TotalCharges` by replacing them with zero, as these records corresponded to customers with zero tenure.
- Removed the `customerID` identifier.
- Applied numerical imputation and standardization.
- Applied one-hot encoding to categorical variables.

### 3. Train-Test Split

The dataset was divided into:

- 80% training data
- 20% testing data

Stratified splitting was used to preserve the original class distribution.

### 4. Handling Class Imbalance

The dataset contains more non-churn customers than churn customers.

Class weighting was used to address this imbalance:

- Random Forest: `class_weight="balanced"`
- XGBoost: `scale_pos_weight`

### 5. Model Training and Cross-Validation

Two classification algorithms were trained and evaluated:

- Random Forest
- XGBoost

Stratified 5-fold cross-validation was used to evaluate model performance consistently.

### 6. Hyperparameter Optimization

RandomizedSearchCV was applied to both models to identify better hyperparameter combinations using ROC-AUC as the optimization metric.

## Model Performance

The final tuned models were evaluated on the held-out test dataset.

| Metric | Tuned Random Forest | Tuned XGBoost |
|---|---:|---:|
| Accuracy | 75.23% | 75.30% |
| Precision | 52.20% | 52.26% |
| Recall | 79.41% | 80.21% |
| F1-Score | 62.99% | 63.29% |
| ROC-AUC | 84.16% | **84.84%** |

**Best-performing model: Tuned XGBoost**

XGBoost achieved the highest ROC-AUC of 84.84%, exceeding the project target of 80%.

It also achieved slightly higher recall, precision, accuracy, and F1-score than the tuned Random Forest model.

## Feature Importance Analysis

Feature importance was extracted from the tuned XGBoost model to identify the most influential features in its predictions.

The top features included:

1. Contract type: Month-to-month
2. Online Security: No
3. Contract type: Two year
4. Internet Service: Fiber optic
5. Tech Support: No
6. Contract type: One year
7. Internet Service: DSL
8. Payment Method: Electronic check
9. Streaming Movies: Yes
10. Customer tenure

Contract type, particularly month-to-month contracts, was the most influential feature.

These importance scores describe the model's predictive behavior and do not establish causal relationships.

## Visualizations and Results

The `results/` directory contains:

- `churn_distribution.png` — Distribution of customer churn.
- `tuned_models_roc_curve.png` — ROC curve comparison between tuned models.
- `tuned_models_confusion_matrices.png` — Confusion matrices for both models.
- `top10_xgboost_feature_importance.png` — Top 10 XGBoost feature importances.
- `xgboost_feature_importance.csv` — Complete feature importance results.
- `tuned_model_comparison.csv` — Final model performance comparison.

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Imbalanced classification techniques
- Jupyter Notebook

## Conclusion

This project demonstrates how machine learning can be used to predict customer churn and identify important customer characteristics.

Both tuned models achieved ROC-AUC scores above 80%. Tuned XGBoost performed slightly better overall, achieving an ROC-AUC of 84.84%.

The results highlight the importance of contract type, online security, internet service, and customer tenure in predicting customer churn.

The project also demonstrates a complete machine learning workflow, including data cleaning, preprocessing, class imbalance handling, cross-validation, hyperparameter tuning, model evaluation, and feature importance analysis.