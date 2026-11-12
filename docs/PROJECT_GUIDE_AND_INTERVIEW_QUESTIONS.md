# BoomBikes — Bike Rental Demand Modelling
## Project explanation and interview preparation

### Project summary

This project uses daily bike-sharing data to understand factors associated with rental demand and build a multiple linear regression model for total rentals. It explores seasonal and weather effects, prepares categorical variables and uses statistical diagnostics such as Variance Inflation Factor (VIF) to review predictor relationships.

**60-second interview pitch**

“I worked on a demand-modelling case study for BoomBikes, a bike-sharing business. I explored 730 daily observations with 16 variables, including season, calendar information and weather conditions. I used Python for data cleaning and exploratory analysis, encoded categorical variables and built a multiple linear regression model using scikit-learn and statsmodels. I examined coefficient interpretation and multicollinearity using VIF. For a production-style prediction, I would ensure that only information available before the rental day is used and would validate the final model using a held-out test set.”

### Business problem

Bike rental demand changes with season, calendar effects and weather. The business needs to understand these relationships to plan fleet availability, staffing and operating capacity.

### Dataset

The project summary describes 730 daily observations and 16 variables, including date, season, year, month, weekday, weather situation, temperature, feels-like temperature, humidity, wind speed, casual rentals, registered rentals and total rentals (`cnt`). The source `day.csv` is not currently in the repository.

### Modelling workflow

1. Load and inspect the dataset; check types, missingness and duplicates.
2. Explore demand distributions and relationships with candidate predictors.
3. Encode categorical variables such as season and weather situation.
4. Fit a multiple linear regression model.
5. Interpret coefficients and examine multicollinearity using VIF.
6. Validate on held-out data and inspect residual behaviour.

**Important target leakage point:** `cnt = casual + registered`. Do not use `casual` or `registered` as predictors when predicting total demand before the day occurs. Those components are only known after rentals have happened. This is an important modelling decision to be able to explain in an interview.

### Interview questions and suggested answers

**1. Why use linear regression for demand prediction?**  
It gives an interpretable baseline and estimates the relationship between demand and multiple explanatory variables. Its assumptions and predictive performance still need to be checked.

**2. What is multiple linear regression?**  
It models a continuous target as a linear combination of two or more predictors, with coefficients representing the expected change in the target for a one-unit change in a predictor, holding other predictors constant.

**3. Why encode categorical variables?**  
Most regression implementations expect numeric inputs. One-hot encoding represents categories with indicator columns without implying an artificial numeric ordering.

**4. What is multicollinearity?**  
It occurs when predictors are strongly correlated. It can make coefficient estimates unstable and harder to interpret, even if overall prediction remains acceptable.

**5. What is VIF?**  
Variance Inflation Factor measures how much the variance of a coefficient is inflated because of linear relationships with other predictors. High VIF values flag potential multicollinearity.

**6. What is the difference between R² and RMSE?**  
R² measures the proportion of target variance explained by the model relative to a baseline. RMSE measures typical prediction error in the target's units and penalises larger errors more strongly.

**7. Why inspect residuals?**  
Residual plots help identify non-linearity, heteroscedasticity, outliers and systematic patterns the model has not captured.

**8. What is heteroscedasticity?**  
It means the variance of residuals changes across fitted values or predictor ranges. It can affect statistical inference and may indicate that the model structure needs attention.

**9. Why split data into training and test sets?**  
The model is fitted on training data and evaluated on data not used for fitting. This provides an estimate of how well it generalises to unseen observations.

**10. What is target leakage in this project?**  
The target `cnt` is the sum of casual and registered rentals. Using either component to predict `cnt` would leak direct information about the target and would not represent a real forecast made in advance.

**11. How would you improve the model?**  
I would use time-aware validation, investigate non-linear effects and interactions, test regularised regression or tree-based models, and compare performance against a simple seasonal baseline.

**12. What business decisions could the model support?**  
It could inform fleet availability, staffing and operating plans. Predictions should be evaluated with an error tolerance that makes sense for the cost of over- or under-estimating demand.

### Limitations to be ready to discuss

- The raw `day.csv` file is not included in the repository.
- The existing README does not state a verified final test score.
- The final model should exclude target-derived variables such as `casual` and `registered`.
- A random split may not reflect the forecasting use case; time-aware validation is more appropriate.

### Resume bullet

Developed a Python-based bike rental demand modelling case study, using exploratory analysis, categorical encoding, multiple linear regression and VIF diagnostics to study seasonal and weather-related demand drivers.

### Files

- [Notebook](../Untitled3.ipynb)
- [Presentation](../Presentation.pdf)
