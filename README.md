#  Number of Orders Prediction

This project aims to predict the **number of food delivery orders** using historical data. The task is treated as a regression problem where multiple features — mostly related to time and calendar — are used to forecast the number of orders placed on a given day.

The project includes **EDA**, **feature engineering**, and the training of two regression models: **Random Forest Regressor** and **LightGBM Regressor**.

---

##  Goal

Build a model that can predict the number of daily orders based on input features like:
- Date
- Holiday information
- Functioning Day status
- Derived features like day of the week and month

---

##  Tech Stack

| Tool / Library       | Usage                            |
|----------------------|----------------------------------|
| Python               | Scripting language               |
| Pandas, NumPy        | Data loading and manipulation    |
| Matplotlib, Seaborn  | Data visualization               |
| Scikit-learn         | Data preprocessing, metrics, RF  |
| LightGBM             | Gradient boosting regression     |
| Jupyter Notebook     | Interactive development          |

---

##  Workflow Overview

### ✅ 1. Data Preprocessing
- Converted `Date` column to datetime
- Extracted **day**, **month**, and **weekday** from date
- Applied **Label Encoding** to categorical variables (`Holiday`, `Functioning Day`)
- Dropped unused columns like `ID` and the original `Date`

### ✅ 2. Exploratory Data Analysis
- Visualized number of orders over time
- Compared orders based on holidays and weekdays
- Identified trends and seasonality using basic plots

### ✅ 3. Model Training
#### 🔹 Random Forest Regressor
- Trained using `sklearn.ensemble.RandomForestRegressor`
- Default parameters were used
- Performance evaluated using:
  - **R² Score**
  - **Mean Absolute Error (MAE)**
  - **Mean Squared Error (MSE)**

#### 🔹 LightGBM Regressor
- Trained using `lightgbm.LGBMRegressor`
- Also used default parameters (no tuning)
- Same metrics used for evaluation

> No advanced hyperparameter tuning or cross-validation was done.

---

##  Results

| Model              | R² Score | MAE    | MSE     |
|--------------------|----------|--------|---------|
| Random Forest      | ~0.94    | Low    | Low     |
| LightGBM           | ~0.93    | Low    | Slightly higher than RF |

- **Random Forest** slightly outperformed LightGBM on this dataset
- Both models performed well on the training data, but no testing on unseen data (like a holdout set) was done

---

##  What I Actually Learned

- How to extract datetime features from a column
- The value of simple visualizations in understanding temporal data
- The process of encoding categorical features
- Training and evaluating basic regression models
- Using LightGBM for the first time in a real use case
- Understanding what R², MAE, and MSE mean in the context of regression

---

##  Limitations

- No parameter tuning or optimization done for either model
- No feature scaling or selection applied
- Model performance is only evaluated on training data (not robust)
- Didn’t explore time-series models (despite the temporal nature of data)

---



: Suresh Jakhar