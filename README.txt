# What Drives the Price of a Car?

## Project Overview

The goal of this project is to understand which vehicle characteristics are associated with the price of used vehicles. Using a dataset of used vehicle listings, I performed exploratory data analysis and built regression models to identify relationships between vehicle characteristics and price.

The results of this analysis are intended to help a used car dealership make more informed decisions about vehicle inventory and pricing.

## Dataset

The dataset contains approximately 426,000 used vehicle listings and includes information such as:

- Price
- Manufacturer and model
- Model year
- Odometer mileage
- Vehicle condition
- Fuel type
- Transmission
- Drive type
- Title status
- Vehicle type
- Paint color
- Region and state

Before modeling, I cleaned the data by removing unrealistic values, handling missing categorical values, removing features with excessive missing data, and creating additional features such as vehicle age and log-transformed odometer mileage.

## Analysis and Modeling

I followed the CRISP-DM framework throughout the project:

1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation
6. Deployment

Exploratory data analysis was used to investigate vehicle prices, mileage, age, missing values, and categorical vehicle characteristics.

I then compared several regression approaches, including:

- Multiple Linear Regression
- Linear Regression with log-transformed odometer mileage
- Ridge Regression
- Lasso Regression
- Ridge Regression including the specific vehicle model

Cross-validation was used to compare model performance, and GridSearchCV was used to tune the Ridge regularization parameter.

## Model Performance

The final model was a Ridge regression model that included specific vehicle model information while grouping infrequent categories during one-hot encoding.

The final model achieved approximately:

- **Cross-Validation MAE:** $6,501
- **Test MAE:** $6,525
- **Test RMSE:** $10,771
- **Test R²:** 0.521

MAE was used as the primary evaluation metric because it provides an easily interpretable estimate of the model's average prediction error in dollars.

## Key Findings

The analysis suggests that several vehicle characteristics are associated with used vehicle prices:

- **Vehicle age and mileage are important pricing factors.** Older vehicles and vehicles with greater mileage generally have lower prices.
- **Manufacturer and specific vehicle model contain important pricing information.** Adding the specific vehicle model improved predictive performance compared with models that only included the manufacturer.
- **Transforming odometer mileage improved model performance.** Using log-transformed mileage produced better cross-validation results than using raw mileage.
- **Title status and vehicle condition are associated with price**, although these relationships should be interpreted alongside other vehicle characteristics.
- Vehicle price cannot be explained by any single characteristic. Multiple characteristics contribute to the differences observed in used vehicle prices.

These relationships should be interpreted as associations rather than evidence that a particular characteristic directly causes a change in vehicle price.

## Recommendations

Based on the analysis, a used car dealership should consider:

- Using vehicle age and mileage as important factors when evaluating inventory and setting prices.
- Considering the specific make and model rather than relying only on manufacturer when comparing vehicles.
- Accounting for title status and vehicle condition when evaluating comparable listings.
- Using predictive models as a pricing support tool rather than as the sole basis for pricing decisions.

The final model has a test MAE of approximately $6,525, meaning predictions can still differ substantially from actual listing prices. Dealership experience and additional vehicle-specific information should therefore be considered alongside model estimates.

## Next Steps

Future analysis could incorporate additional information that was not available in this dataset, including:

- Mechanical and maintenance history
- Optional equipment and trim level
- Accident history
- Local market demand
- More recent vehicle listings

The model could also be evaluated on newer listings to determine whether the relationships identified in this dataset remain consistent over time.

## Repository Contents

- `Practical Application Assignment 2 - Final Draft.ipynb` — Complete Jupyter notebook containing data exploration, preparation, modeling, evaluation, and recommendations.
- `README.md` — Project overview and summary of findings.

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Full Analysis

The complete analysis, code, visualizations, model development, and evaluation can be found in the Jupyter notebook included in this repository.