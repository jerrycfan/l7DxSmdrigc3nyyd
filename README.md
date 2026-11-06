# Customer Happiness Prediction

**Machine Learning Classification | Apziva AI Residency Project 1**

## Project Overview

This project aims to predict customer happiness based on survey responses and identify which questions are most useful for prediction.

The project target is to achieve at least 73% classification accuracy while exploring whether fewer survey questions can maintain or improve prediction performance.

## Dataset Description

The dataset contains 126 customer responses, six survey features (X1–X6), and one binary target variable (Y).

**Target Variable:**

- **Y:** Customer happiness (0 = Unhappy, 1 = Happy)

**Survey Features:**

| Feature | Description |
|---|---|
| X1 | My order was delivered on time |
| X2 | The contents of my order were as I expected |
| X3 | I ordered everything I wanted to order |
| X4 | I paid a good price for my order |
| X5 | I am satisfied with my courier |
| X6 | The app makes ordering easy for me |

Each feature is rated on a scale of 1 to 5, where higher values indicate more positive responses.

## Methodology

- Exploratory Data Analysis
- Seven Classification Models (Logistic Regression, Decision Tree, Random Forest, SVM, Gradient Boosting, KNN, Naive Bayes)
- Repeated Stratified 5-Fold Cross-Validation
- Feature Selection using ANOVA and Exhaustive Search
- Hyperparameter Tuning using Grid Search
- Model Stability Analysis across 10,000 Random Seeds

## Key Findings

**Feature Selection:** X1 (on-time delivery), X3 (ordering everything wanted), and X6 (ease of ordering through the app) were the best-performing feature combination across several models. These findings suggest that the survey could potentially be reduced from six questions to three.

### Model Performance Progression

| Stage | Best Model | Validation Accuracy |
|---|---|---|
| Initial Model Evaluation | Gradient Boosting | 59.85% |
| After Feature Selection | Decision Tree | 70.79% |
| After Hyperparameter Tuning | KNN | 71.61% |

These results were obtained using Repeated Stratified 5-Fold Cross-Validation with a fixed random seed (random_state=1). They represent the best results at each stage, rather than performance on an independent test set.

### Model Stability Analysis

The best-performing KNN configuration was evaluated across 10,000 random seeds, each using Repeated Stratified 5-Fold Cross-Validation.

| Metric | Result |
|---|---|
| Highest Accuracy (Seed 3861) | 74.47% |
| Average Accuracy | 69.75% |
| Lowest Accuracy | 64.49% |
| Standard Deviation | 1.29 percentage points |

Although the highest observed accuracy exceeded the 73% target, it was selected from 10,000 random seeds and does not represent expected performance on unseen data. The average accuracy remained below the target.

Further evaluation using more data and an independent test set is needed to confirm these findings.

## Project Files

- `happy_customers.ipynb` — Complete analysis, model training, evaluation, and conclusions.
- `requirements.txt` — Required Python packages.
- `data/` — Original customer survey dataset in CSV format.
