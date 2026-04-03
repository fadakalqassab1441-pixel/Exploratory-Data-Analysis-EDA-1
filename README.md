# 🛒 Walmart Sales Data Analysis

## 📌 Project Overview
This project focuses on a detailed historical record of sales from 45 Walmart stores, analyzed alongside various economic and environmental factors. The goal is to understand the drivers behind retail performance and provide insights for predictive modeling of future sales.

## 📊 Dataset Description
* **Source:** Walmart Recruiting - Store Sales Forecasting (Kaggle)
* **Time Period:** 2010 – 2012
* **Scale:** 6,435 rows × 8 columns

### **Feature Breakdown**
| Feature | Description |
| :--- | :--- |
| **Store** | Unique identifier (ID) for each of the 45 Walmart stores. |
| **Date** | The specific week of the sales record (DD-MM-YYYY). |
| **Weekly_Sales** | Total sales for the given store during that specific week. |
| **Holiday_Flag** | Binary indicator (1 = Holiday week, 0 = Non-holiday week). |
| **Temperature** | Average temperature in the region during the week of the sale. |
| **Fuel_Price** | Average cost of fuel in the region during the week. |
| **CPI** | Consumer Price Index (measure of inflation/cost of living). |
| **Unemployment** | Prevailing unemployment rate in the region. |

---

## 🎯 Project Purpose
The primary objective of this analysis is to perform **Exploratory Data Analysis (EDA)** and **Predictive Modeling** to achieve the following:

1.  **Identify Seasonality:** Quantify how major holidays (Super Bowl, Labor Day, Thanksgiving, Christmas) impact revenue.
2.  **Economic Correlation:** Evaluate if macro-economic factors like inflation (CPI) or fuel prices have a measurable effect on consumer spending.
3.  **Store Benchmarking:** Compare the performance of different store locations to identify top-performing units.
4.  **Forecasting:** Establish a foundation for building regression models to predict future weekly sales.

---

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** Pandas, Matplotlib, Seaborn, NumPy
