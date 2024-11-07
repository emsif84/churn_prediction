# 1 Background and Goals

* Source: https://www.kaggle.com/code/bandiatindra/telecom-churn-prediction/input
* You can find the description about the variables in the link.
* The analysis is divided into 2 parts: The first part is about customer and revenue churn and the second part is about churn prediction using machine learning models. The second part has not been published yet.
* Why did I choose this dataset? Simply because i´m currently working in the telco industry and therefore familiar with this kind of data.

# 2 Data Structure
* The dataset has 7043 observations and 21 variables which can be divided into x classes. The classes and description of the variables are as follow:

1. Key variable: CustomerID
2. Contract variables:
    * Contract: Levels [Month-to-month, One year, Two year]
    * InternetService: Levels [DSL,Fiber optic, No]
    * PaperlessBilling: Levels [Yes, No]
    * PaymentMethod: Levels [Electronic check,Mailed check,Bank transfer (automatic),Credit card (automatic)]
3. Feature variables:
    * PhoneService
    * MultipleLines
    * OnlineSecurity
    * OnlineBackup
    * Device Protection
    * TechSupport

# 3 Executive Summary
* In total, 26% of the customers churn within 6 years. This makes a total loss of $2.857.223 (18% of total charges) and a loss per month of $396.840.
* 55% of customers have a month-to-month contract, followed by customers with a two year contract (24%) and a one year contract (21%).
* Looking at the churn rate per contract type, customers with a month-to-month contract have a very high churn rate of 43%, whereas customers with a one year contract only have a rate of 10%. Customers with a two year contract have the lowest churn rate of only 3%.
* When looking closer to the churn rate among tenure, a high proportion of customers churn already within few months. Considerable 47% of customers already churn in the first 8 months. This very high proportion apply only to customers with a month to month contract, due to their not existing minimal contract duration.  
* The most influential variables on churn have contract type,online security and tech support (moderat relationship). The lowest relationship with churn have multiple lines, phone service and gender.

# 5 Recommendations

# 6 Caveat



