# **Predict Customer Personality to Boost Marketing Campaign by Using Machine Learning**

**Created by:**
- Siti Hajjah Mardiah
- Email : sitihamardiah1997@gmail.com
- Linkedin : https://www.linkedin.com/in/sitihajjahmardiah/

## **📍 Table of Content 📍**
- Business Understanding
    - Problem Statement
    - Goals
    - Objectives
- Data Preparation
    - Data Description
    - Libraries & Datasets
- Data Understanding
    - Exploring Datasets
    - Feature Engineering
    - EDA (Exploratory Data Analysis)
- Data Preprocessing
    - Checking Data Null and Duplicated Data
    - Handling Missing Value
    - Drop Unnecessary Feature
    - Feature Encoding
- Clustering Model
    - Elbow Method
    - Silhouette Score
    - K-Means Clustering
- Insights and Business Recommendations
    - Insights
    - Business Recommendations
 

## **⚙ Work Environment ⚙**

- **Tools**

[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)

- **Programming Language**

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)

- **Dataset**

[Marketing campaign](https://drive.google.com/file/d/1fg5Oh0zoyA_qDMziplBrbiJ-7X7QxYfp/view?usp=sharing)

## **⛳ Business Understanding ⛳**

### **📌 Problem Statement**

The company can develop rapidly when it knows the behavior of its customer personality, so that it can provide better services and benefits to potential customers to become loyal customers. By processing historical marketing campaign data to improve performance and target the right customers so they can transact on the company's platform, from this data insight our focus is to create a cluster prediction model to make it easier for companies to make decisions.

### **📌 Goals**
Creating customer segmentation to find out potential customers according to their behavior with the aim of providing the best treatment for customers so that companies can easily make decisions and improve marketing campaign performance.

### **📌 Objectives**

Creating customer segmentation by cluster prediction model using unsupervised learning to find out potential customers according to their behavior.

## **⛳ Data Preparation ⛳**

### **📌 Data Description**

**Marketing Campaign Dataset [link dataset](https://drive.google.com/file/d/1fg5Oh0zoyA_qDMziplBrbiJ-7X7QxYfp/view?usp=sharing)**

**Dataset Description:**

This dataset contains `2240 samples/rows` and `29 features/columns`, which is each feature can be grouped into several groups including Accepted/Responses Campaign, Customer Information, Sales Product Type, Number of Purchases Type, Cost and Revenue. The following are for more details:

**Accepted/Responses Campaign**

- `AcceptedCmp1` - 1 if customer accepted the offer in the 1st campaign, 0 otherwise
- `AcceptedCmp2` - 1 if customer accepted the offer in the 2nd campaign, 0 otherwise
- `AcceptedCmp3` - 1 if customer accepted the offer in the 3rd campaign, 0 otherwise
- `AcceptedCmp4` - 1 if customer accepted the offer in the 4th campaign, 0 otherwise
- `AcceptedCmp5` - 1 if customer accepted the offer in the 5th campaign, 0 otherwise
- `Response (target)` - 1 if customer accepted the offer in the last campaign, 0 otherwise
- `Complain` - 1 if customer complained in the previous 2 years

**Customer Information**

- `ID` - Customer's id
- `Year_Birth` - Customer's year of birth
- `Education` - customer’s level of education
- `Marital_Status` - customer’s marital status
- `Income` - customer’s yearly household income
- `Kidhome` - number of small children in customer’s household
- `Teenhome` - number of teenagers in customer’s household
- `DtCustomer` - date of customer’s enrolment with the company
- `Recency` - number of days since the last purchase

**Sales Product Type**

- `MntCoke` - amount spent on cokce products
- `MntFishProducts` - amount spent on fish products
- `MntMeatProducts` - amount spent on meat products
- `MntFruits` - amount spent on fruits products
- `MntSweetProducts` - amount spent on sweet products
- `MntGoldProds` - amount spent on gold products

**Number of Purchases Type**

- `NumDealsPurchases` - number of purchases made with discount
- `NumWebPurchases` - number of purchases made through company’s web site
- `NumCatalogPurchases` - number of purchases made using catalogue
- `NumStorePurchases` - number of purchases made directly in stores
- `NumWebVisitsMonth` - number of visits to company’s web site in the last month

**Cost and Revenue**

- `Z_CostContact = 3` (Cost to contact a customer)
- `Z_Revenue = 11` (Revenue after client accepting campaign)

# **💡 Data Understanding 💡**

## **📌 Explore Datasets**

### **💉 Basic Datasets Information**

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/425780bc-1696-4817-92b0-c67a980b2a0c)

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/24c30c62-daf1-4107-a7f3-4846ac0aef00)

