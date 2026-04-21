# Airbnb-Occupancy-Drivers-by-City
Analyzing what drives Airbnb occupancy rates across US cities using R (EDA), Python (Lasso, Random Forest), and Tableau.

## Overview
Analyzing what drives Airbnb occupancy rates across US cities using machine learning and statistical modeling.

***Summary**: Occupancy was partially predictable across all three cities. Strongest drivers differed by market, with host credibility and review activity appearing most consistently across locations.*

## Cities Analyzed
San Francisco, New York, Kissimmee

## Tools
- **R** - Exploratory Data Analysis
- **Python** - Feature selection and modeling
- **Tableau** -  Visualization

## Approach
1. EDA in R to understand the data, missing values, and relationships with target (occupancy)
2. Lasso regression for feature selection → Linear Regression
3. Boruta for feature selection → Random Forest (looking beyond linear relationships)
4. Diagnosed and fixed RF overfitting on small dataset (300 rows)

## Results by City 
| City | Model | Test R² |
|------|-------|---------|
| San Francisco | Linear Regression (Lasso) | 0.21 |
| San Francisco | Random Forest (Boruta) | 0.23 |
| New York | Linear Regression (Lasso) | 0.47 |
| New York | Random Forest (Boruta) | 0.60 |
| Nashville | Linear Regression (Lasso) | 0.58 |
| Nashville | Random Forest (Boruta) | 0.58 |

## Key Findings
- **San Francisco** - Only 4 features selected by Boruta. Lower model performance overall - data size may be a limiting factor
- **New York** - Best RF performance (0.60), length of stay features were highly predictive
- **Kissimmee** - LR and RF nearly identical (0.58), more features in LR gave no additional predictive power


## Features consistently driving occupancy across all cities
- `superhost` - appeared in all three LASSO feature selections, suggesting host credibility is a recurring predictor of occupancy.
- `num_reviews` - universal signal
- `listing_type` - Room type matters 

## What varies by city
- New York uniquely selected `length_of_stay` metrics → suggesting booking duration patterns are more informative in this market.
- San Francisco driven purely by credential and location-driven signals (longitude, reviews, ratings)
- Kissimmee, simpler feature structure, less benefit from extra complexity

## Does superhost status matter more in New York or San Francisco?
Permutation importance for superhost was similar in both New York City and San Francisco, with a slightly higher importance in NYC.

## Limitations
- Each city had only ~300 listings, limiting stability
- One-hot encoded categorical variables can make feature selection and linear model estimates less stable
- Selected predictors are associated with occupancy, not proven to cause higher or lower occupancy
- Feature importance does not imply causation

## Data Source
https://www.airroi.com/
