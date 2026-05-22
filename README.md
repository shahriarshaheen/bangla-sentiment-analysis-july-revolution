# Bangla Sentiment Analysis on July Revolution Social Media Data

## Overview

This project presents a comparative analysis of classical machine learning and transformer-based models for Bangla sentiment analysis on social media comments collected during the July Revolution of 2024 in Bangladesh.

The study evaluates the effectiveness of traditional TF-IDF based approaches alongside fine-tuned transformer models on a low-resource Bangla NLP dataset. The project focuses on preprocessing strategies, feature engineering, transformer fine-tuning, and comparative evaluation across multiple models.

---

## Objectives

- Perform exploratory data analysis (EDA) on Bangla social media sentiment data
- Analyze platform-wise sentiment distribution and dataset characteristics
- Implement preprocessing pipelines for both classical ML and transformer models
- Compare TF-IDF based machine learning models with transformer-based approaches
- Evaluate model performance using Accuracy, Precision, Recall, and Macro F1-score
- Investigate the effectiveness of language-specific pretrained models for Bangla NLP

---

## Dataset

The project uses the **Student-People Mass Uprising Public Sentiments Dataset**, originally introduced by Hossen et al.

### Dataset Characteristics

- Total samples: 4,200
- Language: Bangla
- Platforms:
  - Facebook
  - YouTube
  - Twitter (X)
- Sentiment classes:
  - Positive
  - Negative
  - Neutral

After duplicate removal and preprocessing:

- Final dataset size: 4,083 samples

### Dataset Source

```text
https://doi.org/10.5281/zenodo.15342899
```

---

## Exploratory Data Analysis (EDA)

The EDA phase included:

- Label distribution analysis
- Platform-wise sentiment analysis
- Duplicate detection
- Text length analysis
- Word count and character count statistics
- Data quality verification
- Platform bias analysis

### Key Observations

- Initial dataset was balanced across sentiment classes
- Facebook contributed the highest number of comments
- Twitter showed highly skewed sentiment distribution
- Social media comments were short, noisy, and informal

---

## Preprocessing

Two separate preprocessing pipelines were implemented.

### Classical ML Preprocessing

Applied for TF-IDF based models:

- Unicode normalization
- Lowercasing
- Punctuation removal
- Stopword removal
- Extra whitespace cleanup

### Transformer Preprocessing

Applied for BanglaBERT, XLM-RoBERTa, and mBERT:

- Minimal cleaning
- Preservation of contextual structure
- Retained punctuation and sentence structure

Duplicate removal was performed before train-test splitting to prevent data leakage.

---

## Feature Engineering

### TF-IDF Features

- Character-level TF-IDF (`char_wb`)
- N-gram range: `(2,5)`
- Maximum features: `10,000`

Character n-grams were used to better capture Bangla morphological patterns and spelling variations common in social media text.

---

## Models Implemented

### Classical Machine Learning Models

- Logistic Regression
- Naive Bayes
- Random Forest

### Transformer Models

- BanglaBERT
- XLM-RoBERTa
- mBERT

Transformer models were fine-tuned for sequence classification using Hugging Face Transformers.

---

## Experimental Results

| Model               | Accuracy | Macro F1 |
| ------------------- | -------- | -------- |
| BanglaBERT          | 0.8704   | 0.8726   |
| mBERT               | 0.8484   | 0.8500   |
| XLM-RoBERTa         | 0.8460   | 0.8467   |
| Logistic Regression | 0.8433   | 0.8445   |
| Random Forest       | 0.8250   | 0.8261   |
| Naive Bayes         | 0.8115   | 0.8114   |

---

## Key Findings

- BanglaBERT achieved the best overall performance
- TF-IDF + Logistic Regression remained highly competitive
- Character-level TF-IDF worked effectively for Bangla social media text
- Neutral sentiment class achieved the highest classification accuracy
- Platform-specific sentiment imbalance may introduce bias

---

## Technologies Used

### Programming Language

- Python

### Libraries & Frameworks

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- transformers
- datasets
- torch
- evaluate
- accelerate

### Environment

- Google Colab (T4 GPU)

---

## Repository Structure

```text
bangla-sentiment-analysis-july-revolution/
│
├── notebooks/
│   └── bangla_sentiment_analysis_pipeline.ipynb
│
├── reports/
│   ├── final_report.pdf
│   └── literature_review.pdf
│
├── images/
│   ├── confusion_matrices/
│   ├── model_comparison/
│   └── eda_visualizations/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## How to Run

### Clone Repository

```bash
git clone <repository-link>
cd bangla-sentiment-analysis-july-revolution
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Notebook

Open:

```text
notebooks/bangla_sentiment_analysis_pipeline.ipynb
```

---

## Report

The repository also includes:

- Final IEEE-format project report
- Literature review document
- Experimental visualizations and confusion matrices

---

## Authors

- AL Shahriar Bin Shaheen
- Sushmita Alia
- Sanchary Roy

---

## Acknowledgment

This work was conducted as part of an academic machine learning and natural language processing project focused on Bangla sentiment analysis and transformer-based modeling.
