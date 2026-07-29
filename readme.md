# bigmart-sales-forecasting-ml
An end-to-end data analytics and machine learning project for forecasting sales in the Big Mart retail system using Python, XGBoost, feature engineering.
# 🛒 Big Mart Sales Forecasting using Machine Learning

## Overview

This project develops a Machine Learning pipeline to predict product sales at Big Mart stores based on product characteristics and store information.

The project covers the complete data science workflow, including:

- Data exploration (EDA)
- Data preprocessing
- Feature engineering
- Model development
- Hyperparameter tuning
- Model evaluation
- Business insights

The objective is to identify the best predictive model while extracting actionable insights to support retail decision-making.

---

## Dataset

Dataset: Big Mart Sales Prediction

Target variable:

- Item_Outlet_Sales

Main features include:

- Product information
- Product visibility
- Product weight
- Fat content
- Outlet type
- Outlet size
- Outlet location
- Outlet establishment year
- Maximum retail price (MRP)

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

- Dataset overview
- Missing value analysis
- Data quality inspection

### 2. Data Preprocessing

- Missing value imputation
- Data cleaning
- Feature standardization
- Categorical normalization
- Visibility correction
- Outlet age generation

### 3. Feature Engineering

Additional features created:

- Item Type Group
- Outlet Age
- MRP × Visibility interaction
- Outlet Age × Outlet Type interaction

### 4. Feature Encoding

- One-Hot Encoding
- Numerical feature selection

### 5. Machine Learning Models

Models implemented:

- Linear Regression
- Lasso Regression
- Random Forest Regressor
- XGBoost Regressor

Hyperparameter tuning:

- GridSearchCV
- RandomizedSearchCV

### 6. Model Evaluation

Evaluation metrics:

- MAE
- RMSE
- R² Score
- Cross Validation

### 7. Feature Importance

Feature importance analysis using XGBoost.

### 8. Business Insights

Translate model findings into retail recommendations.

---

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Plotly
- Scikit-learn
- XGBoost

---

## Repository Structure

BigMart-Sales-Forecasting/
│
├── data/
│ ├── train.csv
│
├── notebooks/
│ └── BigMart_Sales_Forecasting.ipynb
│
├── images/
│ ├── feature_importance.png
│ ├── prediction_result.png
│
├── README.md
└── requirements.txt

---

## Key Results

- Developed four regression models.
- Applied feature engineering to improve predictive performance.
- Tuned model parameters using cross-validation.
- Identified the most influential sales drivers.
- Generated business recommendations based on model interpretation.

---

## Future Improvements

- LightGBM
- CatBoost
- SHAP Explainability
- Time-series forecasting
- Model deployment with Streamlit

---

## Author

Pham Phuong Thy
