# E-COMMERCE CUSTOMER CHURN ANALYSIS AND PREDICTION

## Background
- How to help business an product team to filter potential customer churn?

### Objective
- Build machine learning model to predict potensial customer churn

### Data and Assumption
- The dataset is obtained from [ecommerce customer churn analysis and prediction|Kaggle](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction)
- Calculation of GMV : `cashback = 10% GMV`,`GMV = Average cashback x number of orders last month x 10`
- Cleaned the data missing value with `median()`

## Data Analysis
### Data Overview
| **No** | **Variable** | **Description** |
|----|----------|-------------|
|1.|CustomerID|Unique customer ID|
|2.|Churn|Churn flag|
|3.|Tenure|Tenure of customer in organization|
|4.|PreferredLoginDevice|Preferred login device of customer|
|5.|CityTier| City Tier|
|6.|WarehouseToHome|Distance in between warehouse to home of customer|
|7.|PreferredPaymentMode|Preferred payment method of customer|
|8.|Gender|Gender of customer|
|9.|HourSpendOnApp|Number of hours spend on mobile application or website|
|10.|NumberOfDeviceRegistered|Total number of devices is registered on particular customer|
|11.|PreferredOrderCat|Preferred order category of customer in last month|
|12.|SatisfactionScore|Satisfactory score of customer on service|
|13.|MaritalStatus|Marital status of customer|
|14.|NumberOfAddress|Total number of added on particular customer|
|15.|Complain|Any complaint has been raised in last month|
|16.|OrderAmountHikeFromLastYear|Persentage increases in oreder from last year|
|17.|CouponUsed|Total number of coupon has been used in last month|
|18.|OrderCount|Total number of orders has been places in last month|
|19.|DaySinceLastOrder|Day last order by customer|
|20|CashbackAmount|Average cashback in last month|

**Load Data :**
- Target label : `Churn`
- 18 feature
- Categorical feature :
    - 3 `Tenure`
    - 5 `CityTier`
    - 6 `WarehouseToHome`
    - 8 `Gender`
    - 9 `HourSpendOnApp`
    - 11 `PreferedOrderCat`
    - 13 `MaritalStatus`

### Exploratory Data Analysis (EDA) 
![Monthly Churn](https://user-images.githubusercontent.com/99067852/162407929-bbef5ac4-7084-4535-bf16-1b54bda2ccd8.jpg)

**Observation & Insight :**
Customers with low Tenure (2 months first) has much higher churn potential from upper middle tenure

![Churn-not churn percentae composition of order category](https://user-images.githubusercontent.com/99067852/162407956-1e25eced-4a90-40db-a397-0bbc3eecd1e4.jpg)

**Observation & Insight :**
The percentage of churn due to customer complaints (32.9%) almost 3 times greater than churn percentage of total customers who did not complain (11.85%).

![Churn-not churn percentae composition of customer complain](https://user-images.githubusercontent.com/99067852/162407978-5099f4e7-6ee4-458d-9b64-4aa2fda604b6.jpg)

**Observation & Insight :**
Customers who order the phone category tend to churn compared to customers who order categories of goods other.

## Machine Learning Modellling
Before the model is trained, the dataset needs to be divided into two datasets, namely training data and testing data. In this case, the percentage for training data is 70% and testing data is 30%. Then, the data is trained into several machine learning algorithms and evaluated using two metrics, namely Recall score as primary metrics and Precision as secondary metrics. The use of recall metrics aims to minimize false negative values where customers who actually churn are considered not to churn. The use of precision scores as secondary metrics aims to reduce the false positive value (customers who don't actually churn are considered churn) are not too large. The training data is trained into the following machine learning models
- Logistic Regression
- Decision Tree
- KNN
- Random Forest
- XGBoost


## Model Evaluation
![table comparison](https://user-images.githubusercontent.com/99067852/162470906-8dd1ff34-e764-401b-b8ca-ab8aff5ffa91.jpg)

The table above shows the performance of each model after hyperparameter tuning and the best model is obtained, namely XGboost with a recall test value of 0.86 and a precision test of 0.58. So XGBoost was chosen as the model that will be used to predict the new data.

**Feature Importance**
![Feature Importance Score](https://user-images.githubusercontent.com/99067852/162472132-47f617c9-bfef-4885-a95b-822c7bda72b7.png)




