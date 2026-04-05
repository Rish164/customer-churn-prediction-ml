## 📊 Initial Data Understanding

### 🔹 Dataset Overview

* The dataset contains **7043 rows and 21 columns**.
* It represents customer data from a telecom company.
* The goal is to predict whether a customer will churn.

---

### 🔹 Target Variable

* Column: **Churn**
* Data Type: Object (categorical)
* Values:

  * **No** → 5174
  * **Yes** → 1869

#### 📌 Observation:

* The dataset is **imbalanced**, with significantly more non-churn customers than churn customers.

---

### 🔹 Feature Types

* **Categorical Features:** Majority of the dataset (e.g., gender, contract, payment method)
* **Numerical Features:**

  * `tenure`
  * `MonthlyCharges`
  * `TotalCharges` (currently incorrect type)

#### 📌 Observation:

* The dataset is dominated by **categorical variables**, requiring encoding during preprocessing.

---

### 🔹 Data Issues Identified

#### 1. Incorrect Data Type

* `TotalCharges` is stored as an **object (string)** instead of numeric.
* Likely due to missing or blank values.

#### 2. Irrelevant Column

* `customerID` is a unique identifier and does not contribute to prediction.
* This column should be removed.

---

### 🔹 Initial Feature Intuition

Based on domain understanding, the following features are expected to significantly influence churn:

* `tenure` (customer duration)
* `Contract` (type of subscription)
* `MonthlyCharges`
* `TotalCharges`

However, other features such as services and customer demographics may also impact churn and will be evaluated during model training.

---

### 🔹 Key Takeaways

* Dataset is **imbalanced**, requiring careful evaluation metrics.
* Contains a mix of categorical and numerical data.
* Requires data cleaning before modeling.
* Feature importance will be validated using machine learning models rather than assumptions.
