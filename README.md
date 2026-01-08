
#  Customer Churn Analysis | Power BI

##  Overview

Customer churn is a critical business problem for subscription-based companies, as losing customers directly impacts revenue and growth.
This project uses **Power BI** to analyze customer data and identify **churn patterns, key drivers, and high-risk customer segments**, enabling data-driven retention strategies.

The project covers the **complete analytics lifecycle**:
data cleaning → modeling → DAX calculations → interactive dashboards → business insights.

---

##  Objectives

* Understand **who is churning**
* Identify **why customers churn**
* Analyze **service, contract, and billing behavior**
* Measure **revenue impact of churn**
* Support **churn prediction and retention decisions**

---

##  Dataset

The dataset dataset contains customer-level data with the following categories:

### Customer Demographics

* Gender
* Senior Citizen status

### Service Subscriptions

* Phone Service
* Internet Service (DSL, Fiber optic, No internet)
* Add-on services (Online Security, Tech Support, Streaming TV, Streaming Movies, etc.)

### Contract & Billing

* Contract type
* Payment method
* Paperless billing
* Monthly charges
* Total charges

### Customer Behavior

* Tenure
* Churn status (Yes / No)

Each row represents **one customer**.

---

##  Tools & Technologies

* **Power BI Desktop**
* **Power Query** – data cleaning & transformation
* **DAX** – KPIs and measures
* **Data Modeling**
* **Interactive Dashboards & Slicers**

---

##  Data Cleaning & Transformation

Data preparation was done using **Power Query**, including:

* Handling null and blank values
* Correcting data types (e.g., `TotalCharges`)
* Standardizing categorical columns
* Creating derived columns:

  * `SeniorCitizenFlag`
  * `TotalServices`
* Unpivoting service columns for service-level analysis

---

##  Key DAX Measures

```DAX
Total Customers =
COUNTROWS ( Telco )

Churned Customers =
CALCULATE (
    COUNTROWS ( Telco ),
    Telco[Churn] = "Yes"
)

Churn Rate =
DIVIDE ( [Churned Customers], [Total Customers] )

Avg Monthly Charges =
AVERAGE ( Telco[MonthlyCharges] )

Avg Total Charges =
AVERAGE ( Telco[TotalCharges] )

Revenue Lost =
CALCULATE (
    SUM ( Telco[TotalCharges] ),
    Telco[Churn] = "Yes"
)

Revenue Retained =
CALCULATE (
    SUM ( Telco[TotalCharges] ),
    Telco[Churn] = "No"
)
```

---

##  Dashboard Sections

### 1️ Customer Demographics Analysis

* Total customers & churned customers
* Churn distribution by gender and senior citizen status
* Tenure vs churn patterns

### 2️ Service Subscription Analysis

* Phone & internet service adoption
* Churn rate by internet service type
* Add-on services used by churned customers
* Relationship between number of services and churn

### 3 Contract & Billing Insights

* Churn rate by contract type
* Payment method vs churn
* Monthly & total charges analysis
* Paperless billing impact
* Tenure by contract duration

### 4️ Churn Prediction & Key Drivers

* Overall churn rate
* High-risk customer segments
* Revenue lost vs retained
* Consolidated churn drivers for prediction

---

##  Key Insights

* **Month-to-month contracts** have the highest churn
* **Fiber optic customers** churn more than DSL or no-internet users
* Customers with **fewer services** are more likely to churn
* **Electronic check** payment method shows higher churn
* Churn causes **significant revenue loss**
* Long-term contracts improve retention and lifetime value

---

##  Business Recommendations

* Encourage migration to **long-term contracts**
* Promote **service bundling** (Tech Support, Online Security)
* Target **high-risk segments** with personalized offers
* Monitor pricing strategies for high-charge customers

---

##  Outcome

This project demonstrates how **Power BI** can be used to:

* Convert raw data into actionable insights
* Identify churn drivers
* Support proactive customer retention strategies

---

##  How to Use

1. Download the `.pbix` file
2. Open in **Power BI Desktop**
3. Interact with slicers to explore churn patterns

---

###  If you find this project useful, feel free to star the repository!

