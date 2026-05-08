# Loan Prediction using Machine Learning

🚀 Overview

This project predicts whether a loan application will be approved or not based on applicant details such as income, credit history, employment status, and other factors.

The solution uses ensemble machine learning models combined with feature engineering to achieve strong predictive performance.

🎯 Problem Statement

Given applicant data, predict the loan approval status:

Y → Loan Approved
N → Loan Rejected

🧠 Approach

1. Data Preprocessing
   Removed unnecessary columns (e.g., Loan_ID)
   Handled missing values:
   Numerical → median
   Categorical → mode
   Converted target variable:
   Y → 1
   N → 0

2. Feature Engineering

Created new meaningful features:

Total_Income = Applicant + Coapplicant income
Log_Income (log transformation)
Log_LoanAmount (log transformation)
EMI (loan burden estimate)
Balance_Income (remaining income after EMI)
Income_per_Loan (income-to-loan ratio)

3. Encoding
   Label encoding for categorical variables:
   Gender, Married, Education, Self_Employed, Property_Area

4. Models Used
   HistGradientBoostingClassifier
   RandomForestClassifier
   VotingClassifier (Ensemble)

The final prediction is based on a weighted soft voting ensemble.

5. Evaluation
   Used Stratified K-Fold Cross Validation (k=5)
   Metric: Accuracy
   📈 Results
   Model Accuracy
   Gradient Boosting ~0.80
   Random Forest ~0.80
   Ensemble Model ~0.81
