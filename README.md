# High-Risk-Patients---Predictions
## 🏥 Healthcare Readmission Prediction — SQL + Python + Power BI
## 📘 Project Overview

This project predicts patient readmission within 30 days of discharge using hospital data.
Hospitals lose revenue and face penalties when patients are frequently readmitted.
The goal is to identify high-risk patients early so care teams can intervene — reducing costs and improving patient outcomes.

## 🎯 Business Problem

Hospitals need to know which patients are likely to be readmitted soon after discharge.
Manual monitoring is slow and inconsistent, leading to higher costs and lower quality of care.

### Business Goal:

Predict 30-day readmissions using patient, clinical, and hospitalization data.

Identify key factors driving readmission.

Enable proactive patient management and better discharge planning.

## 🧩 Dataset

Dataset Source: Kaggle (Healthcare Readmission Prediction, 2024–2025 version).
Rows: ~30,000
Key Columns:

Column	Description
patient_id	Unique identifier
age	Patient’s age
gender	Male/Female/Other
blood_pressure	Recorded as systolic/diastolic
cholesterol	Serum cholesterol level
bmi	Body Mass Index
diabetes, hypertension	Chronic conditions
medication_count	Total medications prescribed
length_of_stay	Days admitted
discharge_destination	Home / Nursing Facility
readmitted_30_days	Target variable (Yes/No)
## 🧠 Steps & Methodology
### 1. Data Cleaning & Transformation

~ Split blood_pressure into systolic_bp and diastolic_bp.

~ Handled missing values and encoded categorical variables.

~ Removed insignificant features (gender, cholesterol, medication_count).

### 2. Exploratory Data Analysis (EDA)

Analyzed readmission distribution across age, BMI, stay length, and discharge type.

Found higher readmission in older patients and those discharged to nursing facilities.

### 3. Hypothesis Testing

Chi-Square Tests: Checked categorical relationships (e.g., diabetes vs readmission).

T-Tests: Compared means of continuous variables (BMI, stay length).

Key significant factors: diabetes, hypertension, bmi, discharge_destination.

## 4. Modeling

## Built multiple models:

Model	Technique	AUC	Recall (1)	Comment
Logistic Regression	Baseline	0.58	0.00	Poor minority recall
XGBoost + SMOTE	Boosted Trees	0.50	Moderate	Overfitting / unstable
Random Forest + SMOTE	Ensemble	0.52	Improved	Best balance & interpretability
## 5. Feature Importance
Rank	Feature	Importance
1	BMI	0.48
2	Age	0.35
3	Length of Stay	0.10
4	Discharge Destination	0.02
5	Diabetes / Hypertension	0.02
6. Export & Visualization (Power BI)

Exported predictions (patient_id, predicted_prob, predicted_label).

Built Power BI Dashboard with:

KPI cards (Accuracy, Recall, AUC)

Readmission probability distribution

Feature importance chart

High-risk patient table

## 📊 Key Insights

High BMI and older age strongly increase readmission probability.

Patients discharged to nursing facilities are most at risk.

Chronic conditions like diabetes and hypertension raise risk modestly.

Predictive modeling helps target at-risk patients before they are readmitted.

## 🧾 Tools & Technologies

Languages: Python (Pandas, NumPy, Scikit-learn, Imbalanced-learn, Matplotlib, Seaborn)
ML Techniques: Logistic Regression, Random Forest, XGBoost, SMOTE
Visualization: Power BI
Data Source: SQL / Kaggle

## 🚀 Impact

Enables hospital staff to proactively monitor high-risk patients.

Reduces preventable readmissions → cost savings + better care outcomes.

Supports data-driven decision-making and resource optimization.
