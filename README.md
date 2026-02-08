# E-commerce Sales Prediction

## Project Overview

This project focuses on predicting **Units Sold** for e-commerce products using historical sales, pricing, discount, customer segment, and marketing spend data. Accurate sales prediction can help businesses improve inventory planning, optimize marketing budgets, and make data-driven pricing decisions.

The problem is framed as a **supervised regression task**, and multiple models are evaluated using **cross validated Mean Absolute Error (MAE)** to ensure robust and fair comparison.


## Business Problem

E-commerce businesses often struggle with inaccurate demand forecasts, leading to overstocking, stockouts, and inefficient marketing spend.

**Business question:**

> *Given product, pricing, discount, customer segment, and marketing information, how many units are likely to be sold?*

**Key stakeholders:**

* Marketing teams (campaign planning and ROI estimation)
* Operations & inventory planners
* Business analysts


## Dataset

The dataset used in this project is publicly available on Kaggle:

**E-commerce Sales Prediction Dataset**
[https://www.kaggle.com/datasets/nevildhinoja/e-commerce-sales-prediction-dataset](https://www.kaggle.com/datasets/nevildhinoja/e-commerce-sales-prediction-dataset)

### Key Features

* **Date** – transaction date
* **Product_Category** – category of the product
* **Price** – product price
* **Discount** – discount applied
* **Customer_Segment** – customer type
* **Marketing_Spend** – marketing expenditure
* **Units_Sold (Target)** – number of units sold

The dataset contains approximately 1,000 observations.


## Methodology

The project follows a standard data science workflow:

1. **Data Wrangling & Feature Engineering**

   * Date parsing and feature extraction (month, day, weekday)
   * Handling missing values
   * One hot encoding of categorical variables
   * Feature scaling where appropriate

2. **Exploratory Data Analysis (EDA)**

   * Distribution analysis of sales
   * Relationship between discounts, marketing spend, and units sold
   * Category level sales trends

3. **Modeling**

   * Baseline model (mean predictor)
   * Linear Regression
   * Random Forest Regressor

   Hyperparameter tuning is performed using **GridSearchCV**.


## Evaluation Metrics

The primary evaluation metric is **cross validated Mean Absolute Error (MAE)**.

**Why MAE?**

* Interpretable in business terms (average error in units sold)
* Less sensitive to outliers than RMSE
* Cross-validation provides a stable estimate of model performance

RMSE and R² were explored but not emphasized, as MAE was used consistently for model comparison.


## Results Summary

* The baseline model provides a reference level of performance
* Linear Regression and Random Forest models are evaluated against the baseline
* Models are compared using mean and standard deviation of cross validated MAE

A detailed summary of model performance can be found in the **Model Metrics** file.


## Limitations & Future Work

* The dataset size is relatively small, which may limit generalization
* External factors such as seasonality and competitor actions are not included

**Future improvements:**

* Incorporating external or time-series data
* Exploring Gradient Boosting models
* Using time aware validation strategies
