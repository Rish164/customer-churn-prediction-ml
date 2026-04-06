## 🌳 Model 2: Random Forest

### 🎯 Objective

Apply an ensemble-based machine learning model to improve prediction performance and capture complex patterns in customer churn data.

---

## 🔹 Overview

Random Forest is an **ensemble learning algorithm** that builds multiple decision trees and combines their predictions using majority voting.

* Reduces overfitting compared to a single decision tree
* Handles non-linear relationships
* Works well with mixed feature types

---

## ⚙️ Implementation

```python
from sklearn.ensemble import RandomForestClassifier

rf_model = RandomForestClassifier(n_estimators=100, random_state=42)

rf_model.fit(X_train, y_train)

y_pred_rf = rf_model.predict(X_test)
y_prob_rf = rf_model.predict_proba(X_test)[:, 1]
```

---

## 📊 Performance Metrics

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.79  |
| Precision | 0.64  |
| Recall    | 0.49  |
| F1 Score  | 0.55  |
| ROC-AUC   | 0.82  |

---

## 🔍 Observations

* Slightly lower accuracy compared to Logistic Regression
* Lower precision → more false positives
* Lower recall → missed more churn customers
* Slightly weaker ROC-AUC score

---

## 🚨 Key Insight

> Despite being a more complex model, Random Forest did not outperform Logistic Regression on this dataset.

---

## 🧠 Interpretation

* The dataset may not require complex non-linear modeling
* Random Forest may need hyperparameter tuning for better performance
* Default settings are not sufficient for optimal results

---

## ⚠️ Limitation

* Higher model complexity without performance gain
* Lower recall is problematic for churn prediction

---

## 🚀 Conclusion

Random Forest did not provide performance improvements over the baseline model. This highlights the importance of model selection based on data characteristics rather than model complexity.
