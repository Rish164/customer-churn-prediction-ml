## 🤖 Logistic Regression: Intuition and Implementation

---

## 🔹 What is Logistic Regression?

Logistic Regression is a **supervised machine learning algorithm** used for **binary classification**, where the output has two possible values:

* 0 → No Churn
* 1 → Churn

---

## 🔹 Core Idea

Instead of directly predicting a class, Logistic Regression predicts:

> **The probability that a customer will churn**

---

## 🔹 How It Works (Intuition)

The model:

1. Takes input features (e.g., tenure, monthly charges)
2. Assigns importance (weights) to each feature
3. Combines them into a single score
4. Converts that score into a probability between 0 and 1

---

## 🔹 Decision Making

* If probability ≥ 0.5 → Predict Churn
* If probability < 0.5 → Predict No Churn

👉 This threshold can be adjusted depending on business needs.

---

## 🔹 Why Logistic Regression?

* Simple and fast
* Easy to interpret
* Works well as a baseline model
* Outputs probabilities (useful for decision-making)

---

## ⚙️ Implementation in This Project

---

### 🔸 Model Initialization

```python id="f8j7py"
from sklearn.linear_model import LogisticRegression

model = LogisticRegression(max_iter=1000)
```

---

### 🔸 Model Training

```python id="1y2c2m"
model.fit(X_train, y_train)
```

👉 The model learns patterns from training data.

---

### 🔸 Predictions

#### Class Predictions:

```python id="tfz3q9"
y_pred = model.predict(X_test)
```

#### Probability Predictions:

```python id="1n8qzv"
y_prob = model.predict_proba(X_test)[:, 1]
```

👉 `predict()` → final decision (0 or 1)
👉 `predict_proba()` → probability of churn

---

## 📊 Example Output

```id="u8y8hs"
Predicted labels: [0 0 0 0 0 0 0 0 0 1]
Predicted probabilities: [0.42, 0.09, ..., 0.73]
```

---

## 📊 Model Evaluation

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.81  |
| Precision | 0.69  |
| Recall    | 0.53  |
| F1 Score  | 0.60  |
| ROC-AUC   | 0.84  |

---

## 🔹 Interpretation

### ✅ Accuracy (0.81)

* Good overall performance
* But misleading due to class imbalance

---

### ⚠️ Precision (0.69)

* When the model predicts churn, it is correct ~69% of the time

---

### 🚨 Recall (0.53)

* Only 53% of actual churn cases are detected
* Many churn customers are missed

---

### ⚖️ F1 Score (0.60)

* Moderate balance between precision and recall

---

### 🔥 ROC-AUC (0.84)

* Strong ability to distinguish between churn and non-churn

---

## 🔹 Confusion Matrix

|            | Predicted No | Predicted Yes |
| ---------- | ------------ | ------------- |
| Actual No  | 708 (TN)     | 68 (FP)       |
| Actual Yes | 132 (FN)     | 149 (TP)      |

---

## 🔍 Key Observations

* High True Negatives → model is good at identifying non-churn customers
* Moderate True Positives → some churn detected
* High False Negatives → many churn cases missed ❗

---

## 🚨 Business Impact

* **False Negatives (132)**:

  * Customers who churned but were not identified
  * Leads to revenue loss

---

## 📈 ROC Curve

* Curve bends toward the top-left
* Indicates strong classification performance

---

## 🔹 Key Insight

> The model performs well overall but is conservative in predicting churn, leading to missed churn cases.

---

## 🔹 Threshold Limitation

* Default threshold = 0.5
* Leads to lower recall

---

## 🔹 Improvement Strategy

Lowering threshold:

```python id="qvbn8n"
y_pred_03 = (y_prob >= 0.3).astype(int)
```

👉 Results in:

* Higher recall (detect more churn)
* Lower precision (more false alarms)

---

## 🧠 Key Learnings

* Logistic Regression predicts probabilities, not just classes
* Encoding and scaling are essential preprocessing steps
* Accuracy alone is not reliable for imbalanced data
* Recall is critical in churn prediction problems
* Threshold tuning can improve business outcomes

---

## 🚀 Conclusion

Logistic Regression provides a strong baseline model with good classification ability. However, its lower recall indicates that many churn cases are not being detected, suggesting the need for more advanced models or threshold optimization.

