# 📊 Credit Risk – Probability of Default (PD) Modelling

## 🔎 Project Overview

This project builds a **Probability of Default (PD) model** to estimate borrower credit risk using the **Home Credit Default Risk** dataset.

The goal is to compare interpretable and performance-driven models and translate model outputs into business-friendly risk decisions.

---

## 📁 Dataset

* Source: Home Credit Default Risk (Kaggle)
* Total records: ~307K loan applications
* Working sample: 70,000 observations
* Target variable:

  * `TARGET = 1` → Default
  * `TARGET = 0` → Non-default

---

## ⚙️ Modelling Workflow

### 1️⃣ Data Preparation

* Loaded loan-level retail credit data
* Selected numeric features for modelling
* Missing value handling using median imputation
* Addressed class imbalance using class-weighted models

### 2️⃣ Models Built

#### Logistic Regression (Interpretability Model)

* Baseline credit risk model
* Used for transparent and explainable risk assessment

#### Random Forest (Performance Model)

* Captures non-linear relationships
* Used for stronger predictive ranking power

---

### 3️⃣ Model Evaluation

* ROC-AUC used as primary metric due to imbalanced classes
* Confusion matrix used for threshold analysis
* Model comparison focused on ranking quality rather than accuracy

---

### 4️⃣ Threshold Optimization

* Probability threshold adjusted to **0.30**
* Increased default detection while controlling false approvals
* Demonstrates risk appetite trade-off used in credit strategy

---

## 📈 Results

| Model               | ROC-AUC |
| ------------------- | ------- |
| Logistic Regression | ~0.61   |
| Random Forest       | ~0.69   |

**Key Insight:**
Random Forest achieved stronger ranking power and better separation of high-risk borrowers.

---

## 🔑 Top Predictive Features

* EXT_SOURCE_2
* EXT_SOURCE_3
* DAYS_BIRTH
* DAYS_EMPLOYED
* DAYS_LAST_PHONE_CHANGE
* DAYS_REGISTRATION
* DAYS_ID_PUBLISH

These variables were identified as strong drivers of borrower default risk.

---

## 🏦 Risk Bucket Segmentation

Predicted probabilities were converted into business-friendly risk bands:

* **Low Risk (PD < 10%)**
* **Medium Risk (10% – 30%)**
* **High Risk (PD > 30%)**

Observed default rates increased consistently across buckets, demonstrating strong ranking capability of the model and enabling portfolio-level monitoring.

---

## 📊 Visualizations

### ROC Curve

![ROC Curve](images/roc_curve.png)

### Feature Importance

![Feature Importance](images/feature_importance.png)

### Risk Bucket Analysis

![Risk Buckets](images/risk_buckets.png)

---

## 💼 Business Interpretation

* Logistic Regression supports explainability for regulatory and business stakeholders.
* Random Forest improves predictive performance for borrower ranking.
* Risk buckets translate model outputs into underwriting decisions.
* Lower thresholds improve default capture but increase approval risk, highlighting the balance between growth and risk control.

---

## 🛠 Tools & Libraries

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib

---

## 🚀 Key Learning Outcomes

* End-to-end credit risk modelling workflow
* Handling imbalanced datasets
* Model comparison using ROC-AUC
* Threshold tuning aligned with risk appetite
* Feature importance interpretation
* Risk segmentation for portfolio monitoring
