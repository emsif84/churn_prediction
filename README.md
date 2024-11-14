# 1 Background and Goals

* Source: https://www.kaggle.com/code/bandiatindra/telecom-churn-prediction/input
* Why did I choose this dataset? I am currently working in the Telco Industry and therefore i am familiar with this kind of data.
* The goal of this analysis is to explore the churn und revenue rate as well as to find patterns how the variables interact with churn. Based on the findings an another goal is to give recommendations to decrease the churn rate on a long-run. 

# 2 Data Structure
After tidying the dataset has `7030 observations` and `21 variables` which can be divided into `7 classes`:

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

## 3.1 Churn Rate
In total, based on this data 26% of the customers has churned in 6 years. The customer asset has decreased from 7030 to 5202 customers.<br><br>


55% of customers have a month-to-month contract, followed by customers with a two year contract (24%) and a one year contract (21%).

![Distribution Contract Types and Churn](/assets/img/Distribution_Contract_Types_and_Churn.png)

Looking at the churn rate per contract type, customers with a month-to-month contract have a very high churn rate of 43%, whereas customers with a one year contract only have a rate of 10%. Customers with a two year contract have the lowest churn rate of 3%.

When looking closer to the churn rate among tenure, a high proportion of customers churn already within few months. Considerable 47% of customers already churn in the first 8 months.  

![Total Distribution of Churn among tenure](/assets/img/Total_Distribution_of_Churn_among_tenure.png)

This very high proportion apply soley to customers with a month-to-month contract due to their not existing minimal contract duration. Furthermore because of the high volume of month-to-month contracts at the same time. Therefore the question comes up, why such a high proportion of customers churns within the first months. To answer this question, the data was divided into lower and upper 8 months.


## 3.2 Relationship Churn with categorical variables
When looking at the relationship between the categorical variables and churn, customers with no internet service have the lowest churn rate among the variables Online Security, Online Backup, Devide Protection, Tech Support, Streaming Movies and Streaming TV. However, customers which have internet service have higher churn rates when not making use of the variables Online Security, Online Backup, Devide Protection and Tech Support. The correlation between these variables and churn is statistically significant (p < .01) with a moderat relationship.

Interestingly, on the other hand, all socio-demographic variables - gender, dependents, partner and senior citizen, have small impacts on churn with respectively small correlations:

![Correlations Churn and categorical variables](/assets/img/Correlation_between_Churn_and_categorical_variables.png)
(low effect: 0.1; medium effect: 0.3; high effect: 0.5)

As already mentioned in Section 3.1, the contract types have a big impact on Churn with a statistically significant correlation of 0.41.




## 3.3 Financial effects on Churn


![Mean Monthly Charges by Internet Service](/assets/img/Mean_Monthly_Charges_by_Internet_Service.png)




# 5 Recommendations

# 6 Caveat



