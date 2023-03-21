# Pwc Switzerland Power BI virtual case experience - Customer Retention Analysis

---
![image](https://user-images.githubusercontent.com/24377958/226604798-dc5886e9-75aa-4927-8ad1-2841849286d7.png)
![image](https://user-images.githubusercontent.com/24377958/226608014-32f8f9d0-fef1-41d0-b9f5-d00df38ebf18.png)

# Table of Contents

- [Problem Statement](https://github.com/jiang54/Customer-Retention-Analysis#Problem-Statement)
- [Data Sourcing](https://github.com/jiang54/Customer-Retention-Analysis#Data-Sourcing)
- [Data Preparation](https://github.com/jiang54/Customer-Retention-Analysis#Data-Preparation)
- [Data Modeling](https://github.com/jiang54/Customer-Retention-Analysis#Data-Modeling)
- [Data Visualization](https://github.com/jiang54/Customer-Retention-Analysis#Data-Visualization)
- [Data Analysis](https://github.com/jiang54/Customer-Retention-Analysis#Data-Analysis)
- [Insights](https://github.com/jiang54/Customer-Retention-Analysis#Insights)
- [Recommendation](https://github.com/jiang54/Customer-Retention-Analysis#Recommendation)
- [Shareable link](https://github.com/jiang54/Customer-Retention-Analysis#Shareable-Link)


---

# Problem Statement

The purpose of this analysis is to: 
- Define proper KPIs
- Create a dashboard for the retention manager that reflects all relevant Key Performance indicators(KPIs)
and metrics in the dataset.
- Based on your findings, recommend suggestions as to what needs to be changed

Here are some inputs:
- Customers who left within the last month
- Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech 
support, and streaming TV and movies
- Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges 
and number of tickets opened in the categories administrative and technical
- Demographic info about customers – gender, age range, and if they have partners and dependents

---

# Data Sourcing

The Dataset used for this analysis was presented by [Pwc Switzerland](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and available at:

# Data Preparation

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.

The customer retention dataset is given by a table named:

- `churn` which has `23 columns and 7043 rows` of observation


The tabulation below shows the `churn` table with its column names and their description:
| Column Name | Description |
| ----------- | ----------- |
| customerID |   Represents the unique number of the customer in the dataset|
| gender | Describes the gender of the customer |
| SeniorCitizen | Describes if the customer is a senior citizen |
| Partner | Describes if the customer has a partner |
| Dependents | Describes if the customer has a dependent |
| tenure | Describes how long as a customer |
| PhoneService | Describes if the customer has registered a phone service |
| MultipleLines | Describes if the customer has registered multiple lines |
| InternetService | Describes if the customer has registered for internet service |
| OnlineSecurity | Describes if the customer has registered for online security  |
| OnlineBackup | Describes if the customer has registered for online backup |
| DeviceProtection | Describes if the customer has registered for device protection |
| TechSupport | Describes if the customer has registered for tech support |
| StreamingTV | Describes if the customer has registered  to stream tv|
| StreamingMovies | Describes if the customer has registered to stream movies |
| Contract | Describes if the length of the contract of the customer |
| PaperlessBilling | Describes if the customer has registered for paperless billing |
| PaymentMethod | Describes the payment method of the customer |
| MonthlyCharges | Represents the monthly charge incurred by the customer |
| TotalCharges | Represents the total charge incurred by the customer |
| numAdminTickets | Represents the number of admin tickets opened by the customer |
| numTechTickets | Represents the number of tech tickets opened by the customer |
| Churn | Describes if the customer is at risk of churn |

Data Cleaning for the dataset was done in power query as follows:

No row have missing value, data is clean and has meaningful column names
Each of the columns in the table were validated to have the correct data type

Column `Service Year` is added 
`Service Year = SWITCH(TRUE(),[tenure]<=12,"<=1 year",[tenure]<=24,"<=2 years",[tenure]<=36,"<=3 years",[tenure]<=48,"<=4 years",">4 years")`

#Data Modeling

A single table in Power BI covers most of the information and does not require any modeling.

![image](https://user-images.githubusercontent.com/24377958/226606789-bf9eb5d5-dda9-41ff-af1c-0542dff10b19.png)

# Data Analysis (Add Necessary Measures)
![image](https://user-images.githubusercontent.com/24377958/226606933-620fe1e0-1316-4ce5-b83c-98de8288074d.png)

`% of Citizen Yes = DIVIDE(CALCULATE(COUNTROWS('01 Churn-Dataset'), '01 Churn-Dataset'[SeniorCitizen] = 1), COUNTROWS('01 Churn-Dataset'))`

`% of Dependent = DIVIDE(CALCULATE(COUNTROWS('01 Churn-Dataset'), '01 Churn-Dataset'[Dependents] = "Yes"), COUNTROWS('01 Churn-Dataset'))`

`% of DeviceProtection = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[DeviceProtection] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

`% of OnlineBackup = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[OnlineBackup] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

`% of OnlineSecurity = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[OnlineSecurity] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

`% of Partner Yes = DIVIDE(CALCULATE(COUNTROWS('01 Churn-Dataset'), '01 Churn-Dataset'[Partner] = "Yes"), COUNTROWS('01 Churn-Dataset'))`

`% of PhoneService = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[PhoneService] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

`% of StreamingMovies = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[StreamingMovies] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

`% of StreamingTV = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[StreamingTV] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

`% of TechSupport = DIVIDE(calculate(countrows('01 Churn-Dataset'),'01 Churn-Dataset'[TechSupport] = "Yes"),COUNTROWS('01 Churn-Dataset'))`

# Data Visualization

The Chrun Dashboard shows the Demographics, Account Information, Service Items and some KPIs, e.g. Risk Customer, Phoneline Service, # of Admin Tickets, Yearly Charges, Monthly Charges

![image](https://user-images.githubusercontent.com/24377958/226604798-dc5886e9-75aa-4927-8ad1-2841849286d7.png)

The Personal Insight Pages shows my logic from finding > Analysis > Solutions
![image](https://user-images.githubusercontent.com/24377958/226607994-00d683a0-b284-47dd-9247-766d885ae83f.png)

# Insights
As we can see:

Findings are
About high rate of Churn:

Call Tech Support less
Less worry about data security and integrity
Perfer streaming movies and TV shows
More Likely M-M Contract
Higher Average Cost

Further thinking: 

May meet more technical Problems
Easier to data loss and device damage
Leding to higher monthly cost
More cautious and not want long-term service contract
Higher economic pressure

Solutions:

Increase response time and support speed
Promote online backup and device protection
More streaming movies and TV shows
Provide more flexible and cost-effective service contracts

# Virtual Case Experience Link
Virtual Case Experience:

[Virtual Case Experience Website](https://www.theforage.com/virtual-internships/prototype/a87GpgE6tiku7q3gu/PwC-Digital-Up-skilling-Virtual-Case-Experience?ref=38HZaFghHQngHaj8b)
