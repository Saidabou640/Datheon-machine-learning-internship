# Datheon Machine Learning and Data Science Internship

Welcome to my GitHub repository for the Datheon Machine Learning and Data Science Internship.

This repository contains the four projects completed during the internship. Each project explores a different machine learning task, including classification, regression, customer churn prediction, and natural language processing.

## Projects

### Task 1: Multi-Class Benchmark Classification Pipeline

**Status:** Completed

- Dataset: Iris
- Task: Multi-class classification
- Models: Logistic Regression and Decision Tree
- Techniques: Data preprocessing, EDA, feature scaling, and model evaluation.

**Best test accuracy:** 96.67% (Decision Tree)

[View Task 1 Project](Task_1_Multiclass_Classification/)

### Task 2: California Housing Price Prediction

**Status:** Completed

- Dataset: California Housing
- Task: Supervised regression
- Models: Linear Regression, Ridge, Lasso, Random Forest, Extra Trees, and HistGradientBoosting.
- Techniques: Feature engineering, preprocessing, hyperparameter tuning, and residual analysis.

**Best RMSE:** $45,066.20 (HistGradientBoosting)

**Best R²:** 0.8450

[View Task 2 Project](Task_2_Housing_Price_Prediction/)

### Task 3: Customer Churn Prediction

**Status:** Completed

- Dataset: IBM Telco Customer Churn
- Task: Binary classification
- Models: Random Forest and XGBoost.
- Techniques: Class imbalance handling, stratified cross-validation, hyperparameter optimization, and feature importance analysis.

**Best ROC-AUC:** 84.84% (Tuned XGBoost)

[View Task 3 Project](Task_3_Customer_Churn_Prediction/)

### Task 4: Sentiment Classification

**Status:** Completed

- Dataset: Women's Clothing E-Commerce Reviews and Datheon Sentiment Reviews
- Task: Sentiment classification of customer reviews.
- Models: Multinomial Naive Bayes and Logistic Regression.
- Techniques: Text preprocessing, TF-IDF vectorization, class balancing, and sentiment prediction.

**Best macro F1-score:** 59.22% (Balanced Logistic Regression)

[View Task 4 Project](Task_4_Sentiment_Classification/)

## Technologies and Tools

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- NLTK
- Jupyter Notebook
- Git and GitHub

## Repository Structure

```text
Datheon_Internship/
├── Task_1_Multiclass_Classification/
│   ├── data/
│   ├── notebooks/
│   ├── results/
│   ├── README.md
│   └── requirements.txt
├── Task_2_Housing_Price_Prediction/
│   ├── data/
│   ├── notebooks/
│   ├── results/
│   ├── README.md
│   └── requirements.txt
├── Task_3_Customer_Churn_Prediction/
│   ├── data/
│   ├── notebooks/
│   ├── results/
│   ├── README.md
│   └── requirements.txt
├── Task_4_Sentiment_Classification/
│   ├── data/
│   ├── notebooks/
│   ├── outputs/
│   ├── README.md
│   └── requirements.txt
└── README.md
```

## Installation and Usage

1. Clone the repository:

```bash
git clone https://github.com/Saidabou640/Datheon-machine-learning-internship.git
```

2. Navigate to the project folder:

```bash
cd Datheon-machine-learning-internship
```

3. Open the folder in VS Code.

4. For each task, follow the installation instructions in its individual README and install the corresponding requirements.

5. Open the Jupyter Notebook in the task's `notebooks` folder and run the cells.

## About

This repository was created as part of my participation in the Datheon Machine Learning and Data Science Internship. It documents the projects, experiments, and results completed throughout the internship.