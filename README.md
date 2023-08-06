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