**Observations:**

- Dataset has `29 columns` and `2240 rows` data
- There are 3 types of data types namely: `int64, object, float64`
- `Income` column has 2216 non-null values, and `24 null / missing values`

## **📌 Feature Engineering** ##

Creating Features Engineering for these columns:

- Age
- Age Group
- Total Dependents
- Customer Has Children
- Total Spending
- Total Transactions
- Total Accepted Campaign (Accepted Campaign 1-5)
- Ever Accepted Campaign (Accepted Campaign at least 1x)
- Conversion Rate
- Income Segmentation
- Recency Segmentation

# **💡 Exploration Data Analysis (EDA) 💡**

## **📌 Correlation between Conversion Rate and related Attributes which potentially respond to a campaign** ##

For checking correlation, can use several methods:
- Heatmap Correlation
- Diverging Bars
- Marginal Histogram

### **💉 Heatmap Correlation** ###

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/441d3977-5f51-4b5e-a0fc-bfcc4c18cef0)

### **💉 Diverging Bars** ###

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/e8bab5d9-38e0-4161-a1dd-ff7b0e143523)

**Observations:**

After conducting the analysis to find a correlation between the Conversion Rate and related Attributes using Heatmap and Diverging Bars, the following information is obtained:
- Top 10 attributes that have strong correlation with Conversion Rate (the coefficient value >= 0.5):
    - NumWebVisitsMonth - 0.72 - Negatif
    - NumCatalogPurchases - 0.66 - Positif
    - TotalSpending - 0.62 - Positif
    - MntMeatProducts - 0.62 - Positif
    - NumStorePurchases - 0.55 - Positif
    - Total_Transactions - 0.53 - Positif
    - Income - 0.53 - Positif
    - MntSweetProducts - 0.52 - Positif
    - Has_child - 0.51 - Negatif
    - MntFishProducts - 0.51 - Positif
- In addition, there are several attributes that have a fairly strong correlation with the Conversion Rate (the coefficientlies between 0.30 and 0.49):
    - MntFruits - 0.48 - Positif
    - Dependents - 0.46 - Negatif
    - Kidhome - 0.44 - Negatif
    - MntCoke - 0.44 - Positif
    - MntGoldProds - 0.37 - Positif
    
Based on these results, further analysis can be conducted to visualize the correlation between attributes which are strongly correlated with the Conversion Rate individually using the Marginal Histogram.

### **💉 Marginal Histogram** ###

**Conversion Rate VS Income**

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/4583731c-ffd0-4fce-a3c9-dab9291ebd20)


**Conversion Rate VS Total Spending**

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/6a069831-4fe4-4678-be84-2119b4dae621)

**Conversion Rate VS Age**

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/3e7e7248-67b3-495d-abbe-46f4934af861)

**Insights:**
Based on the Heatmap data visualization, it shows that there are several attributes which have strong positive correlation with the Conversion Rate, including TotalSpending, Total_Transactions, Income, NumCatalogPurchases and NumStorePurchases, MntMeatProducts, MntSweetProducts, MntFishProducts, MntFruits, MntCoke and MntGoldProds.

**Recommendations:**
From information above, based on attributes which have strong positive correlation with the conversion rate, 3 conclusions can be drawn:
- Based on customer behavior, there are 3 attributes that most influence the conversion rate, namely TotalSpending, Total_Transactions and Income. Therefore, further marketing campaigns can be implemented for customers who have high TotalSpending, Total_Transactions and Income.
- Based on purchase type, it is recommended that more marketing campaigns be implemented through catalogs and shops.
- Based on the product type, it is recommended that the types of products promoted are Meat Products, Sweet Products, Fish Products, Fruit Products, Coke and Gold Products.

# **⛳ Data Preprocessing ⛳**

**📌 Checking Data Null and Duplicated Data**

**📌 Handling Missing Value**

**📌 Drop Unnecessary Feature**

