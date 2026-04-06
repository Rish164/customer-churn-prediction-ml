# 📊 Customer Churn Prediction using Machine Learning

## 🚀 Project Overview

This project aims to predict **customer churn** for a telecom company using machine learning models.
Churn prediction helps businesses identify customers likely to leave, enabling proactive retention strategies.

---

## 🎯 Objective

* Predict whether a customer will churn (Yes/No)
* Compare multiple machine learning models
* Identify the best-performing model based on evaluation metrics

---

## 📁 Dataset

* Source: IBM Telco Customer Churn Dataset
* Total Records: 7043
* Features: 21 (including target variable `Churn`)

---

## 🔍 Problem Type

* **Binary Classification**

  * 0 → No Churn
  * 1 → Churn

---

## ⚙️ Project Workflow

### 1. Data Understanding

* Identified feature types (categorical & numerical)
* Detected class imbalance
* Observed important features (tenure, charges, contract)

---

### 2. Data Cleaning

* Removed irrelevant column: `customerID`
* Converted `TotalCharges` to numeric
* Handled missing values using median
* Converted target variable (`Churn`) to numeric (0/1)

---

### 3. Data Preprocessing

* Applied **One-Hot Encoding** to categorical variables
* Used `drop_first=True` to avoid multicollinearity
* Applied **StandardScaler** for feature scaling
* Result: Fully numeric dataset (30 features)

---

### 4. Data Splitting

* Train: 70%
* Validation: 15%
* Test: 15%
* Used **stratified sampling** to maintain class distribution

---

## 🤖 Models Used

1. Logistic Regression
2. Random Forest
3. XGBoost

---

## 📊 Model Performance

| Metric    | Logistic Regression | Random Forest | XGBoost |
| --------- | ------------------- | ------------- | ------- |
| Accuracy  | **0.81**            | 0.79          | 0.79    |
| Precision | **0.69**            | 0.64          | 0.63    |
| Recall    | **0.53**            | 0.49          | 0.48    |
| F1 Score  | **0.60**            | 0.55          | 0.55    |
| ROC-AUC   | **0.84**            | 0.82          | 0.82    |

---

## 📈 Visual Analysis

* Confusion Matrix used to analyze prediction errors
* ROC Curve used to compare classification performance
* Bar Graph used for model comparison

---

## 🔍 Key Insights

* Logistic Regression outperformed all other models
* Complex models (Random Forest, XGBoost) did not improve performance
* Dataset patterns are effectively captured by linear relationships
* Recall is a critical metric for churn prediction

---

## 🚨 Challenges Faced

* Incorrect data type for `TotalCharges`
* Dataset imbalance affecting evaluation
* Explosion of features due to encoding (`customerID` issue)
* Confusion between encoding and scaling
* Loss of column names after scaling
* Managing workflow across multiple notebooks

---

## 🧠 Learnings

* Importance of proper data preprocessing
* Difference between encoding and scaling
* Why simpler models can outperform complex ones
* Role of evaluation metrics beyond accuracy
* Importance of stratified sampling in imbalanced datasets

---

## 🏁 Final Conclusion

> Logistic Regression is the best-performing model for this dataset.
> It achieves the highest accuracy, recall, and ROC-AUC score while remaining simple and interpretable.
> Increasing model complexity did not lead to better results, highlighting the importance of understanding data characteristics.

---

## 🔮 Future Improvements

* Threshold tuning to improve recall
* Handling class imbalance (SMOTE / class weights)
* Hyperparameter tuning
* Feature engineering
* Deployment as a web application

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* XGBoost

---

## 📌 Author

**Risheek Verma**

---
