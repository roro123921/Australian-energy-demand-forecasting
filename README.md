# Australian Energy Demand Forecasting

Machine learning project analysing the relationship between weather conditions and electricity demand across Australia's National Electricity Market (NEM) using 20 years of historical data.

---

## Overview

Electricity demand varies significantly throughout the day and is strongly influenced by weather conditions. During periods of extreme heat or cold, demand increases as households and businesses rely more heavily on air conditioning and heating.

This project investigates how weather and temporal factors influence electricity demand across the five eastern Australian states and develops a machine learning model capable of forecasting electricity demand.

The project uses historical electricity demand data from the Australian Energy Market Operator (AEMO) together with weather observations from the Australian Bureau of Meteorology (BoM) covering the period **2000–2019**.

---

## Objectives

* Clean and integrate large-scale electricity demand and weather datasets.
* Explore relationships between electricity demand and weather variables.
* Perform statistical analysis and feature engineering.
* Train a machine learning model to predict electricity demand.
* Evaluate model performance and identify the most influential predictors.

---

## Dataset

### Electricity Demand

* Australian Energy Market Operator (AEMO)
* Half-hourly electricity demand
* Five NEM regions:

  * New South Wales (NSW)
  * Victoria (VIC)
  * Queensland (QLD)
  * South Australia (SA)
  * Tasmania (TAS)

### Weather Data

* Bureau of Meteorology (BoM)
* Half-hourly observations from capital city weather stations
* Variables include:

  * Temperature
  * Humidity
  * Rainfall
  * Wind speed

### Time Period

2000–2019 (20 years)

---

## Project Workflow

### 1. Data Preparation

* Imported and combined raw CSV files
* Parsed and standardised datetime values
* Aligned weather and electricity demand timestamps
* Removed duplicate records
* Handled missing values
* Merged datasets across all five states
* Exported a cleaned dataset for analysis

### 2. Exploratory Data Analysis (EDA)

* Investigated electricity demand trends over time
* Examined daily and seasonal demand patterns
* Analysed relationships between:

  * Temperature and demand
  * Humidity and demand
  * Rainfall and demand
  * Wind speed and demand
* Produced visualisations to identify trends and correlations

### 3. Feature Engineering

Created model features including:

* Hour of day
* Month
* Year
* State
* Weather variables

---

## Machine Learning

### Model

Random Forest Regressor

### Evaluation Metrics

* R² Score
* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

### Performance

The Random Forest model achieved an **R² score of approximately 0.87**, demonstrating strong predictive performance for electricity demand using weather and temporal features.

---

## Key Findings

* Temperature was the strongest predictor of electricity demand.
* Electricity demand followed clear daily and seasonal patterns.
* Weather variables significantly improved prediction accuracy.
* Random Forest effectively captured the non-linear relationship between weather conditions and electricity demand.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* SciPy
* Jupyter Notebook

---

## Repository Structure

```
Australian-energy-demand-forecasting/
│
├── data/
│   ├── raw/
│   └── cleaned/
│
├── notebook/
│   ├── 01_data_preparation.ipynb
│   ├── 02_exploratory_data_analysis.ipynb
│   ├── 03_machine_learning.ipynb
│   └── 04_model_evaluation.ipynb
│
├── report/
│
├── README.md
├── LICENSE
└── .gitignore
```

---

## My Contribution

This project was completed as part of **ADS1002 – Data Challenges 2** at Monash University in a team of four students.

My primary contributions included:

* Cleaning and preparing electricity demand datasets
* Exploratory data analysis
* Investigating rainfall-demand relationships
* Statistical analysis and visualisation
* Evaluating machine learning model performance
* Documenting project findings

---

## Future Improvements

Potential extensions include:

* Comparing additional machine learning models such as XGBoost and LightGBM.
* Incorporating public holiday and calendar effects.
* Using lagged demand features for time-series forecasting.
* Hyperparameter optimisation to further improve model performance.

---

## Acknowledgements

* Australian Energy Market Operator (AEMO)
* Australian Bureau of Meteorology (BoM)
* Monash University — ADS1002 Data Challenges 2
