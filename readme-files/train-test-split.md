## 🔀 Data Splitting

### 🎯 Objective

Divide the dataset into separate subsets for training, validation, and testing to ensure unbiased model evaluation and proper generalization.

---

## 🔹 Splitting Strategy

The dataset was divided into three parts:

* **Training Set (70%)** → Used to train the model
* **Validation Set (15%)** → Used for tuning and model selection
* **Test Set (15%)** → Used for final performance evaluation

---

## 🔹 Implementation

Since Scikit-learn does not directly support a 70/15/15 split, a two-step approach was used:

### Step 1: Split into Training and Temporary Set

```python
X_train, X_temp, y_train, y_temp = train_test_split(
    X, y,
    test_size=0.3,
    random_state=42,
    stratify=y
)
```

---

### Step 2: Split Temporary Set into Validation and Test Sets

```python
X_val, X_test, y_val, y_test = train_test_split(
    X_temp, y_temp,
    test_size=0.5,
    random_state=42,
    stratify=y_temp
)
```

---

## 🔹 Final Split Sizes

| Dataset    | Samples |
| ---------- | ------- |
| Training   | 4930    |
| Validation | 1056    |
| Test       | 1057    |

---

## 🔹 Handling Class Imbalance

The dataset is imbalanced (more non-churn than churn cases).
To address this, **stratified splitting** was used:

```python
stratify=y
```

### 📌 Purpose:

* Maintains the same proportion of churn vs non-churn across all datasets
* Ensures fair training and evaluation

---

## ⚠️ Challenges Faced & Solutions

### 🔸 Issue 1: Target Variable Shape

* Problem: Target variable (`y`) was loaded as a DataFrame instead of a Series
* Effect: Potential shape mismatch during model training

#### ✅ Solution:

```python
y = pd.read_csv(...).squeeze()
```

* Converted target to 1D structure as required by ML models

---

### 🔸 Issue 2: Multi-Notebook Workflow

* Problem: Data preprocessing and splitting were done in separate notebooks
* Effect: Loss of transformations between steps

#### ✅ Solution:

* Saved processed datasets:

  * `preprocessed_churn.csv`
  * `target.csv`
* Reloaded them in the splitting notebook

---

### 🔸 Issue 3: Risk of Distribution Shift

* Problem: Random splitting could distort class distribution
* Effect: Biased model evaluation

#### ✅ Solution:

* Applied stratified sampling to preserve original distribution

---

## 🔹 Key Takeaways

* Proper data splitting is critical for reliable model evaluation
* Stratification is essential when dealing with imbalanced datasets
* Maintaining a clean and reproducible pipeline improves project robustness

---

## 🚀 Next Step

Proceed to:

* Model Training (Logistic Regression, Random Forest, XGBoost)
* Performance Evaluation and Comparison
