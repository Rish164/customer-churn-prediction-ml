## 🚀 Model 3: XGBoost (Extreme Gradient Boosting)

### 🎯 Objective

Apply an advanced boosting algorithm to improve prediction performance by learning from previous errors and capturing complex patterns in the data.

---

## 🔹 Overview

XGBoost is an **ensemble learning algorithm** based on boosting, where models are built sequentially and each new model focuses on correcting the errors of the previous ones.

* Handles complex, non-linear relationships
* Focuses on difficult-to-predict cases
* Highly efficient and widely used in real-world problems

---

## ⚙️ Implementation

```python
from xgboost import XGBClassifier

xgb_model = XGBClassifier(
    n_estimators=100,
    learning_rate=0.1,
    random_state=42,
    use_label_encoder=False,
    eval_metric='logloss'
)

xgb_model.fit(X_train, y_train)

y_pred_xgb = xgb_model.predict(X_test)
y_prob_xgb = xgb_model.predict_proba(X_test)[:, 1]
```

---

## 📊 Performance Metrics

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.79  |
| Precision | 0.63  |
| Recall    | 0.48  |
| F1 Score  | 0.55  |
| ROC-AUC   | 0.82  |

---

## 🔍 Observations

* Performance is similar to Random Forest but slightly lower
* Lower recall compared to Logistic Regression
* Misses a higher number of churn customers
* No improvement despite increased model complexity

---

## 🚨 Key Insight

> XGBoost did not outperform Logistic Regression, indicating that boosting-based complexity does not provide additional benefits for this dataset.

---

## 🧠 Interpretation

* Dataset may not require complex ensemble techniques
* Linear relationships dominate the data
* Default hyperparameters may not be optimal

---

## ⚠️ Limitations

* Lower recall is critical for churn prediction
* Increased complexity without performance gain
* Requires hyperparameter tuning for better results

---

## 🚀 Conclusion

XGBoost, despite being a powerful algorithm, did not improve performance in this case. This highlights that model effectiveness depends on data characteristics, and simpler models can outperform advanced techniques when patterns are relatively linear.
