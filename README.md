# Customer Churn Intelligence System

A complete data science project that analyzes customer churn behavior, identifies key churn drivers, builds machine learning models, and provides business recommendations to help companies reduce customer loss.

## Project Goal

The goal of this project is to predict whether a customer is likely to churn and understand the main factors that influence churn behavior.

## Dataset

The project uses the Telco Customer Churn dataset, which includes customer information such as tenure, contract type, payment method, internet service, monthly charges, total charges, and churn status.

After cleaning, the dataset contains 7,032 customers.

## Workflow

* Data loading and understanding
* Data cleaning
* Feature engineering
* Exploratory data analysis
* Machine learning modeling
* Model evaluation
* Feature importance analysis
* Business recommendations

## Key Insights

* Overall churn rate is 26.58%.
* Month-to-month customers have the highest churn rate: 42.71%.
* Customers in their first year have the highest churn rate: 47.68%.
* Customers using electronic check have the highest churn rate: 45.29%.
* Higher monthly charges are linked with higher churn risk.

## Models Used

Two models were trained:

* Logistic Regression
* Random Forest Classifier

## Model Results

| Model               | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
| ------------------- | -------: | --------: | -----: | -------: | ------: |
| Logistic Regression |   0.7214 |    0.4852 | 0.7914 |   0.6016 |  0.8343 |
| Random Forest       |   0.7683 |    0.5538 | 0.6604 |   0.6024 |  0.8147 |

## Best Model

Logistic Regression was selected as the best model because it achieved the highest Recall, which is important in churn prediction because businesses need to detect as many high-risk customers as possible.

## Main Churn Drivers

* Tenure
* Contract type
* Internet service type
* Monthly charges
* Payment method
* Total charges

## Business Recommendations

* Target month-to-month customers with retention offers.
* Improve onboarding for new customers.
* Monitor customers using electronic check payments.
* Review pricing plans for high monthly charge customers.
* Use the model as an early warning system to identify customers likely to churn.

## Tools Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib

## Conclusion

This project shows how customer data can be used to understand churn behavior, predict high-risk customers, and support better business decisions through data-driven retention strategies.
