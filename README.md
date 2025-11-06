# 📊 Customer Churn Analysis Project

## 🔹 Project Overview
This project focuses on **analyzing and predicting customer churn** for a telecom company. The goal is to identify high-risk customers, understand churn patterns, and provide actionable insights for **retention strategies**. The solution combines **SQL ETL**, **Power BI dashboards**, and **Python (Random Forest)** machine learning.

---

## 🔹 Data & Resources
- **Dataset:** Customer demographics, account details, payment info, services, and churn status  
- **Visualization Colors:** #4A44F2, #9B9FF2, #F2F2F2, #A0D1FF  
- **Target Audience:** Telecom, retail, finance, and any business focusing on **customer retention**  

---

## 🔹 Step 1: ETL in SQL Server
- Created database `db_Churn` and staging table `stg_Churn` from CSV  
- Cleaned and handled nulls using `ISNULL`  
- Loaded cleaned data into production table `prod_Churn`  
- Created SQL views for Power BI:  
  - `vw_ChurnData` → Customers who **Churned / Stayed**  
  - `vw_JoinData` → **New Joiners**

**Key Metrics Computed in SQL:**  
- Total Customers  
- Total Churn & Churn Rate  
- New Joiners  

---

## 🔹 Step 2: Power BI Transformations
- Added calculated columns:  
  - `Churn Status` (1 = Churned, 0 = Stayed)  
  - `Monthly Charge Range`  
- Created mapping tables:  
  - `Age Group` & `Tenure Group` (with sorting for visualization)  
- Unpivoted services for analysis of service usage patterns  

---

## 🔹 Step 3: Power BI Measures
- **Total Customers:** COUNT(Customer_ID)  
- **New Joiners:** COUNTIF(Customer_Status = "Joined")  
- **Total Churn:** SUM(Churn Status)  
- **Churn Rate:** Total Churn / Total Customers  

---

## 🔹 Step 4: Power BI Dashboards & Insights
**Summary Page:**  
- Top Cards: Total Customers, New Joiners, Total Churn, Churn Rate%  
- Demographics: Churn rate by **Gender & Age Group**  
- Account Info: Churn rate by **Payment Method, Contract, Tenure Group**  
- Geography: Top 5 states by Churn Rate  
- Services: Churn rate by **Internet Type & Service Usage**  
- Churn Reason: Breakdown by category & reason  

**Churn Prediction using Random Forest:**  
- Imported SQL views → Excel → Python (Jupyter Notebook)  
- Preprocessed data: Label encoding, target encoding  
- Trained Random Forest model, evaluated with **Confusion Matrix & Classification Report**  
- Predicted high-risk customers from joiner data → Saved for visualization in Power BI  

**Prediction Dashboard Highlights:**  
- Right-side grid: Customer ID, Monthly Charge, Total Revenue, Refunds, Referrals  
- Demographics: Churn count by Gender, Age, Marital Status  
- Account Info: Churn count by Payment Method, Contract, Tenure Group  
- Geography: Churn count by State  

---

## 🔹 Outcome & Impact
- Complete **ETL process** for customer data  
- Interactive **Power BI dashboards** for historical and predicted churn  
- **Predictive model** identifies potential churners with high accuracy  
- Insights used for targeted marketing and **customer retention strategies**  

**Technologies Used:** SQL Server, Power BI, Python (pandas, scikit-learn, matplotlib, seaborn)  

