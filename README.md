# ReviewInsight-NLP-based-Customer-Feedback-Analyzer

# Restaurant Review Sentiment Analysis

An NLP project that analyzes restaurant customer reviews to determine sentiment using both **classical machine learning** and **transformer-based deep learning models**. The goal is to compare traditional NLP pipelines with modern deep learning approaches and understand how different preprocessing strategies affect performance.

---

# Project Overview

Customer reviews contain valuable feedback that can help businesses understand customer satisfaction and identify areas for improvement. This project builds a sentiment classification system that predicts whether a restaurant review expresses **positive or negative sentiment**.

The project explores two main approaches:

1. Classical machine learning models using TF-IDF features  
2. Transformer-based models for contextual language understanding

Libraries used include:

- scikit-learn  
- NLTK  
- spaCy  
- PyTorch  
- BERT  
- DistilBERT  

---

# Dataset

The dataset consists of restaurant reviews derived from Yelp. Each record contains:

- restaurant URL  
- rating (1–5)  
- review date  
- review text  

Ratings were converted into sentiment labels:

| Rating | Sentiment |
|------|------|
| 4–5 | Positive |
| 1–2 | Negative |

This converts the problem into a **binary sentiment classification task**.

---

# Project Pipeline

The project follows a typical NLP workflow:
Data Exploration
↓
Text Preprocessing
↓
Feature Engineering
↓
Model Training
↓
Model Evaluation
↓
Model Comparison

---

# Exploratory Data Analysis (EDA)

Initial analysis was performed to understand the dataset characteristics:

- review length distribution  
- class balance between positive and negative reviews  
- common words appearing in reviews  

This step helps identify issues such as **class imbalance** and noisy text before building models.

---

# Text Preprocessing

Two different NLP preprocessing pipelines were implemented to evaluate their impact on model performance.

### NLTK Pipeline

Steps included:

- converting text to lowercase  
- removing punctuation  
- removing stopwords  
- stemming using Porter Stemmer  

Example transformation:

**Original**
The food was absolutely amazing!

**Processed**
food absolut amaz

---

### spaCy Pipeline

Steps included:

- tokenization  
- stopword removal  
- lemmatization  

Example transformation:

**Original**
The food was absolutely amazing!

**Processed**
food absolutely amazing


This allowed comparison between **stemming-based and lemmatization-based preprocessing**.

---

# Feature Engineering

Text data was converted into numerical representations using **TF-IDF vectorization**.

TF-IDF captures the importance of words within documents relative to the entire dataset.

N-grams were used to capture short phrases such as:
great food
bad service
highly recommend

---

# Classical Machine Learning Models

Two traditional classifiers were trained using TF-IDF features.

### Logistic Regression

A linear classification model widely used in text classification.

### Support Vector Machine (SVM)

A maximum-margin classifier that performs well in high-dimensional feature spaces.

Hyperparameters were optimized using **GridSearch with cross-validation**.

---

# Model Performance

Pipeline comparison results:

| Pipeline | Accuracy |
|------|------|
| NLTK + Logistic Regression | 0.952 |
| NLTK + SVM | 0.953 |
| spaCy + Logistic Regression | 0.950 |
| spaCy + SVM | 0.949 |

Classical models performed very well due to effective preprocessing and feature engineering.

---

# Transformer-Based Models

To compare classical approaches with modern deep learning methods, transformer models were fine-tuned for sentiment classification.

Models explored include:

- BERT  
- DistilBERT  

Transformers capture contextual relationships between words and can better understand complex sentence structures.

Example:

The food was good but the service was terrible.


Transformer models can capture the mixed sentiment within such sentences more effectively.

---

# Evaluation Metrics

Model performance was evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Confusion Matrix  

These metrics provide a comprehensive view of classification performance, especially in the presence of class imbalance.

---

# Key Insights

- Classical ML models achieved strong performance (~95% accuracy) with TF-IDF features.  
- Preprocessing strategies (NLTK vs spaCy) had a small but noticeable effect on performance.  
- Transformer models demonstrated the ability to capture contextual meaning in reviews.  
- Sentiment classification is highly effective for extracting insights from large volumes of customer feedback.

---

# Future Improvements

This project will be extended to build a more complete **restaurant feedback analytics platform**.

## Aspect-Based Sentiment Analysis

Instead of only predicting overall sentiment, the system will detect sentiment toward specific aspects such as:

| Aspect | Example |
|------|------|
| Food | taste, quality |
| Service | staff behavior, waiting time |
| Ambience | environment, seating |
| Price | value for money |

Example:
The food was amazing but the service was slow.

Output:
Food → Positive
Service → Negative


---

## Sentiment Trend Analysis

Sentiment will be tracked over time to detect patterns in customer feedback.

Example insights:

- improvement or decline in service quality  
- seasonal trends in customer satisfaction  
- recurring customer complaints  

---

## Interactive Dashboard

An interactive dashboard will be developed to help restaurant managers visualize feedback insights.

Potential features include:

- sentiment distribution  
- aspect-level sentiment breakdown  
- common complaint keywords  
- sentiment trends over time  

This will transform the project from a research notebook into a **practical decision-support system for businesses**.

---

# Conclusion

This project demonstrates the complete NLP workflow for sentiment analysis, from exploratory data analysis to model evaluation and comparison. The study highlights the strengths of both classical machine learning techniques and transformer-based models for analyzing large volumes of customer reviews.

Future work will extend this system into a full **restaurant feedback intelligence platform** capable of identifying actionable insights from customer reviews.


