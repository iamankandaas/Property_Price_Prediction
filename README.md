# Property Price Prediction Project

## Overview
This project focuses on predicting median house values in California districts using district-level features. It employs **Simple Linear Regression** and **Multiple Linear Regression** to identify key factors influencing housing prices and to develop predictive models. The project also demonstrates various data preprocessing and feature engineering techniques to improve model performance.

---

## Project Workflow

### 1. Data Preprocessing
- Handled missing values in the `total_bedrooms` column by imputing the median.
- Created new composite features to reduce multicollinearity:
  - `rooms_per_household` = `total_rooms` / `households`
  - `bedrooms_per_room` = `total_bedrooms` / `total_rooms`
  - `population_per_household` = `population` / `households`
- Dropped highly correlated features: `total_rooms`, `total_bedrooms`, `population`, and `households`.
- Encoded the categorical feature `ocean_proximity` using one-hot encoding.
- Normalized numerical features using MinMaxScaler for consistent input ranges.
- Added polynomial features (squared and cubed terms) for `median_income`.
- Introduced interaction terms, e.g., `median_income * housing_median_age`.
- Applied log transformations to stabilize variance in skewed features.

---

### 2. Modeling

#### Simple Linear Regression
- **Predictor**: `median_income`
- **Target**: `median_house_value`
- **Performance**:
  - RMSE: 0.1736
  - R²: 0.4589

#### Multiple Linear Regression
- **Predictors**: All features after preprocessing.
- **Target**: `median_house_value`
- **Performance**:
  - RMSE: 0.01697
  - R²: 0.9948

---

## Technologies Used
- **Programming Language**: Python
- **Libraries**:
  - Data Analysis: `pandas`, `numpy`
  - Visualization: `seaborn`, `matplotlib`
  - Machine Learning: `scikit-learn`
  - Preprocessing: `MinMaxScaler`

---

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/property-price-prediction.git
