# California Housing Price Prediction

## Project Overview

This project applies machine learning regression techniques to predict median house values in California districts.

The objective is to build, evaluate, and compare several regression models, improve predictive performance through feature engineering and hyperparameter tuning, and identify the factors that contribute most to housing prices.

## Dataset

The project uses the California Housing dataset.

- **Total records:** 20,640
- **Target variable:** `median_house_value`
- **Task type:** Supervised regression

The dataset includes information about housing districts, such as median income, housing age, average rooms, population, and geographical location.

## Project Workflow

### 1. Exploratory Data Analysis

- Examined dataset structure and statistical summaries.
- Investigated feature distributions and relationships.
- Explored correlations between input features and median house values.

### 2. Data Preprocessing

- Checked for missing values.
- Applied numerical imputation where needed.
- Scaled numerical features.
- Encoded categorical variables using one-hot encoding.

### 3. Feature Engineering

Created additional features and interaction features to help models capture relationships between housing characteristics.

### 4. Model Development

Implemented and compared several regression algorithms:

- Ordinary Least Squares (OLS) Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- Extra Trees Regressor
- HistGradientBoosting Regressor

### 5. Hyperparameter Tuning

Applied hyperparameter optimization to improve model performance, including tuning the HistGradientBoosting model.

### 6. Model Evaluation

Models were evaluated using three regression metrics:

- **RMSE:** Measures the typical magnitude of prediction errors, with greater penalty for large errors.
- **MAE:** Measures the average absolute prediction error.
- **R²:** Measures the proportion of variance in the target variable explained by the model.

## Model Performance

The final models were evaluated on the test dataset.

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| HistGradientBoosting | **45,066.20** | 29,688.57 | **0.8450** |
| Tuned HistGradientBoosting | 45,070.13 | **29,411.32** | 0.8450 |
| Random Forest | 48,737.00 | 31,431.63 | 0.8187 |
| Extra Trees | 50,313.56 | 32,898.45 | 0.8068 |
| OLS | 69,127.04 | 49,645.49 | 0.6353 |
| Lasso | 69,130.57 | 49,648.47 | 0.6353 |
| Ridge | 69,134.97 | 49,652.14 | 0.6353 |

## Visualizations and Results

The `results/` directory contains the following visualizations and evaluation files:

| File | Description |
|---|---|
| `actual_vs_predicted.png` | Comparison of actual and predicted housing prices |
| `correlation_heatmap.png` | Correlation between numerical features |
| `engineered_feature_correlation...` | Correlation analysis of engineered features |
| `final_model_comparison.png` | Visual comparison of regression model performance |
| `final_model_comparison.csv` | Numerical comparison of all evaluated models |
| `linear_models_residual_distribu...` | Residual distributions for linear models |
| `permutation_feature_importan...` | Feature importance based on permutation |
| `residual_distribution_comparis...` | Comparison of residual distributions |
| `residual_plot.png` | Analysis of prediction residuals |
| `ridge_predicted_vs_actual.png` | Ridge regression predictions versus actual values |


**Best overall results:** HistGradientBoosting achieved the lowest RMSE and highest R², while the tuned HistGradientBoosting model achieved the lowest MAE.

The two HistGradientBoosting versions performed very similarly, demonstrating that hyperparameter tuning produced only a small change in overall performance.

## Model Interpretation and Analysis

Additional analysis was conducted to understand model behavior and identify influential features.

- Permutation feature importance was used to examine the contribution of input features.
- Residual analysis was performed to investigate prediction errors.
- Model predictions and evaluation metrics were compared to understand differences between linear and tree-based methods.

The HistGradientBoosting models achieved an R² of approximately 0.845, indicating that they explained around 84.5% of the variance in the test-set housing values.

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Conclusion

This project demonstrates a complete machine learning regression workflow, from exploratory data analysis and preprocessing to feature engineering, model training, hyperparameter tuning, and evaluation.

Tree-based ensemble methods significantly outperformed the linear regression models on this dataset.

HistGradientBoosting achieved the strongest overall results, with an RMSE of approximately 45,066 and an R² of 0.845.

The project highlights the importance of model comparison, feature engineering, and evaluation using multiple regression metrics rather than relying on a single performance measure.