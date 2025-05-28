# 🚲 Bike Sharing Demand Prediction - Multiple Linear Regression

## 📌 Project Overview

This project involves building a **Multiple Linear Regression** model to predict the daily demand for shared bikes in the American market. The business problem is modeled for **BoomBikes**, a U.S.-based bike-sharing service provider, which aims to understand the factors affecting bike demand and adjust its business strategy accordingly after the COVID-19 lockdown.

---

## 🎯 Problem Statement

**BoomBikes** has seen a significant decline in revenue due to the COVID-19 pandemic. As the economy begins to recover, the company wants to forecast bike rental demand to prepare for market resurgence.

The objectives are:
- To identify the key variables influencing bike demand.
- To build a regression model that can accurately predict total rentals (`cnt`).
- To provide insights that guide business strategy and resource allocation post-lockdown.

---

## 🧾 Dataset Description

- The dataset contains daily records of bike rentals, along with weather conditions and temporal features.
- Key variables include:
  - **`cnt`**: Total bike rentals (target variable)
  - **`casual`**, **`registered`**: Number of casual and registered rentals
  - **`season`**, **`weathersit`**, **`mnth`**, **`weekday`**, etc.: Categorical features
  - **`temp`**, **`atemp`**, **`hum`**, **`windspeed`**: Continuous variables

> **Note**: Variables such as `season` and `weathersit`, although numeric, are actually **categorical** and should be treated accordingly.

---

## 💡 Business Goal

The regression model will:
- Help **BoomBikes** understand the dynamics of rental demand
- Provide a predictive framework for estimating future demand
- Allow management to prepare resources, promotions, and infrastructure to meet expected demand levels

---

## 🧹 Data Preparation

- Converted nominal categorical variables (`season`, `weathersit`, `mnth`, `weekday`) into string labels
- Created **dummy variables** to handle categorical data
- Retained binary variables like `yr` (year: 0 for 2018, 1 for 2019) due to their potential importance
- Dropped variables like `instant`, `dteday`, `casual`, and `registered` to avoid data leakage

---

## 🧠 Model Building

- Built a **Multiple Linear Regression** model with `cnt` (total rentals) as the target
- Used **Recursive Feature Elimination (RFE)** and **p-values** for feature selection
- Performed **residual analysis** to validate linear regression assumptions
- Evaluated model performance on a test set using **R-squared**:

```python
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
