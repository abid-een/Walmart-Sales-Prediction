# Walmart Sales Prediction Project

## Table of Contents
1. [Introduction](#introduction)
2. [Problem Statement](#problem-statement)
3. [Project Objectives](#project-objectives)
4. [Data Description](#data-description)
5. [Data Preprocessing](#data-preprocessing)
6. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
7. [Modeling and Forecasting](#modeling-and-forecasting)
8. [Results and Evaluation](#results-and-evaluation)
9. [How to Run the Notebook](#how-to-run-the-notebook)
10. [Future Work](#future-work)
11. [Acknowledgements](#acknowledgements)
12. [License](#license)

---

## Introduction

This repository contains a single Jupyter Notebook file, **Capstone_Project_Walmart.ipynb**, which encompasses the entire Walmart Sales Prediction project. The notebook includes data preprocessing, exploratory data analysis, modeling using the SARIMA framework, forecasting, and model evaluation. The project aims to forecast weekly sales for 45 Walmart stores for the next 12 weeks, providing valuable insights for inventory and resource planning.

---

## Problem Statement

Retail chains with multiple outlets face challenges in managing inventory due to mismatches between supply and demand. This project tackles the problem by analyzing historical sales data and predicting future weekly sales, aiding effective inventory management and decision-making.

---

## Project Objectives

- **Sales Forecasting:** Forecast weekly sales for each of the 45 stores over the next 12 weeks.
- **Insight Generation:** Analyze the impact of factors such as holidays, temperature, fuel price, CPI, and unemployment on sales.
- **Actionable Recommendations:** Identify trends and provide insights to optimize inventory levels and improve operational efficiency.
- **Model Evaluation:** Validate the forecasting model using metrics such as MAE, MSE, and RMSE.

---

## Data Description

The dataset (Walmart.csv) includes 6,435 rows and 8 columns with the following features:

- **Store:** Store number (1–45)
- **Date:** Week of sales (formatted as DD-MM-YYYY)
- **Weekly_Sales:** Sales figures for the corresponding week
- **Holiday_Flag:** Indicator of whether the week includes a holiday (0 or 1)
- **Temperature:** Temperature on the day of the sale
- **Fuel_Price:** Regional fuel price
- **CPI:** Consumer Price Index
- **Unemployment:** Unemployment rate

---

## Data Preprocessing

Key preprocessing steps in the notebook include:

- **Missing Value Check:** Confirm that there are no missing values.
- **Date Conversion:** Convert the 'Date' column to datetime format.
- **Feature Engineering:** Create additional features such as Day_of_Week, Month, and Year.
- **Outlier Detection:** Identify any outliers in numerical features.
- **Scaling (Optional):** Normalize numerical features if needed.

---

## Exploratory Data Analysis (EDA)

The notebook performs an in-depth exploratory analysis by:

- **Descriptive Statistics:** Providing summary statistics for each feature.
- **Visualizations:**
    - Bar plots showing total sales per store
    - Line and scatter plots to identify trends and relationships
    - Heatmaps and pair plots for correlation analysis
- **Seasonal Decomposition:** Using additive and multiplicative models to reveal seasonal trends and residuals.
- **Insights:**
    - Identification of sales patterns during holidays
    - Analysis of how external factors affect sales

---

## Modeling and Forecasting

The forecasting approach is based on the **SARIMA (Seasonal ARIMA)** model, which is well-suited for time-series data with seasonal trends.

### Key Steps:
1. **Stationarity Check:**  
    - Performed using the Augmented Dickey-Fuller test after differencing.
2. **Model Selection:**  
    - Utilized auto_arima to determine optimal SARIMA parameters.
3. **Model Training:**  
    - Fit the SARIMA model on the training set.
4. **Prediction and Forecasting:**  
    - Generate predictions on the test set and forecast weekly sales for the next 12 weeks.
5. **Evaluation:**  
    - Metrics such as MAE, MSE, and RMSE are used to assess model performance.

---

## Results and Evaluation

- **Forecast Accuracy:**
    - **MAE:** Approximately 43,867
    - **MSE:** Around 3.25 × 10^9
    - **RMSE:** Approximately 57,022
- **Key Insights:**
    - Clear seasonal trends and sales spikes during holidays.
    - Variation in sensitivity to external factors such as unemployment and CPI.
    - The SARIMA model effectively captures the underlying sales patterns, providing reliable forecasts.

---

## How to Run the Notebook

1. **Clone the Repository:**

    bash
    git clone https://github.com/abid-een/Walmart-Sales-Prediction.git
    cd Walmart-Sales-Prediction

2. **Set Up a Virtual Environment (Optional but Recommended):**

    bash
    python -m venv env
    source env/bin/activate  # On Windows: env\Scripts\activate

3. **Install Dependencies:**

    bash
    pip install -r requirements.txt

    (Ensure that your requirements.txt includes necessary packages such as pandas, numpy, matplotlib, seaborn, statsmodels, and pmdarima.)

4. **Launch the Jupyter Notebook:**

    bash
    jupyter notebook Capstone_Project_Walmart.ipynb

---

## Future Work

- **Incorporate Exogenous Variables:** Extend the model using SARIMAX to include external factors (e.g., temperature, fuel price, CPI).
- **Extended Forecasting Horizon:** Explore forecasting beyond 12 weeks.
- **Real-Time Updates:** Implement dynamic forecasting as new data becomes available.
- **Inventory Optimization:** Integrate forecasting with inventory management systems for improved decision-making.

---

