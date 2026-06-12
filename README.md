# Customer-Churn-Intelligence-System
# Customer Churn Intelligence System

## Project Overview

Customer churn is one of the most important business problems for subscription-based companies. Losing customers directly affects revenue, customer lifetime value, and long-term business growth.

This project presents an end-to-end **Customer Churn Intelligence System** that analyzes customer behavior, identifies churn patterns, builds machine learning models to predict churn, and translates the results into practical business recommendations.

The project focuses on both technical analysis and business value, making it suitable for a data science portfolio.

---

## Problem Statement

The main business question is:

**Can we identify customers who are likely to churn and understand the key factors behind their behavior?**

By answering this question, companies can:

* Detect high-risk customers early
* Reduce revenue loss
* Improve customer retention strategies
* Design better pricing and contract plans
* Increase customer lifetime value

---

## Dataset

The project uses the **Telco Customer Churn Dataset**.

The dataset contains customer information such as:

* Customer demographics
* Tenure
* Phone and internet services
* Contract type
* Payment method
* Monthly charges
* Total charges
* Churn status

Target variable:

* `Churn`: whether the customer left the company or not

Dataset size:

* Original dataset: **7,043 customers**
* Cleaned dataset: **7,032 customers**

---

## Tools and Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib

---

## Project Workflow

1. Data Loading
2. Data Understanding
3. Data Cleaning
4. Feature Engineering
5. Exploratory Data Analysis
6. Model Training
7. Model Evaluation
8. Feature Importance
9. Business Recommendations

---

## Data Cleaning

The main cleaning issue was related to the `TotalCharges` column. Although it represents a numerical value, it was stored as an object data type because some values contained blank spaces.

Cleaning steps:

* Converted `TotalCharges` from object to numeric
* Removed rows with missing `TotalCharges`
* Converted `Churn` into binary format:

  * No = 0
  * Yes = 1
* Removed `customerID` because it is only an identifier

Only 11 rows were removed, which represents a very small portion of the dataset.

---

## Feature Engineering

New features were created to improve analysis and model performance:

* `TenureGroup`: groups customers based on how long they stayed with the company
* `MonthlyChargeGroup`: categorizes customers into low, medium, and high monthly charges
* `MonthToMonthRisk`: identifies customers with month-to-month contracts

These features help capture churn-related customer behavior in a more business-friendly way.

---

## Exploratory Data Analysis

### Churn Distribution

![Churn Distribution](images/churn_distribution.png)

The overall churn rate is **26.58%**, meaning that around one-quarter of customers left the company.

---

### Churn Rate by Contract Type

![Churn by Contract](images/churn_by_contract.png)

Customers with **Month-to-month contracts** have the highest churn rate:

**42.71%**

This shows that short-term contract customers are more likely to leave because they have less commitment to the company.

---

### Churn Rate by Tenure Group

![Churn by Tenure Group](images/churn_by_tenure_group.png)

Customers in the **0–1 Year tenure group** have the highest churn rate:

**47.68%**

This indicates that new customers are at the highest risk of churn, making onboarding and early customer support very important.

---

### Churn Rate by Payment Method

![Churn by Payment Method](images/churn_by_payment_method.png)

Customers using **Electronic check** have the highest churn rate:

**45.29%**

This suggests that payment method is strongly related to churn behavior.

---

### Monthly Charges by Churn Status

![Monthly Charges by Churn](images/monthly_charges_by_churn.png)

Customers with higher monthly charges appear more likely to churn. This may indicate that pricing and perceived value are important factors in customer retention.

---

## Key Business Insights

The main insights from the analysis are:

* The overall churn rate is **26.58%**
* Month-to-month contract customers have the highest churn rate: **42.71%**
* Customers in their first year have the highest churn rate: **47.68%**
* Customers using electronic check have the highest churn rate: **45.29%**
* Higher monthly charges appear to be associated with higher churn risk
* Tenure, contract type, payment method, and pricing are major churn drivers

