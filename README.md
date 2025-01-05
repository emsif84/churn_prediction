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
In total, based on this data 26% of the customers have churned in 6 years. The customer asset has decreased from 7030 to 5202 customers, apart from customers who have signed contracts during this period.

When analysing the churn rate among tenure, a high high proportion of customers churn already within few months. Considerable 47% of customers already churn in the first 8 months.

![Churn among months](/assets/img/churn_among_months.png)

This very high proportion apply soley to customers with a month-to-month contract due to their not existing minimal contract duration. Furthermore because of the high volume of month-to-month contracts at the same time. This finding will be discussed in the following section. 

To analyze the median churn moment of each contract type, tenure was scaled with a baseline of zero in each contract type to consider for its minimal duration. Based on this scaling, the median churn moment of month-to-month contracts is 7 months, the median churn moment of one year contracts is 39 months and the median churn moment of two year contracts is 41 months. This indicates that the type of contract influences the moment a customer is likely to churn.

![Distribution churn rate among internet service](/assets/img/distribution_internetservice_churn_yes.png)

As seen in the plots above, the distribution of the churn moment among customers with a month-to-month contract is highly right skrewed (left plot). A significant proportion of customers churn in the beginning of their contract as mentioned in the previous section. In contrast, the distribution of the churn moment for customers with a one year contract is more balanced (middle plot) but also shows a tendency to increase with higher tenure. Lastly, the distribution for customers with a two year contract is also highly skrewed, but to the left (right plot).

## 3.2 Churn Value
The sum of total charges account for $16,050,465 whereas the sum of total charges among customers who have churned account for $2,857,223. This makes a furture loss of 18% apart from customers who have signed contracts during this period.

When focusing on monthly charges, the median monthly charge of $80 among customers who have churned is generally higher compared to $64 for those who have not churned. 
Breaking down the median monthly charges among internet services, customers with fiber optic have the highest median of $92, followed by customers with DSL at $56 and finally customers with no internet service at $20. 

![MonhtlyCharges by Internet Service and Churn](/assets/img/monthlycharges_internetservice_churn.png)

When comparing the distribution of the median monthly charge between customers who haved churned and those who have not, the median charges of $87 among customers with fiber optic who have churned is lower to those who have not churned with $95. Similarly, the median monthly charges for customers with DSL who have churned is $49, compared to $60 for those who have not churned. Customers with no internet service have a median monthly charges of $20, regardless of whether they have churned or not.

## 3.3 Correlation Churn with variables

In general, all variables have at most a moderate relationship with churn. The strongest correlation with churn has contract (Cramers`v=0.41, p<0.01), followed by internet service (Cramers'V=0,33, p<0.01) and payment method (Cramers'V=0,30, p<0.01). Interestingly, socio-demographic variables, i.e. gender, dependents, partner and senior citizen show only a weak relationship with churn and therefore play only a subordinate role in predicting it.

When analyzing the contract distribution (left plot), 3875 customers have a month-to-month contract (55%), followed by 1695 customers with a two year contract (24%) and 1460 customers with a one year contract (21%). Regarding the distribution of internet service (right plot), 3094 customers have fiber optic as a service (44%), followed by 2414 customers with DSL (34%) and lastly 1522 customers with no internet service (22%).

![Churn by InternetService, Contract](/assets/img/churn_by_internetservice_contract.png)

Examing the churn rate per contract type, customers with a month-to-month contract have a very high churn rate of 43%, whereas customers with a one year contract only have a rate of 10%. Customers with a two year contract have the lowest churn rate of 3%. Regarding the churn rate among internet service, customers with fiber optic have the highest churn rate of 42%, customers with DSL have a churn rate of 19% and customers with no internet service have a rate of 7%.<br>
Analyzing the variables accessible only to customers with internet service (count=5508), i.e. online security, tech support, online backup and device protection - online security  (Cramers´V=0.28, p<0.01) and tech support (Cramers´V= .27, p<0.01) have the strongest correlation with churn.

As mentioned in the previous section, 47% of customers churn within the first 8 months. All these customers have a month-to-month-contract. This raises the question of why this happens. To anwser this question, data was analyzed by comparing customers who churned to those who don´t churned within 8 months. The results present a slightly different picture compared to the overall correlations. The most striking, internet service has now the highest correlation of 0.42 (p<0.01) with churn. It´s more likely that customers with fiber optic tend to churn more in the first 8 months compared to customers with DSL or with no internet service. Furthermore, internet service is followed by  payment method (Cramers'V=0.28, p<0.01) and paperless billing (Cramers'V=0.25,p<0.01). Online security decreased to 0.21 (Cramers'V, p<0.01) but still shows the strongest relationship with churn among customers with internet service, while tech support dropped to 0.17 (Cramers'V, p<0.01)
Lastly, as already mentioned, the high churn rate in the first 8 months exists due to the contract type itself. Customers choose month-to-month contracts to have the flexibility to churn at any time. All in all, internet service and indirect contract types have the strongest relationship with churn, while the correlation with socio-demographic variables remain weak.

# 4 Recommendations

1. Based on the results, it is recommended that the primary strategy should focus on minimizing the high churn rate during the first 8 months. Targeted interventions must be implemented to adress this high churn rate. This primary includes both customers with a month-to-month contract and customers using fiber optic as an internet service.
2. Following the primary strategy, interventions should aim to encourage more customers to choose a two year contract. This guarantee long-term revenue, opens the oppurtunity to develop the customer relationship and development. Interventions could be more attractive prices, access to extra services or access to loyalty programs.
3. When addressing internet service for tackling the high churn rate among customers particularly with fiber optic as a service, and in light of national goals to diffuse fiber optic technology, the long-term strategy should be to convince more customers of both the short-term and long-term benefits of choosing fiber optic technology. <!--Regarding of a recent study of Bearingpoint (2024*) about the acceptance of fiber optic among german households-->