# BoomBikes — Bike Rental Demand Modelling

A regression case study exploring the factors associated with daily bike rental demand and how they can support operational planning.

**Tools:** Python · Pandas · NumPy · scikit-learn · statsmodels · Matplotlib · Seaborn

## Business question

How do seasonal, calendar and weather conditions relate to daily bike rentals, and how can a demand model support fleet and capacity planning?

## Dataset

The project summary describes 730 daily observations and 16 columns. Fields include date, season, year, month, weekday, weather situation, temperature, feels-like temperature, humidity, wind speed, casual rentals, registered rentals and total rentals (`cnt`).

The source `day.csv` is not currently listed in the repository, so a local copy is needed to reproduce the notebook from a fresh clone.

## Workflow

- Inspect data types, missing values and duplicates.
- Explore distributions and relationships between demand and explanatory variables.
- Encode categorical fields such as season and weather situation.
- Fit a multiple linear regression model using scikit-learn and/or statsmodels.
- Interpret coefficients and review multicollinearity using VIF.
- Evaluate performance on held-out data and inspect regression assumptions.

## Important modelling note

The target `cnt` is the sum of `casual` and `registered` rentals. Those two component fields must not be used as predictors when the objective is to predict total rentals before the day occurs; doing so would create target leakage. Use only features that would genuinely be available at prediction time.

The current README does not provide a verified final holdout score. No performance figure is claimed here.

## Repository contents

- `Untitled3.ipynb` — analysis notebook.
- `Presentation.pdf` — project presentation.

## Reproducibility

Obtain the original `day.csv`, place it at the input path expected in the notebook or update the path, then run the notebook in a Python environment with the libraries listed above.


## Author

**Eshwar Ramesh** · [GitHub](https://github.com/EshwarRamesh7) · [Portfolio](https://eshwarrameshportfolio.netlify.app) · [LinkedIn](https://www.linkedin.com/in/eshwar-ramesh-9a4652251)
