# Supermarket Sales Analysis

## Overview

This project analyses transaction-level supermarket sales data to investigate customer purchasing behaviour and identify characteristics associated with high-quantity transactions.

The analysis follows a commercial data analytics perspective, focusing on product behaviour, customer characteristics, payment methods, and purchasing time.

The project includes data preprocessing, feature engineering, exploratory data analysis, visualisation, machine learning, and model evaluation.

## Dataset

**Dataset:** Supermarket Sales

The dataset contains **1,000 supermarket transactions** recorded across three branches.

Key variables include:

* Branch
* City
* Customer type
* Customer gender
* Product line
* Unit cost
* Quantity
* Payment method
* Customer rating
* Transaction date and time
* Revenue and other financial variables

## Data Preprocessing

The dataset was checked for data quality before modelling.

The preprocessing included:

* Checking for missing values
* Checking for duplicate records
* Converting the transaction date into datetime format
* Combining date and time into a datetime variable
* Creating temporal features:

  * Month
  * Day of week
  * Hour
* Removing variables that were constant or unsuitable for prediction
* Excluding financial variables derived directly from the target or related calculations to avoid data leakage
* Encoding categorical variables using one-hot encoding

## Machine Learning Problem

The analysis investigates:

> **Can customer, product and purchasing-time characteristics identify high-quantity transactions?**

Transactions were divided into two groups:

* `0` = Low quantity: 1–5 units
* `1` = High quantity: 6–10 units

The target was almost perfectly balanced:

* Low quantity: 504 transactions (50.4%)
* High quantity: 496 transactions (49.6%)

## Machine Learning Model

### Random Forest Classifier

A Random Forest Classifier was applied to identify whether transaction-level characteristics could distinguish high-quantity from low-quantity purchases.

Predictors included:

* Branch
* City
* Customer type
* Gender
* Product line
* Payment method
* Unit cost
* Customer rating
* Month
* Day of week
* Hour

Categorical variables were one-hot encoded using a Scikit-learn preprocessing pipeline.

## Model Evaluation

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix
* Majority-class baseline accuracy

### Results

| Metric            | Result |
| ----------------- | -----: |
| Accuracy          | 50.00% |
| Precision         | 49.49% |
| Recall            | 49.49% |
| F1-score          | 49.49% |
| Baseline Accuracy | 50.38% |

The Random Forest performed approximately at the baseline level, with an accuracy **0.38 percentage points below the baseline**.

## Feature Importance

The most influential features identified by the Random Forest included:

1. Unit cost — 18.56%
2. Customer rating — 16.55%
3. Hour — 12.62%
4. Day of week — 9.84%
5. Month — 5.75%

These results suggest that transaction cost, customer ratings, and purchasing time contributed more to the model's decision-making than individual customer characteristics.

Feature importance is interpreted as the contribution of a variable to the model's decisions and does not imply causation.

## Exploratory Analysis

The project investigates purchasing behaviour through visualisations such as:

* Quantity distribution
* Average quantity by product line
* Average quantity by customer type
* Average quantity by hour
* Unit cost versus quantity
* Customer rating versus quantity
* Percentage of high-quantity transactions by product line

These analyses provide descriptive insights into supermarket purchasing behaviour.

## Key Findings

The Random Forest identified unit cost, customer rating and transaction timing as the most influential variables. However, the model achieved approximately 50% accuracy, which was effectively the same as the 50.38% baseline.

Therefore, the available transaction-level variables provided limited predictive information for distinguishing high-quantity transactions.

The dataset can still provide useful descriptive insights into purchasing behaviour, but stronger prediction would likely require additional information such as customer purchasing history, promotions, discounts, inventory availability, loyalty behaviour, and marketing exposure.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

## Project Structure

```text
Supermarket-Sales/
│
├── supermarket_sales.csv
├── Supermarket_Sales_Analysis.ipynb
└── README.md
```
