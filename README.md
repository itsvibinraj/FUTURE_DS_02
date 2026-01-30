# FUTURE_DS_02
# 📊 Social Media Campaign Performance Tracker

![Power BI](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)

## 📖 Project Overview
This project is part of a data analytics internship task to analyze the performance of simulated social media ad campaigns. The goal was to build an interactive **Power BI Dashboard** that helps marketing teams evaluate ad effectiveness, optimize ad spend, and identify the most profitable demographics.

The dashboard answers critical business questions such as:
* How well did the ad campaign perform overall?
* Which specific campaigns had the highest Return on Investment (ROI)?
* Who is the most engaged target audience (Age & Gender)?
* Where can we cut costs to improve profitability?

## 📂 Data Source
* **Dataset:** Facebook Ads Performance Data
* **Source:** Kaggle (Provided by Future Interns)
* **Format:** CSV
* **Key Columns:** `Campaign ID`, `Ad ID`, `Impressions`, `Clicks`, `Spent`, `Total Conversions`, `Approved Conversions`.

## 🛠️ Tech Stack & Skills
* **Tool:** Microsoft Power BI Desktop
* **Data Cleaning:** Power Query Editor
* **Analysis:** DAX (Data Analysis Expressions)
* **Visualization:** KPI Cards, Clustered Bar Charts, Line Charts, Detailed Tables.

## 🔍 Steps Followed

### 1. Data Transformation (ETL)
* Imported raw CSV data into Power BI.
* Used **Power Query** to clean the data:
    * Fixed date format issues using "Using Locale" settings.
    * Removed "Error" rows caused by footer data/garbage values.
    * Changed data types (e.g., `Spent` to Currency, `Clicks` to Whole Number).

### 2. Data Modeling & DAX
* Created explicit **Measures** to calculate marketing KPIs using the `DIVIDE` function to handle division-by-zero errors:
    ```dax
    CTR = DIVIDE(SUM(Data[Clicks]), SUM(Data[Impressions]))
    Cost Per Conversion = DIVIDE(SUM(Data[Spent]), SUM(Data[Approved_Conversion]))
    ROI = DIVIDE([Estimated Revenue] - SUM(Data[Spent]), SUM(Data[Spent]))
    ```
* *Note: Revenue was simulated based on an Average Order Value (AOV) of $100.*

### 3. Dashboard Design
* **KPI Cards:** Displayed headline metrics (CTR, Total Spend, Total Conversions, ROI).
* **Demographic Analysis:** Clustered Bar Charts comparing performance by `Age` and `Gender`.
* **Deep Dive Table:** A detailed list of campaigns sorted by ROI to identify top performers.
* **Slicers:** Added interactivity for users to filter by `Campaign ID`, `Age`, and `Gender`.

## 💡 Key Insights
1.  **Top Performer:** **Campaign 916** is the undisputed winner, delivering a massive **1503% ROI** with an extremely low Cost Per Conversion ($6.24).
2.  **Ideal Audience:** **Females aged 30-34** are the most valuable demographic, driving the highest volume of impressions and engagement.
3.  **Budget Inefficiency:** **Campaign 1178** has the highest reach (Impressions) but is expensive ($43.85 per conversion). Budget should be reallocated from 1178 to 916.
4.  **Creative Fatigue:** The overall Click-Through Rate (CTR) is **0.01%**, suggesting that while reach is high, the ad creative (images/text) needs a refresh to improve engagement.

## 🚀 How to Run
1.  Download the `.pbix` file from this repository.
2.  Open it in **Microsoft Power BI Desktop**.
3.  Use the slicers on the right to drill down into specific age groups or campaign IDs.

---
*Created by Vibin Raj*

