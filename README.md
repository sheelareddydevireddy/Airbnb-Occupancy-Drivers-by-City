# Airbnb-Occupancy-Drivers-by-City
Analyzing what drives Airbnb occupancy rates across US cities using R (EDA), Python (Lasso, Random Forest), and Tableau.

## Overview
Analyzing what drives Airbnb occupancy rates across US cities using machine learning and statistical modeling.

## Cities Analyzed
San Fransisco, New York, Kissimmee

## Tools
- **R** - Exploratory Data Analysis
- **Python** - Feature selection and modeling
- **Tableau** -  Visualization

## Approach
1. EDA in R to understand the data, missing values, and relationships with target (occupancy)
2. Lasso regression for feature selection → Linear Regression
3. Boruta for feature selection → Random Forest (looking beyond linear relationships)
4. Diagnosed and fixed RF overfitting on small dataset (300 rows)

## Results 
![Occupancy Drivers by City](tableau/your_image_name.png)