---

## Machine Learning Models

Two classification models were trained and compared:

1. Logistic Regression
2. Random Forest Classifier

The data was split into training and testing sets using an 80/20 split.
Categorical features were encoded using One-Hot Encoding, and numerical features were scaled using StandardScaler.

---

## Model Performance

| Model               | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
| ------------------- | -------: | --------: | -----: | -------: | ------: |
| Logistic Regression |   0.7214 |    0.4852 | 0.7914 |   0.6016 |  0.8343 |
| Random Forest       |   0.7683 |    0.5538 | 0.6604 |   0.6024 |  0.8147 |

---

## Best Model Selection

Although Random Forest achieved higher accuracy, Logistic Regression achieved better Recall and ROC-AUC.

In customer churn prediction, **Recall** is especially important because the company wants to identify as many potential churn customers as possible before they leave.

Logistic Regression achieved:

* Recall: **79.14%**
* ROC-AUC: **83.43%**

Therefore, **Logistic Regression** was selected as the best model for this project.

---

## Feature Importance

![Feature Importance](images/feature_importance.png)

The most influential churn-related features include:

* Tenure
* Internet service type
* Contract type
* Monthly charges
* Month-to-month contract risk
* Total charges

These results indicate that customer loyalty duration, service type, pricing, and contract commitment are major factors affecting churn behavior.

---

## Business Recommendations

Based on the analysis and model results, the company should consider the following actions:

### 1. Target Month-to-Month Customers

Customers with month-to-month contracts have the highest churn rate. The company should offer discounts, loyalty points, or special benefits to encourage these customers to switch to one-year or two-year contracts.

### 2. Improve New Customer Onboarding

Customers in the first year have the highest churn risk. The company should improve onboarding by providing welcome offers, follow-up communication, technical support, and satisfaction checks during the first months.

### 3. Monitor Electronic Check Customers

Customers using electronic check have a high churn rate. The company should investigate whether this payment method is connected to customer dissatisfaction, payment issues, or lower engagement.

### 4. Review Pricing for High Monthly Charge Customers

Customers with higher monthly charges may leave if they do not feel they are receiving enough value. The company should create personalized bundles, loyalty discounts, or value-added services for this group.

### 5. Use the Model as an Early Warning System

The selected Logistic Regression model can be used to identify high-risk customers. The company can then contact these customers before they churn and offer personalized retention actions.

---

## Project Structure

```text
Customer-Churn-Intelligence-System/
│
├── data/
│   ├── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   └── customer_churn_cleaned.csv
│
├── images/
│   ├── churn_distribution.png
│   ├── churn_by_contract.png
│   ├── churn_by_tenure_group.png
│   ├── churn_by_payment_method.png
│   ├── monthly_charges_by_churn.png
│   └── feature_importance.png
│
├── models/
│   └── best_churn_model.pkl
│
├── Customer_Churn_Analysis.ipynb
├── README.md
├── requirements.txt
├── model_results.csv
├── feature_importance.csv
└── .gitignore
```

---

## How to Run the Project

1. Clone the repository:

```bash
git clone https://github.com/your-username/Customer-Churn-Intelligence-System.git
```

2. Install the required libraries:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```bash
jupyter notebook Customer_Churn_Analysis.ipynb
```

4. Run all cells.

---

## Future Improvements

* Add Streamlit dashboard
* Add SHAP model interpretation
* Perform hyperparameter tuning
* Test additional models such as XGBoost
* Add customer segmentation
* Create a prediction form for new customers
* Deploy the model as a simple web application

---

## Project Summary

This project demonstrates the full data science workflow from data cleaning and exploratory analysis to machine learning and business recommendations.

It shows how customer data can be used to understand churn behavior, predict high-risk customers, and support data-driven decision-making.

The final model can help companies move from reactive customer loss analysis to proactive customer retention.
