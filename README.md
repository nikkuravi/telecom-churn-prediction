# Telecom Churn Prediction Analysis

This project aims to predict customer churn for a telecom company based on their usage patterns and behavior.  Retaining existing customers is crucial for telecom businesses as it is more cost-effective than acquiring new ones. By predicting churn, the company can take proactive measures to retain valuable customers.

## Table of Contents

- [Problem Statement](#problem-statement)
- [Business Impact](#business-impact)
- [Data Overview](#data-overview)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Model Building](#model-building)
- [Model Performance](#model-performance)
- [Key Insights & Recommendations](#key-insights-recommendations)
- [Conclusion & Next Steps](#conclusion-next-steps)

## Problem Statement

Customer churn is a significant challenge for telecom companies.  The goal of this project is to develop a predictive model that identifies customers at high risk of churning, allowing the company to implement targeted retention strategies.

## Business Impact

Churn directly impacts revenue and increases marketing costs associated with acquiring new customers.  Predictive churn modeling empowers companies to:

* Reduce revenue loss.
* Minimize marketing expenses.
* Improve customer satisfaction and loyalty.

## Data Overview

The data used in this project is sourced from telecom usage records.  Key features include:

* `MonthlyCharges`: The amount charged to the customer monthly.
* `TotalCharges`: The total amount charged to the customer.
* `Tenure`: The number of months the customer has been with the company.
* `Contract Type`: The type of contract the customer has (e.g., month-to-month, one year, two year).
* `Internet Service`: The type of internet service the customer uses (e.g., DSL, Fiber optic).
* `Payment Method`: The customer's payment method.

The target variable is `Churn` (Yes/No).  High-value customers (top 30% based on `MonthlyCharges`) were filtered for this analysis.

## Exploratory Data Analysis (EDA)

The EDA process involved:

* Handling missing values.
* Addressing data imbalance (churners were significantly fewer than non-churners).

Key insights from EDA:

* Customers with month-to-month contracts had higher churn rates.
* Customers with fiber-optic internet service had higher churn rates.
* Higher `MonthlyCharges` were correlated with increased churn.

## Feature Engineering

* A `tenure_group` feature was created to categorize customers based on their subscription duration.
* One-Hot Encoding was applied to categorical variables.
* Numerical features were scaled to improve model performance.

## Model Building

* Algorithms used: Logistic Regression, Random Forest.
* Train-Test Split: 80%-20% using stratified sampling.
* Evaluation Metrics: Accuracy, Precision, Recall, F1-score, AUC-ROC.

## Model Performance

| Model             | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|-------------------|----------|-----------|--------|----------|---------|
| Logistic Regression | 82%      | 76%       | 65%    | 70%      | 0.85    |
| Random Forest     | 88%      | 81%       | 72%    | 76%      | 0.91    |

The Random Forest model performed better and was selected for potential deployment.

## Key Insights & Recommendations

* Customers with month-to-month contracts and high `MonthlyCharges` are more likely to churn.
* Offering discounts or incentives for long-term contracts to these customers can potentially reduce churn.
* Proactive engagement strategies, such as personalized offers and customer service check-ins, can improve retention.

## Conclusion & Next Steps

**Conclusion:**

Churn prediction is essential for revenue retention in the telecom industry. Analyzing customer behavior enables the development of targeted retention strategies.

**Next Steps:**

* Explore other models like XGBoost for potential performance improvements.
* Deploy the chosen model to automate churn prediction.
* Implement A/B testing to evaluate the effectiveness of implemented interventions.