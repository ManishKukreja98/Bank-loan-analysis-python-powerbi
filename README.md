# 📊 Bank Loan Portfolio Analysis | Python,Power BI

## 📝 Project Overview
This project presents an **end-to-end analysis** of bank loan data to evaluate portfolio performance, identify risk areas, and uncover actionable business insights.  
Using **Python & Power BI**, analysis report and interactive dashboards were created to track key metrics, analyze borrower profiles, and monitor loan performance across multiple dimensions.  

The analysis is structured into three dashboards:  
1. **Summary Dashboard** → High-level KPIs and loan status overview.  
2. **Overview Dashboard** → Trends, regional patterns, and borrower demographics.  
3. **Details Dashboard** → Granular view of loan applications and portfolio performance.

To view/download the analysis report using python [click here](https://github.com/ManishKukreja98/Bank-loan-analysis-python-powerbi/blob/414d88b1366a75ce2452bbf181d8b8c0c1940b2d/Main-files/Python%20Bank%20Loan%20Analysis.pdf)

To view/download the dashboard file [click here](https://github.com/ManishKukreja98/Bank-loan-analysis-powerbi/blob/11b089d19e5957e9e7d6e0f88a3fcb68bfe851c0/Main-files/Bank%20loan%20report%20powerbi%20dashboard.pbix)

##  📌Project Preview

Below are snapshots of the three dashboards included in this project:  

### 1. Summary Dashboard

 ![summary](https://github.com/ManishKukreja98/Bank-loan-analysis-powerbi/blob/11b089d19e5957e9e7d6e0f88a3fcb68bfe851c0/Assets/Screenshot%20dashboard1%20.png)
  
### 2. Overview Dashboard  

![Overview](https://github.com/ManishKukreja98/Bank-loan-analysis-powerbi/blob/11b089d19e5957e9e7d6e0f88a3fcb68bfe851c0/Assets/Screenshot%20dashboard2.png)
  
### 3. Details Dashboard

![Details](https://github.com/ManishKukreja98/Bank-loan-analysis-powerbi/blob/11b089d19e5957e9e7d6e0f88a3fcb68bfe851c0/Assets/Screenshot%20dashboard%203.png)

## 📝 Executive Summary  

This project analyzes a **Bank Loan Dataset** to evaluate loan portfolio performance and borrower behavior. Using **Python(Pandas, Matplotlib, Seaborn, Plotly)** for exploratory analysis and **Power BI** with data modeling, and DAX calculations, the dashboards provide actionable insights:  

- ✅ **Loan Quality** – 86.2% of loans are classified as *good loans*, while 13.8% fall under *bad loans*.  
- 🏢 **Risk Segments** – A large share of bad loans (~25%) were borrowed for *small business* purposes.  
- 💳 **Borrower Intent** – The majority of loan applications were for *debt consolidation*, highlighting a strong trend in financial restructuring.  
- 📆 **Loan Terms** – ~73% of loans were issued with a *36-month term*, indicating borrower preference for shorter repayment horizons.  
- 💍 **Good Loan Drivers** – Nearly 90% of good loans were linked to *weddings* or *major purchases*, suggesting lower default risks in personal-purpose lending.  

These insights enable lenders and financial institutions to:  
-  Identify high-risk loan categories.  
-  Optimize portfolio mix across loan purposes and terms.  
-  Strengthen risk assessment frameworks to reduce defaults.  

## ⚙️ Methodology 

The analysis followed a **two-stage approach using Python and Power BI** to ensure both **deep exploratory analysis** and **interactive dashboarding**.  

---
### **Stage 1 – Data Analysis with Python**  
The raw dataset was first analyzed using **Python** with libraries such as:  
- **Pandas** → for data cleaning, preprocessing, and aggregations.  
- **Matplotlib & Seaborn** → for exploratory data visualization and trend analysis.  
- **Plotly** → for interactive visualizations and deeper portfolio insights.  

Key insights such as loan quality distribution, borrower intent, loan term preferences, and risk segmentation were derived in Python. These insights guided the **dashboard design in Power BI**.  

---

### **Stage 2 – Dashboard Development in Power BI**  
Power BI was then used to create interactive and business-ready dashboards by leveraging advanced data modeling and DAX capabilities.  

Key steps in the methodology include:  

- **Date Table Integration** – A custom *Date Table* was created and linked to the main dataset in the model view. This enabled the use of **Time Intelligence Functions**, such as:  
  - Month-to-Date (MTD) calculations  
  - Month-on-Month (MoM) performance tracking
 
![Data Model](https://github.com/ManishKukreja98/Bank-loan-analysis-powerbi/blob/11b089d19e5957e9e7d6e0f88a3fcb68bfe851c0/Assets/Screenshot%20of%20data%20model.png) 

-  **Dynamic Measure Selection** – A **parameter field** called *Select Measure* was introduced, allowing users to seamlessly switch between different financial metrics:  
    Total Loan Applications  
    Total Funded Amount  
    Total Amount Received  

-  **DAX Calculations** – Functions such as `CALCULATE`, `SUM`, and date-based functions were applied to compute KPIs and trends.  

-  **KPI Calculations using Time Intelligence** – Custom DAX formulas were created to track loan performance over time. For example:  

  - **Month-to-Date (MTD) Amount Received**  
    ```DAX
    MTD Amount Received = CALCULATE([Total Amount Received], DATESMTD('Date'[Date]))
    ```

  - **Previous Month-to-Date (PMTD) Amount Received**  
    ```DAX
    PMTD Amount Received = CALCULATE([Total Amount Received], DATESMTD(DATEADD('Date'[Date], -1, MONTH)))
    ```

  - **Month-over-Month (MoM) Amount Received**  
    ```DAX
    MoM Amount Received = 
      DIVIDE(
        [MTD Amount Received] - [PMTD Amount Received],
        [PMTD Amount Received]
      )
    ```

  Similar formulas were created for other KPIs such as **Loan Applications, Funded Amount, and Average Interest Rate**, enabling robust time-based performance tracking.

## 💡 Recommendations  

Based on the analysis of the loan portfolio, the following recommendations can help optimize lending decisions and risk management:  

1. **Strengthen Small Business Loan Evaluation** 
   - Since a large proportion of bad loans (25%) were taken for small business purposes, stricter eligibility criteria, enhanced due diligence, and better risk assessment models should be applied to small business loan applicants.  

2. **Encourage Low-Risk Loan Purposes** 
   - With nearly 90% of loans for weddings and major purchases classified as good loans, the bank could consider offering targeted loan products with favorable terms for these categories to promote healthy repayment rates.  

3. **Monitor Loans Closely and leverage Predictive Analytics** 
   - Future models can use borrower employment stability, income levels, and debt-to-income ratios to predict default probabilities, thereby reducing the chances of bad loans.  

