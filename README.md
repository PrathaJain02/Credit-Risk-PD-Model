# 📊 Credit Risk – Probability of Default (PD) Modelling

## 🔎 Project Overview

This project builds a **Probability of Default (PD) model** to estimate borrower credit risk using the **Home Credit Default Risk** dataset.

The objective is to compare interpretable and performance-driven models to support credit decision-making and risk monitoring.

---

## 📁 Dataset

* Source: Home Credit Default Risk (Kaggle)
* Total records: ~307K loans (sampled to 70K for modelling)
* Target variable:

  * `TARGET = 1` → Default
  * `TARGET = 0` → Non-default

---

## ⚙️ Modelling Workflow

### 1️⃣ Data Preparation

* Loaded retail loan-level data
* Selected numeric features
* Handled missing values using median imputation
* Addressed class imbalance using class weights

### 2️⃣ Models Built

* **Logistic Regression**

  * Used for interpretability
  * Baseline credit risk model

* **Random Forest**

  * Used for predictive performance
  * Captures non-linear relationships

### 3️⃣ Evaluation Metric

* ROC-AUC used due to imbalanced default distribution
* Confusion matrix used for threshold analysis

### 4️⃣ Threshold Optimization

* Probability threshold adjusted to **0.30**
* Improved default capture while controlling false approvals
* Demonstrates alignment with risk appetite

---

## 📈 Results

| Model               | ROC-AUC |
| ------------------- | ------- |
| Logistic Regression | ~0.61   |
| Random Forest       | ~0.69   |

**Key Insight:**
Random Forest achieved stronger ranking power, making it more effective for identifying high-risk borrowers.

---

## 🔑 Top Predictive Features

* EXT_SOURCE_2
* EXT_SOURCE_3
* DAYS_BIRTH
* DAYS_EMPLOYED
* DAYS_LAST_PHONE_CHANGE

These variables significantly influence borrower default risk.

---

## 📊 Visualizations

### ROC Curve

![ROC Curve](images/roc_curve.png)

### Feature Importance

![Feature Importance](images/feature_importance.png)

---

## 💼 Business Interpretation

* Logistic Regression provides interpretability for regulatory explanation.
* Random Forest improves prediction strength for risk ranking.
* Lower probability thresholds increase default detection but may raise false approvals, illustrating the trade-off between risk control and portfolio growth.

---

## 🛠 Tools & Libraries

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib

---

## 🚀 Key Learning Outcomes

* Credit risk modelling workflow
* Handling imbalanced datasets
* Model comparison using ROC-AUC
* Threshold tuning aligned with risk appetite
* Feature importance analysis

---
