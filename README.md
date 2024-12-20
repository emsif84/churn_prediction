# 1 Background and Goals

* Source: https://www.kaggle.com/code/bandiatindra/telecom-churn-prediction/input
* Why did I choose this dataset? I am currently working in the Telco Industry and therefore i am familiar with this kind of data.
* The goal of this analysis is to explore the churn und revenue rate as well as to find patterns how the variables interact with churn. Based on the findings an another goal is to give recommendations to decrease the churn rate on a long-run. 

# 2 Data Structure
After tidying the dataset has 7030 observations and 21 variables which can be divided into 7 classes:

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
In total, based on this data 26% of the customers has churned in 6 years. The customer asset has decreased from 7030 to 5202 customers, apart from customers who have signed contracts during this period.

When Looking at the contract distribution (left figure), 55% of customers have a month-to-month contract, followed by customers with a two year contract (24%) and a one year contract (21%). When looking at the distribution of the internet service (right figure), 44% of customers have a fiber optic as a service, followed by 34% of customers with DSL and lastly 22% customers with no internet service.

![Churn by Internet Service and Contract Types](/assets/img/churn_by_contracttypes_internetservice.png)

Examing the churn rate per contract type, customers with a month-to-month contract have a very high churn rate of 43%, whereas customers with a one year contract only have a rate of 10%. Customers with a two year contract have the lowest churn rate of 3%. Regarding the churn rate by internet service, customers with a fiber optic contract have the highest churn rate of 42%, customers with a DSL contract have a churn rate of 19% and customers with no internet service have a rate of 7%.<br>

When analysing the churn rate among tenure, a high high proportion of customers churn already within few months. Considerable 47% of customers already churn in the first 8 months.  

![Total Distribution of Churn among tenure](/assets/img/Total_Distribution_of_Churn_among_tenure.png)

This very high proportion apply soley to customers with a month-to-month contract due to their not existing minimal contract duration. Furthermore because of the high volume of month-to-month contracts at the same time. This finding will be discussed in the following section.


## 3.2 Correlation Churn with variables

In general, all variables have at most a moderate relationship with churn. The strongest correlation with churn has contract type with a statistically significant correlation of 0.4 (p<0.01), followed by online security (0.35, p<0.01) and tech support (0,34, p<0.01). Interestingly, socio-demographic variables, i.e. gender, dependents, partner and senior citizen have only a weak relationship with churn (from 0.009 to 0.165).

![Churn by categorical variables](/assets/img/churn_by_categorical_variable.png)

When looking at the variables which are only accessible to customers with internet service, i.e. online backup, online security, tech support and device protection, customers without any internet service are less likely to churn
in comparison to those who have DSL or fiber optic as an internet service. Beyond that, customers who have internet service tend to churn more when they don´t take advantage of them.<br>

As mentioned in the previous section, 47% of customers churn within the first 8 months. All these customers have a month-to-month-contract. This raises the question of why this happens. To anwser this question, data was analyzed by comparing customers who churned to those who don´t churned within 8 months.

![Churn by categorical variables ~ tenure <= 8 months](/assets/img/churn_by_categorical_variables_tenure_less_8months.png)

The results present a slightly different picture compared to the overall correlations. The most striking, internet service has now the highest correlation of 0.42 (p<0.01) with churn. It´s more likely that customers with fiber optic tend to churn more in the first 8 months compared to customers with DSL or with no internet service.<br>

Furthermore, internet service is followed by the variables online security (0.38, p<0.01), tech support (0.37, p<0.01) and online backup (0.34, p<0.01). As previously stated, customers with internet service tend to churn more but now it is sligthly more balanced between customers who take advantage of them to those who do not take advantage.<br>
Lastly, as already mentioned above, the high churn rate in the first 8 months exists due to the contract type itself. Customers choose month-to-month contracts to have the flexibility to churn at any time. All in all, feature variables still have the strongest relationship with churn, while socio-demographic variables show the weakest correlation.

# 4 Recommendations

1. Based on the results, it is recommended that the primary strategy should focus on minimizing the high churn rate during the first 8 months. Targeted interventions must be implemented to adress this high churn rate. This includes both customers with a month-to-month contract and customers using fiber optic as an internet service.
2. Following the primary strategy, interventions should aim to encourage more customers to choose a two year contract. This guarantee long term revenue, opens the oppurtunity to develop the customer relationship and development. Interventions could be more attractive prices, access to extra services or access to loyalty programs.
3. According to the internet service, despite the higher churn rate among customers with fiber optic as an internet service, due to the national goal of spreading fiber optic,     


4. When addressing the variables for targeted interventions, the emphasis should be placed less on socio-demographic factors and more on the variables Online Security, Online Backup, Device Protection and Tech Support. Customers with Internet Service who do not utilize these features are more likely to churn. Therefore, the goal should be to implement interventions that motivate customers to take advantage of these services.