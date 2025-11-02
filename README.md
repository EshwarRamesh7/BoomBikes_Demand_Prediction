# BoomBikes_Demand_Prediction
Multiple Linear Regression model to predict bike rental demand for BoomBikes using Python. Includes data cleaning, EDA, feature analysis, and model interpretation.
# 🚴‍♂️ BoomBikes Demand Prediction — Multiple Linear Regression

## 📄 Project Overview
This project explores factors influencing daily bike demand for **BoomBikes**, a US-based bike-sharing service.  
The goal is to analyze how environmental and seasonal variables affect total rentals and to build a **Multiple Linear Regression** model to predict future demand.

---

## 🎯 Objective
- Identify key variables influencing daily bike rentals.  
- Build a regression model to estimate total demand (`cnt`) using available features.  
- Provide insights to guide business decisions post-pandemic.

---

## 🧩 Dataset Description
The dataset (`day.csv`) contains daily records of bike rentals with 16 features, including:

- **Date and Season Information:** `dteday`, `season`, `yr`, `mnth`, `weekday`  
- **Weather Conditions:** `weathersit`, `temp`, `atemp`, `hum`, `windspeed`  
- **User Types:** `casual`, `registered`  
- **Target Variable:** `cnt` — total rentals per day  

---

## ⚙️ Tools and Libraries Used
- **Language:** Python  
- **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn, statsmodels  

---

## 🧹 Data Preparation
- Imported and inspected dataset using pandas (`df.info()`, `df.head()`).  
- Checked data types and null values.  
- Converted categorical variables like `season` and `weathersit` into dummy variables.  
- Explored correlations and feature relationships for modeling.

---

## 📈 Model Building
- Implemented a **Multiple Linear Regression** model using scikit-learn and statsmodels.  
- Calculated model coefficients to understand the impact of each predictor.  
- Checked multicollinearity using **Variance Inflation Factor (VIF)**.  

---

## 🔍 Key Findings (from current analysis)
- Dataset contains **730 observations** with **16 columns**.  
- Preliminary analysis shows **temperature**, **season**, and **year** significantly affect total demand.  
- Model coefficients indicate the relative influence of independent variables on total rentals.

---

## 📊 Next Steps
- Perform residual analysis and validate model assumptions.  
- Compute **R² score** and finalize model evaluation.  
- Add visualizations for feature importance and residuals.

---



## 📁 Project Structure