**📌 Feature Encoding**

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/90cc2a93-f56b-4178-a620-525a5142ad5a)

**📌 Check Outliers and Handling Outliers**

**📌 Check and Handling Data Distribution**

# **⛳ Clustering Model ⛳**

To determine the optimal number of clusters, we have to select the value of k at the “elbow” ie the point after which the distortion/inertia start decreasing in a linear fashion.

Distortion is calculated as the average of the squared distances (let’s say Euclidean distance) from the cluster centers of the respective clusters. Inertia represents the sum of squared distances of samples to their closest cluster center.

## **📌 Elbow Method** ##

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/4178b807-1253-4b75-acdd-0e092ea77a9a)

**Observation:**

Based on the results of determining the number of clusters using the elbow method, the changes did not change significantly in the 4 clusters, so they will be divided into 4 clusters.

## **📌 Silhoutte Score** ##

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/424ea798-6c77-4821-9fb2-f064f976d12e)

**Observations**

Based on visualization above, n_cluster = 4 is an optimal number for K-Means Clustering in this dataset

## **📌 K-Means Clustering**

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/127fab4a-7d77-416e-8e45-5559a85abb04)

**Observation**

Based on visualization above, there is clearly 4 clusters that generated by K-Means Clustering algorithm using RFM Method for this dataset.

![image](https://github.com/sitihamardiah/Predict-Customer-Personality-to-Boost-Marketing-Campaign-by-Using-Machine-Learning/assets/134268514/df98b206-5364-4144-bc6d-e1ea1f6098fd)

# **⛳ Insights and Business Recommendations ⛳**

### **Insights** ###

**1. Fairly Potential Customer (Cluster 0)**
- There are 494 customers (22.05% of total customers) in this group
- Customers in this group have  average recency 24 days, average of total transactions 7 items and average total spending money 76,469
- This group dominated by Adult customers 11.47% (20-50 years old) have average income around 35,433,907

**2. Most Potential Customer (Cluster 1)**
- There are 617 customers (27.54% of total customers) in this group
- Customers in this group have  average recency 23 days, average of total transactions 20 items and average total spending money 996,356
- This group dominated by Elder customers 17.07% (>50 years old) have average income around 65,403,923

**3. Potential Customer (Cluster 2)**
- There are 650 customers (29.02% of total customers) in this group
- Customers in this group have  average recency 73 days, average of total transactions 20 items and average total spending money 1,019,693
- This group dominated by Elder customers 19.15% (>50 years old) have average income around 65,133,940

**4. Need Attention Customer (Cluster 3)**
- There are 479 customers (21.38% of total customers) in this group
- Customers in this group have  average recency 74 days, average of total transactions 7 items and average total spending money 86,970
- This group dominated by Elder customers 11.4% (>50 years old) have average income around 35,109,462

### **Business Recommendation** ###

**1. Fairly Potential Customer (Cluster 0)**
- Characteristic: Very active for shopping, quite high shopping intensity, spending quite much of money
- Recommendations: Give Discount/Flash Sale, Promo Bundling/Special Offer, Buy 1 Get 1 strategy
    - Example: If customers buy Coke Product with this promo, so they will get 1 free Coke
Recommendations: Vouchers/Rewards, Promo Bundling/Special Offer with Cross Selling bundling
**2. Most Potential Customer (Cluster 1)**
- Characteristic: Very active for shopping, spending quite much of money, very high shopping intensity
- Recommendations: Vouchers/Rewards,  Promo Bundling/Special Offer, Mix & Match bundling strategy
    - Example: Free to choose Coke from 3 different types/brands if meet the minimum purchase

**3. Potential Customer (Cluster 2)**
- Characteristic: Active for shopping, spending very much of money, very high shopping intensity
- Recommendations: Vouchers/Rewards, Promo Bundling/Special Offer with Cross Selling bundling
    - Example: Every purchase of Coke & Meat Products at the same time can get a 10% cheaper price

**4. Need Attention Customer**
- Characteristic: Quite active for shopping, spending quite much of money, quite high shopping intensity
- Recommendations: Discount/Flash Sale, Promo Bundling/Special Offer, Buy 1 Get 1 and Limited Edition Bundling (giving urgency sense to purchase)
    - Example: Get Coke Product promo with 55% discount at 9 AM - 11 AM only
