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
In total, based on this data `26%` of the customers has churned in 6 years. The customer asset has decreased from 7030 to 5202 customers.

When Looking at the contract distribution (left figure), 55% of customers have a month-to-month contract, followed by customers with a two year contract (24%) and a one year contract (21%). When looking at the distribution of the Internet Service (right figure), 44% of the customers have a fiber optic contract, followed by 34% of customers with a DSL contract and lastly 22% customers with no Internet Service.

![Churn by Internet Service and Contract Types](/assets/img/churn_by_contracttypes_internetservice.png)

Examing the churn rate per contract type, customers with a `month-to-month contract` have a very high churn rate of `43%`, whereas customers with a `one year contract` only have a rate of `10%`. Customers with a `two year contract` have the lowest churn rate of `3%`. Regarding the churn rate by Internet Service, customers with a `fiber optic contract` have the highest churn rate of `42%`, customers with a `DSL contract` have a churn rate of `19%` and customers with `no internet service` have a rate of `7%`.<br><br>

When analysing the churn rate among tenure, a high high proportion of customers churn already within few months. Considerable 47% of customers already churn in the first 8 months.  

![Total Distribution of Churn among tenure](/assets/img/Total_Distribution_of_Churn_among_tenure.png)

This very high proportion apply soley to customers with a month-to-month contract due to their not existing minimal contract duration. Furthermore because of the high volume of month-to-month contracts at the same time. Therefore the question comes up, why such a high proportion of customers churns within the first months. To answer this question, the data was divided into lower and upper 8 months.


## 3.2 Correlation Churn with variables

In general, churn has at most a moderate relationship with the other variables. The strongest relationship with churn has contract types with a statistically significant correlation of 0.4, followed by Online security (0.35) and Tech Support (0,34). 

Interestingly, customers without internet service, tend to churn less compared to customers with internet service. When focusing on the customers with internet service, they are more likely to churn if they don´t take advantage of the features Online Security, Online Backup, Device Protection and Tech Support.

![Churn by categorical variables](/assets/img/churn_by_categorical_variable.png)

Finally, all socio-demographic variables - gender, dependents, partner and senior citizen, have small correlations with churn.

![Correlations Churn and categorical variables](/assets/img/Correlation_between_Churn_and_categorical_variables.png)
(low effect: 0.1; medium effect: 0.3; high effect: 0.5)  


# 4 Recommendations

# 5 Caveat



