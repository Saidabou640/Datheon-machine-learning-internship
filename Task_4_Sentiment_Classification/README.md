# Task 4: Sentiment Classification on Customer Reviews

## Project Overview

This project focuses on building a Natural Language Processing (NLP) model to classify customer reviews into three sentiment categories: positive, negative, and neutral.

The project uses text preprocessing and TF-IDF (Term Frequency–Inverse Document Frequency) to convert customer reviews into numerical features. Two machine learning algorithms, Multinomial Naive Bayes and Logistic Regression, are trained and evaluated.

An additional experiment with class-weighted Logistic Regression is conducted to investigate how class balancing affects the classification of minority sentiment categories.

The project also includes a sentiment prediction function that can classify new customer reviews.
## Dataset

Two datasets were used in this project.

### 1. Datheon Sentiment Reviews Dataset

The original dataset was provided through the Datheon internship assignment. It contains 10 customer reviews labeled as positive, negative, or neutral.

Because of its very small size, it was kept as the original assignment dataset but was not used for model training and evaluation.

### 2. Women's Clothing E-Commerce Reviews Dataset

To conduct a more meaningful experiment, a larger customer review dataset was also used.

- Source: [Hugging Face – Women's Clothing E-Commerce Reviews](https://huggingface.co/datasets/Censius-AI/ECommerce-Women-Clothing-Reviews)
- Original size: 23,486 reviews
- Final size: 22,634 reviews
- Text column: `review_text`
- Target column: `sentiment`

The sentiment labels were created from the original star ratings:

| Rating | Sentiment |
|---|---|
| 1–2 stars | Negative |
| 3 stars | Neutral |
| 4–5 stars | Positive |

Rows with missing review text and duplicate review texts were removed during data preparation.

The final dataset contains three sentiment classes. However, the classes are imbalanced, with positive reviews forming the majority.
## Text Preprocessing

Before training the models, the customer reviews were cleaned and processed using NLTK and regular expressions.

The preprocessing steps included:

1. Converting all text to lowercase.
2. Removing HTML tags.
3. Removing punctuation and numbers.
4. Tokenizing the reviews into individual words.
5. Removing English stopwords.
6. Applying lemmatization to reduce words to their base forms.

After preprocessing, TF-IDF was used to convert the cleaned reviews into numerical feature vectors.

The `TfidfVectorizer` was configured with `max_features=5000`, limiting the vocabulary to the 5,000 most relevant features.

The dataset was divided into training and testing sets using an 80/20 split. Stratified sampling was applied to preserve the sentiment class proportions in both sets.## Models

Three models were trained and evaluated:

### 1. Multinomial Naive Bayes

Multinomial Naive Bayes was used as the first classification model. It is commonly applied to text classification tasks and works with the TF-IDF features.

### 2. Logistic Regression

Logistic Regression was trained as the second model to compare its performance with Naive Bayes.

### 3. Balanced Logistic Regression

Since the dataset contains significantly more positive reviews than negative and neutral reviews, an additional Logistic Regression model was trained using:

`class_weight="balanced"`

This setting adjusts the class weights during training to give more consideration to underrepresented sentiment categories.

The balanced model was evaluated separately to investigate the effect of class balancing on classification performance.
## Model Evaluation

The models were evaluated using accuracy, weighted F1-score, and macro F1-score.

The results are shown below:

| Model | Accuracy | Weighted F1 | Macro F1 |
|---|---:|---:|---:|
| Multinomial Naive Bayes | 78.20% | 69.73% | 35.73% |
| Logistic Regression | 82.00% | 79.29% | 56.43% |
| Balanced Logistic Regression | 76.32% | 78.53% | 59.22% |

### Results and Discussion

Logistic Regression achieved the highest accuracy and weighted F1-score among the three models.

However, Balanced Logistic Regression achieved the highest macro F1-score. This indicates better average F1 performance across the three sentiment categories, including the minority classes.

The confusion matrices also showed that class balancing improved the number of correctly classified negative and neutral reviews, although it reduced the number of correctly classified positive reviews.

These results demonstrate the trade-off between overall accuracy and performance across imbalanced sentiment classes.

### Confusion Matrices

The confusion matrices for all three models are available in the `outputs` folder:

- `Naive_Bayes_confusion_matrix.png`
- `Logistic_Regression_confusion_matrix.png`
- `Balanced_Logistic_Regression_confusion_matrix.png`

## Sentiment Prediction

A custom function called `predict_sentiment()` was developed to classify new customer reviews.

The function performs the following steps:

1. Takes a review written by the user.
2. Applies the same text preprocessing steps used during training.
3. Transforms the cleaned review using the fitted TF-IDF vectorizer.
4. Predicts its sentiment using the Balanced Logistic Regression model.

### Example Predictions

The function was tested using three sample reviews:

| Review | Predicted Sentiment |
|---|---|
| I absolutely love this product, it works perfectly! | Positive |
| The product is okay, nothing special. | Neutral |
| Terrible quality and very disappointing. | Negative |

All three sample reviews were classified correctly.


## Installation and Usage

### 1. Clone the Repository

```
git clone https://github.com/Saidabou640/Datheon-machine-learning-internship.git
```

### 2. Navigate to Task 4

```
cd Datheon-machine-learning-internship/Task_4_Sentiment_Classification
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

### 4. Run the Notebook

Start Jupyter Notebook:

```
jupyter notebook
```

Open `notebooks/sentiment_classification.ipynb` and run the cells in order.

The notebook contains the complete workflow, including dataset preparation, text preprocessing, model training, evaluation, and sentiment prediction.
