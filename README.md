# Mobile Devices Project For Data Science with AI II

# Mobile Devices Pricing Prediction

A data science project for STA 4365 (Data Science & AI II) that uses machine learning techniques to predict mobile phone prices based on hardware specifications.

## Project Overview

The dataset, sourced from [Kaggle](https://www.kaggle.com/datasets/abdulmalik1518/mobiles-dataset-2025/data), includes hardware and software features for over 900 mobile devices from major brands like Apple, Samsung, Google, and more. Our goal was to build predictive models that estimate launch prices using features such as RAM, storage, battery capacity, screen size, and more.

## Features Used

After extensive preprocessing and feature selection, the final predictors used were:

- **Battery Capacity (mAh)**
- **Weight (g)**
- **Company**
- **Storage (GB)**
- **RAM (GB)**
- **Screen Size (inches)**
- **Front Camera (MP)**

## Data Preprocessing

- Removed non-USD pricing entries to avoid currency collinearity.
- Converted units and extracted numeric values (e.g., from "128GB" to `128`).
- Created dummy variables for companies.
- Removed features with low importance (e.g., `Back Camera`, `Launch Year`).
- Applied log transformation to reduce skewness in price.
- Standardized predictors for distance-based modeling.

## Models Applied

### 1. **Linear Regression**
- **Base Model R²**: 0.32
- **Log-Transformed Model R²**: 0.49

### 2. **K-Nearest Neighbors Regression**
- **Best Model R²**: **0.85**
- **MAE**: 87.66
- **MSE**: 20,183.56
- Tuned using GridSearchCV with:
  - `k = 5`
  - Manhattan Distance
  - Distance-based weighting

## Findings

- **Top predictors**: Storage, RAM, Weight
- **Most effective model**: KNN with log-transformed prices and scaled predictors
- Log-transformation significantly improved model performance and reduced variance
- Useful for both consumers (choosing value-for-money devices) and manufacturers (price modeling)
