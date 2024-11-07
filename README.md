# 1 Background and Goals

* Source: https://www.kaggle.com/code/bandiatindra/telecom-churn-prediction/input
* Why did I choose this dataset? I am currently working in the Telco Industry and therefore i am familiar with this kind of data.
* The goal of this analysis is to explore the churn und revenue rate as well as to find patterns how the variables interact with churn. Based on the findings an another goal is to give recommendations to decrease the churn rate on a long-run. 

# 2 Data Structure
The dataset has `7043 observations` and `21 variables` which can be divided into `7 classes`:

1. `Key variable`: 
    * CustomerID
2. `Essential variables`:
    * Contract: Levels [Month-to-month, One year, Two year]
    * InternetService: Levels [DSL,Fiber optic, No]
    * PaymentMethod: Levels [Electronic check,Mailed check,Bank transfer (automatic),Credit card (automatic)]
3. `Feature variables`:
    * PaperlessBilling: Levels [Yes, No]
    * PhoneService: Levels [Yes, No]
    * MultipleLines: Levels [Yes, No, No phone service]
    * OnlineSecurity: Levels [Yes, No, No internet service]
    * OnlineBackup: Levels [Yes, No, No internet service]
    * Device Protection: Levels [Yes, No, No internet service]
    * TechSupport: Levels [Yes, No, No internet service]
4. `Financial variables`
    * MonthlyCharges
    * TotalCharges
5. `Behavioural variables`
    * StreamingTV: Levels [Yes, No, No internet service]
    * StreamingMovies: Levels [Yes, No, No internet service]
    * Churn: Levels [Yes, No]
6. `Socio-demographic variables`
    * gender: Levels [Female, Male]
    * SeniorCitizen: Levels [Yes, No]
    * Partner: Levels [Yes, No]
    * Dependents: Levels [Yes, No]
7. `Time variable`
    * tenure: in months


# 3 Executive Summary
* In total, 26% of the customers churn within 6 years. This makes a total loss of $2.857.223 (18% of total charges) and a loss per month of $396.840.
* 55% of customers have a month-to-month contract, followed by customers with a two year contract (24%) and a one year contract (21%).
* Looking at the churn rate per contract type, customers with a month-to-month contract have a very high churn rate of 43%, whereas customers with a one year contract only have a rate of 10%. Customers with a two year contract have the lowest churn rate of only 3%.
* When looking closer to the churn rate among tenure, a high proportion of customers churn already within few months. Considerable 47% of customers already churn in the first 8 months. This very high proportion apply only to customers with a month to month contract, due to their not existing minimal contract duration.  
* The most influential variables on churn have contract type,online security and tech support (moderat relationship). The lowest relationship with churn have multiple lines, phone service and gender.

# 5 Recommendations

# 6 Caveat



