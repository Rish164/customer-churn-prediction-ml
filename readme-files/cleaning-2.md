## 🧹 Data Cleaning Phase

### 🔹 Objective

Prepare the dataset for machine learning by handling inconsistencies, correcting data types, and removing irrelevant features.

---

### 🔹 Steps Performed

#### 1. Removed Irrelevant Column

* Dropped `customerID` as it is a unique identifier and does not contribute to prediction.

---

#### 2. Fixed Data Type Issue

* `TotalCharges` was incorrectly stored as an object (string).
* Converted it to numeric using:

  ```python
  pd.to_numeric(..., errors="coerce")
  ```
* Invalid or blank values were converted to `NaN`.

---

#### 3. Handled Missing Values

* Missing values were found in `TotalCharges`.
* Replaced missing values with the **median** of the column:

  ```python
  df["TotalCharges"] = df["TotalCharges"].fillna(df["TotalCharges"].median())
  ```

---

#### 4. Converted Target Variable

* Converted `Churn` from categorical (`Yes` / `No`) to numerical:

  * Yes → 1
  * No → 0

---

### 🔹 Final Dataset Status

* No missing values remain.
* `TotalCharges` is now in numeric format.
* `Churn` is converted to integer.
* Dataset is clean and ready for preprocessing.

---

### 🔹 Key Takeaways

* Data cleaning is essential to ensure model reliability.
* Handling incorrect data types and missing values improves data quality.
* Removing irrelevant features prevents noise in model training.
