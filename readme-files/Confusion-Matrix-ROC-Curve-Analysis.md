## 📊 Confusion Matrix & ROC Curve Analysis

---

### 🔹 Confusion Matrix

Confusion matrices were plotted for all models to analyze prediction errors.

#### Key Observations:

* Logistic Regression produced the highest number of true positives
* It also had fewer false negatives compared to other models
* Random Forest and XGBoost missed more churn cases, leading to lower recall

---

### 🔹 ROC Curve

ROC curves were plotted to compare model performance across different thresholds.

#### Key Observations:

* All models performed better than random guessing
* Logistic Regression showed the best curve, indicating superior classification capability
* This aligns with its highest ROC-AUC score

---

### 🔹 Overall Insight

* Logistic Regression provides the best balance between detection and accuracy
* Ensemble models did not improve performance significantly
* The dataset favors simpler, linear models
