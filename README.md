# Telecom Customer Churn Analysis and Prediction

## Overview

Customer churn is a major challenge for subscription-based businesses because losing customers reduces recurring revenue and increases the cost of acquiring replacements.

This project analyzes customer demographics, services, account information, and billing behavior to identify factors associated with customer churn and develop machine learning models for predicting customers at risk of leaving.

The project follows an end-to-end data science workflow covering data cleaning, exploratory data analysis, feature engineering, predictive modeling, model evaluation, and data visualization.

## Business Question

> What factors drive customer churn, and can we predict which customers are likely to leave next?

## Objectives

- Analyze customer behavior and churn patterns
- Clean and preprocess telecom customer data
- Identify key factors associated with churn
- Engineer features for analysis and modeling
- Build and compare classification models
- Evaluate model performance using multiple metrics
- Communicate findings through visualizations and a Tableau dashboard
- Translate analytical findings into actionable retention strategies

## Dataset

The project uses the IBM Telco Customer Churn dataset, containing:

- 7,043 customers
- 21 features
- Customer demographic information
- Services and subscription details
- Contract information
- Payment methods
- Monthly and total charges
- Customer churn status

## Data Preparation

The dataset was inspected and cleaned before analysis and modeling.

Key preprocessing steps included:

- Checking for missing values
- Converting `TotalCharges` from string to numeric
- Handling 11 blank `TotalCharges` values associated with customers with zero tenure
- Converting `SeniorCitizen` from binary values to readable labels
- Checking for duplicate records
- Removing the `customerID` identifier
- Encoding the churn target as a binary variable
- Checking numerical variables for potential outliers
- Creating a `tenure_group` feature for analysis and visualization

The numerical variables did not show extreme outliers requiring removal.

## Exploratory Data Analysis

The exploratory analysis examined churn patterns across customer characteristics, services, contracts, tenure, and payment behavior.

### Key Findings

- Month-to-month customers had substantially higher churn than customers on one-year or two-year contracts.
- Customers within their first 12 months showed the highest churn levels.
- Customers with longer tenure were considerably more stable.
- Electronic Check customers had the highest churn rate, at approximately 45%.
- Customers using automatic bank transfer or credit card payment methods had considerably lower churn rates.
- Contract type, tenure, internet service, and payment method emerged as important factors associated with churn.

The analysis produced multiple visualizations to investigate these relationships and identify patterns relevant to customer retention.

## Machine Learning

Two classification models were developed and compared:

### Logistic Regression

Logistic Regression was used as an interpretable baseline classification model.

### Random Forest

Random Forest was selected as a more flexible ensemble model capable of capturing nonlinear relationships and interactions between features.

## Model Preprocessing

Before modeling:

- Categorical variables were encoded
- Class imbalance was addressed using SMOTE
- Data was split into training and test sets using an 80/20 split
- Stratification was used during the train/test split
- Numerical features were standardized using `StandardScaler`

## Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion matrix
- ROC curve
- Five-fold stratified cross-validation

Random Forest performed better than Logistic Regression on the evaluated metrics and was selected as the preferred model for churn prediction.

The evaluation process was designed to assess not only overall accuracy but also the model's ability to distinguish between customers who churn and those who remain.

## Feature Importance

Random Forest feature importance was used to identify variables that contributed most to the model's predictions.

This helped connect the predictive modeling stage back to the exploratory analysis and identify factors that could be considered when designing customer retention strategies.

## Tableau Dashboard

A Tableau dashboard was created to communicate the analysis in an accessible format.

The dashboard allows stakeholders to explore customer churn patterns and examine relationships between churn and customer characteristics.

The cleaned dataset was also exported specifically for Tableau visualization.

## Business Recommendations

Based on the analysis, potential retention strategies include:

- Developing targeted retention programs for month-to-month customers
- Prioritizing new customers during their first year
- Encouraging customers to move toward longer-term contracts
- Investigating the high churn observed among Electronic Check users
- Using predictive modeling to identify customers who may be at higher risk of churn

## Project Structure

```
telecom-churn/
│
├── dashboard/
│   └── Tableau dashboard files
│
├── data/
│   └── Project datasets and processed data
│
├── notebooks/
│   └── Telecom churn analysis notebook
│
├── reports/
│   └── Detailed analysis reports and supporting outputs
│
└── README.md
```

## Tools and Technologies
Python
Pandas
NumPy
Scikit-learn
Matplotlib
Seaborn
Tableau
Jupyter Notebook
Skills Demonstrated
Data cleaning and preprocessing
Data wrangling
Exploratory data analysis
Feature engineering
Statistical reasoning
Classification modeling
Model evaluation
Handling class imbalance
Data visualization
Business insight generation
Stakeholder-focused communication

## Conclusion

This project demonstrates an end-to-end approach to solving a customer churn problem, from understanding and cleaning raw data to exploratory analysis, predictive modeling, evaluation, and visualization.

The analysis identified contract type, customer tenure, internet service, and payment method as important churn-related factors. The machine learning models provide a foundation for identifying customers who may be at higher risk of leaving and supporting targeted retention efforts.
