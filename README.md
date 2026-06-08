# Walmart Sales Analysis & Forecasting

This repository contains a comprehensive data science project focused on conducting Exploratory Data Analysis (EDA), data preprocessing, and predictive modeling using historical retail data from Walmart. 

## Dataset Description
The dataset provides a detailed historical record of sales from multiple Walmart stores paired with various economic and environmental indicators. It serves as a benchmark for understanding the underlying drivers behind retail performance and establishing reliable workflows for future sales forecasting.

### Dataset Source & Scale
* **Source:** Sourced from the classic Kaggle competition: *Walmart Recruiting - Store Sales Forecasting*.
* **Temporal Coverage:** Weekly sales records for 45 distinct Walmart stores across various regions from 2010 to 2012.
* **Scale:** 6,435 rows × 8 columns.

---

## Feature Descriptions

| Feature Name | Data Type | Description |
| :--- | :--- | :--- |
| **Store** | Categorical / Int | The unique identifier (ID) for each of the 45 Walmart stores. |
| **Date** | Temporal / String | The specific week of the sales record (Format: DD-MM-YYYY). |
| **Weekly_Sales** | Numeric / Float | The total sales recorded for the given store during that specific week. |
| **Holiday_Flag** | Binary / Int | Indicator for special events (1 = Holiday week, 0 = Non-holiday week). |
| **Temperature** | Numeric / Float | The average temperature in the region during the week of the sale (in °F). |
| **Fuel_Price** | Numeric / Float | The average cost of fuel in the region during that specific week. |
| **CPI** | Numeric / Float | The Consumer Price Index, measuring inflation and regional cost of living. |
| **Unemployment** | Numeric / Float | The prevailing regional unemployment rate during that week. |

---

## Project Purpose & Objectives
The primary purpose of this project is to leverage advanced EDA and Predictive Modeling to solve key retail challenges:
1. **Identify Seasonality:** Determine exactly how major holiday windows (Super Bowl, Labor Day, Thanksgiving, Christmas) impact revenue spikes.
2. **Economic Correlation:** Evaluate whether macroeconomic indices like inflation (CPI) or fuel prices exert a measurable effect on regional consumer spending.
3. **Store Benchmarking:** Contrast and compare operational performance across all 45 store locations to isolate top-performing units and underperforming branches.
4. **Sales Forecasting:** Build robust regression or time-series machine learning models to predict future weekly sales based on historical trends, seasonal markers, and shifting economic conditions.

---

## Preprocessing Pipeline

To prepare this dataset for machine learning models, a 5-step data engineering pipeline was established:

### 1. Data Quality Assessment
Programmatic evaluation of structural anomalies, incorrect formats, and scale disparities using automated scripts. Key findings included identifying that the `Date` column was read as an arbitrary string object rather than a standardized datetime metric, and detecting massive operational scale variations between target labels (`Weekly_Sales`) and economic traits (`Fuel_Price`).

### 2. Missing Value Imputation
To account for potential missing matrix inputs while maintaining structural integrity, **Median Imputation** was chosen. Retailing financial records often experience heavily skewed distributions due to holiday spikes; substituting missing fields with the median protects the central tendency from being pulled artificially upward by high-value outliers.

### 3. Outlier Detection & Handling
Extreme anomalies and retail spikes were managed using the **Interquartile Range (IQR)** method. Fences were calculated at:
$$\text{Lower Fence} = Q1 - 1.5 \times IQR$$
$$\text{Upper Fence} = Q3 + 1.5 \times IQR$$
Data points scaling beyond these boundaries were systematically isolated to stabilize subsequent model gradient steps.

### 4. Feature Normalization
To prevent features with huge absolute values (`Weekly_Sales`) from dominating distance calculations over microscopic units (`Fuel_Price`), features were normalized using dual techniques:
* **Min-Max Scaling:** Compresses elements precisely between a `[0, 1]` boundary to retain relative mathematical spacing.
* **Z-Score Standardization:** Re-centers variables around a Mean of `0` and a Standard Deviation of `1`, which is ideal for optimization algorithms.

### 5. Principal Component Analysis (PCA)
Applied PCA across the continuous feature matrix to evaluate dimensionality reduction. By examining the `explained_variance_ratio_`, the project quantifies how much total informational variance is retained across orthogonal principal component vectors, ensuring low-dimensional feature projections do not sacrifice critical operational metrics.

---

## Technical Stack
* **Language:** Python 3.x
* **Libraries Used:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
