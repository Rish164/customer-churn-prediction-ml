## ⚙️ Data Preprocessing

### 🎯 Objective

Transform raw customer data into a machine learning–ready format by handling categorical variables, scaling numerical features, and ensuring data consistency.

---

## 🔹 Steps Performed

### 1. Feature & Target Separation

* Split dataset into:

  * **x (features)** → Input variables
  * **y (target)** → `Churn`

---

### 2. Encoding Categorical Variables

* Applied **One-Hot Encoding** using:

  ```python
  pd.get_dummies(x, drop_first=True)
  ```
* Converted categorical features into binary (0/1) columns.
* Used `drop_first=True` to avoid **multicollinearity**.

#### 📌 Outcome:

* Dataset expanded from **20 columns → 30 columns**
* All features became numeric

---

### 3. Feature Scaling

* Applied **StandardScaler**:

  ```python
  scaler.fit_transform(x)
  ```
* Standardized features to ensure equal contribution during model training.

#### 📌 Reason:

* Features had different ranges (e.g., tenure vs charges)
* Prevents bias toward larger values

---

## ⚠️ Challenges Faced & Solutions

### 🔸 Issue 1: Exploding Number of Columns (13,000+)

* Cause: `customerID` was not removed before encoding
* Effect: One-hot encoding created a column for each unique ID

#### ✅ Solution:

* Removed `customerID` before encoding

---

### 🔸 Issue 2: Boolean Representation Instead of 0/1

* Observation: Encoded values appeared as `True/False`

#### ✅ Explanation:

* Boolean values are internally treated as **1/0**
* No additional conversion required

---

### 🔸 Issue 3: Data Type Confusion During Scaling

* Confusion: Whether scaling converts categorical data

#### ✅ Clarification:

* Encoding converts categories → numbers
* Scaling only standardizes numeric values

---

### 🔸 Issue 4: Loss of Column Names After Scaling

* Cause: `StandardScaler` returns a NumPy array

#### ✅ Solution:

```python
x_scaled = pd.DataFrame(x_scaled, columns=x.columns)
```

* Restored column names for better interpretability

## 🔹 Final Output

* Fully numeric dataset
* No missing values
* Properly encoded categorical variables
* Scaled features
* Ready for model training

---

## 🧠 Key Learnings

* Importance of removing unique identifiers before encoding
* Difference between encoding and scaling
* Handling data type transformations carefully
* Maintaining clean and reproducible data pipelines

---

## 🚀 Next Step

Proceed to:

* Data Splitting (Train / Validation / Test)
* Model Training & Evaluation
