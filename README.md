# Logistic Regression for Binary Classification

This project demonstrates how to build a **logistic regression model** for binary classification using a cleaned and preprocessed dataset. The workflow includes missing data handling, categorical encoding, standardization, model training, and evaluation using classification metrics and ROC curve.

---

## 📌 Objectives

- ✅ Load and preprocess the dataset.
- ✅ Train a logistic regression model using `scikit-learn`.
- ✅ Evaluate the model using **accuracy**, **precision**, **recall**, and **ROC curve**.

---

## Tools & Libraries

- Python 3.x  
- pandas   
- scikit-learn  
- matplotlib    
- Jupyter Notebook  

---

## Dataset

- **File**: `churn-bigml-80.csv`
- **Target Variable**: `Churn` (Yes/No)
- **Problem Type**: Binary Classification

---

## Steps Performed

### 🔹 1. Data Preprocessing
- Checked for **missing values** and **zero-value outliers**.
- Replaced:
  - Right-skewed column zeroes with **median**
  - Symmetric column zeroes with **mean**
- Engineered new feature: `Has vmail` from `Number vmail messages`
- Dropped unnecessary columns after transformation

### 🔹 2. Feature Encoding
- **Label Encoding**: `Churn`
- **Ordinal Encoding**: `International plan`, `Voice mail plan`
- **One-Hot Encoding**: `State`

### 🔹 3. Feature Scaling
- Applied **StandardScaler** for all numerical columns using a `ColumnTransformer`

### 🔹 4. Model Training
- Trained a **Logistic Regression** model using `class_weight='balanced'`
- Data split: **90% training**, **10% testing**

### 🔹 5. Model Evaluation
- Evaluated using:
  - Accuracy
  - Precision, Recall, F1-score
  - Confusion Matrix
  - ROC Curve & AUC

---

## Results

### Classification Report

| Class             | Precision | Recall | F1-Score | Support |
|-------------------|-----------|--------|----------|---------|
| **0 (Not Churn)** | 0.95      | 0.80   | 0.87     | 225     |
| **1 (Churn)**     | 0.42      | 0.76   | 0.54     | 42      |

### 📌 Overall Metrics

| Metric              | Value      |
|---------------------|------------|
| **Accuracy**        | 0.80       |
| **Macro Avg F1**    | 0.71       |
| **Weighted Avg F1** | 0.82       |
| **ROC AUC**         | Check Plot |

The model has high precision and F1 on the majority class, but recall is strong for the minority class (churn), which is important in real-world applications where missing churners is costly.

---

## ROC Curve

- The ROC curve was plotted using `matplotlib`
- The AUC score provides insight into the model's ability to separate churn vs. non-churn classes

---

## Author

**Debaswini**

---
