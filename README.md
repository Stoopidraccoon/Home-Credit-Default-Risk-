# Loan Default Risk Prediction with Business Cost Optimization

This project focuses on predicting loan default risk using the **Home Credit Default Risk** dataset (`application_train.csv`).  
The goal is not just to maximize accuracy, but also to **minimize business costs** from false predictions.


## Dataset

- **File Used:** `application_train.csv`
- **Records:** ~307,511 loan applications
- **Features:** 122+
- **Target Variable:**  
  - `0` → Loan repaid  
  - `1` → Loan default  

### Example Features
- **Demographics:** Gender, Age, Education, Family status  
- **Financials:** Income, Employment type, Credit amount  
- **Housing & Social:** Housing type, Region, Occupation  
- **Credit Behavior:** Previous loan approvals, Payment difficulties  

##  Methods Used

- **Exploratory Data Analysis (EDA)**
- **Handling Missing Data**
  - Numeric → median imputation
  - Categorical → `MISSING` category
- **Models Applied**
  - Logistic Regression
  - CatBoost Classifier
  - XGBoost Classifier
- **Business Cost Optimization**
  - Threshold tuning with different costs for False Positives (FP) vs False Negatives (FN)


## Results

--- Logistic Regression ---
AUC: 73.77576318035366
Accuracy: 68.44381574882526
Classification Report:               precision    recall  f1-score   support

           0       0.96      0.69      0.80     56538
           1       0.16      0.67      0.25      4965

    accuracy                           0.68     61503
   macro avg       0.56      0.68      0.53     61503
weighted avg       0.89      0.68      0.76     61503

--- CatBoost ---
AUC: 76.29350623988351
Accuracy: 91.96461961205145
              precision    recall  f1-score   support

           0       0.92      1.00      0.96     56538
           1       0.56      0.02      0.04      4965

    accuracy                           0.92     61503
   macro avg       0.74      0.51      0.50     61503
weighted avg       0.89      0.92      0.88     61503

--- XGBoost ---
AUC: 75.70493507614962
Accuracy: 72.73303741280913
              precision    recall  f1-score   support

           0       0.96      0.73      0.83     56538
           1       0.18      0.65      0.28      4965

    accuracy                           0.73     61503
   macro avg       0.57      0.69      0.55     61503
weighted avg       0.90      0.73      0.79     61503



Best threshold: 0.73, Business cost: 49620.00
Accuracy at best threshold: 0.9193210087312814
[[56538     0]
 [ 4962     3]]


## Visualizations

- Feature Importance (CatBoost,Logistic Regression XGBoost)  
- ROC Curves  
- Precision-Recall Curves  
- Business Cost vs Threshold Analysis  
