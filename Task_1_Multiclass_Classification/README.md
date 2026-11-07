# Task 1: Multi-Class Benchmark Classification Pipeline

## 1. Project Overview
This project implements a supervised multi-class classification pipeline using the Iris dataset. The objective is to train and compare Logistic Regression and Decision Tree models to classify three Iris flower species.

## 2. Dataset
The dataset contains 149 observations after removing one duplicate row, four numerical features, and three target classes: Setosa, Versicolor, and Virginica.

## 3. Data Preprocessing
- Checked for missing values.
- Identified and removed one duplicate row.
- Separated features and target labels.
- Split the data into 80% training and 20% testing sets.
- Applied StandardScaler, fitting it only on the training data.

## 4. Exploratory Data Analysis
Exploratory Data Analysis included statistical summaries, a species distribution plot, and pairwise feature visualizations using Seaborn.

The pairplot showed that Setosa is relatively easy to distinguish, while Versicolor and Virginica have some overlapping measurements.

## 5. Models
Two classification algorithms were trained:
1. Logistic Regression
2. Decision Tree (maximum depth = 3)

## 6. Evaluation Results

| Metric | Logistic Regression | Decision Tree |
|---|---:|---:|
| Accuracy | 93.33% | 96.67% |
| Precision | 93.33% | 96.97% |
| Recall | 93.33% | 96.67% |
| F1-score | 93.33% | 96.66% |

## 7. Conclusion
The Decision Tree achieved the best performance on this test split, correctly classifying 29 out of 30 observations. Logistic Regression correctly classified 28 out of 30 observations.

Both models performed well. The confusion matrices showed that distinguishing Versicolor from Virginica was more difficult than identifying Setosa.

## 8. Project Structure
- `data/`: Iris dataset.
- `notebooks/`: Jupyter notebook containing the analysis and model evaluation.
- `results/`: Saved visualizations.
- `src/`: Source code, if applicable.

## 9. Tools and Libraries
Python, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn.