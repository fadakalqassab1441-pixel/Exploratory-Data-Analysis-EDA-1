Dataset Description: Walmart Sales
This dataset provides a detailed historical record of sales from several Walmart stores, along with various economic and environmental factors. It is designed to help analysts and data scientists understand the drivers behind retail performance and develop predictive models for future sales.
Dataset Source
The dataset is a classic retail analysis dataset commonly sourced from Kaggle (Walmart Recruiting - Store Sales Forecasting). It covers sales data for 45 Walmart stores across various regions over the period of 2010 to 2012.
Dataset Scale
•	Number of Rows: 6,435
•	Number of Columns: 8
Feature Descriptions
The dataset includes the following features, providing both categorical, temporal, and numeric data:
Feature	Description
Store	The unique identifier (ID) for each of the 45 Walmart stores.
Date	The specific week of the sales record (Format: DD-MM-YYYY).
Weekly_Sales	The total sales for the given store during that specific week.
Holiday_Flag	A binary indicator (1 = Holiday week, 0 = Non-holiday week).
Temperature	The average temperature in the region during the week of the sale.
Fuel_Price	The average cost of fuel in the region during the week.
CPI	The Consumer Price Index, a measure of inflation and cost of living.
Unemployment	The prevailing unemployment rate in the region during that week.

Purpose of the Dataset
The primary purpose of using this dataset is to perform Exploratory Data Analysis (EDA) and Predictive Modeling to:
1.	Identify Seasonality: Determine how holidays (Super Bowl, Labor Day, Thanksgiving, Christmas) impact revenue.
2.	Economic Correlation: Evaluate if macro-economic factors like inflation (CPI) or fuel prices have a measurable effect on consumer spending.
3.	Store Benchmarking: Compare the performance of different store locations to identify top-performing units.
4.	Forecasting: Build regression or time-series models to predict future weekly sales based on historical trends and external factors.

