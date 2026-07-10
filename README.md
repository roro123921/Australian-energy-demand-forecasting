## Australian Energy Demand Forecasting

Machine learning project analysing how weather and temporal factors influence electricity demand across Australia's National Electricity Market using 20 years of historical data.

---

## Overview

Electricity demand changes throughout the day and is strongly influenced by weather conditions. During periods of extreme heat or cold, demand increases as households and businesses rely more heavily on air conditioning and heating.

This project combines electricity demand data from the **Australian Energy Market Operator (AEMO)** with weather observations from the **Bureau of Meteorology (BoM)** to investigate these relationships and build a machine learning model capable of forecasting electricity demand.

**Project:** ADS1002 – Data Challenges 2 (Monash University)

---

## Business Problem

Accurate electricity demand forecasting helps energy providers:

- Optimise power generation
- Reduce operational costs
- Improve grid reliability
- Prepare for periods of peak demand

This project investigates how weather and time-based factors affect electricity demand across:

- New South Wales (NSW)
- Victoria (VIC)
- Queensland (QLD)
- South Australia (SA)
- Tasmania (TAS)

**Time Period:** 2000–2019

---

## Project Workflow

### Data Preparation

- Cleaned and merged AEMO electricity demand and BoM weather datasets
- Parsed datetime values and aligned half-hourly observations
- Handled missing values and data inconsistencies
- Combined all states into a single modelling dataset

### Exploratory Data Analysis

- Analysed electricity demand trends over time
- Investigated relationships between demand and:
  - Temperature
  - Humidity
  - Rainfall
  - Wind Speed
- Produced visualisations to identify key patterns

### Machine Learning

- Engineered temporal features
- Trained a **Random Forest Regressor**
- Evaluated model performance using **R², RMSE and MAE**
- Peformed Out-of-Sample testing on future data

---

## Results

| Metric | Result |
|---------|--------|
| **R² Score** | **≈ 0.87** |
| **RMSE** | **349 MW** |
| **MAE** | **223 MW** |

### Key Findings

- Temperature was the strongest predictor of electricity demand.
- Electricity demand followed clear daily and seasonal patterns.
- Weather variables significantly improved prediction accuracy.
- The Random Forest model captured complex non-linear relationships and achieved strong forecasting performance.

---

## Technologies Used

- Python
- Pandas
- NumPy
- SciPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

---

## My Contribution

This project was completed as part of a team of four students for **ADS1002 – Data Challenges 2** at Monash University.

My contributions included:

- Data cleaning and preparation
- Exploratory data analysis
- Rainfall–demand relationship analysis
- Statistical analysis and visualisation
- Machine learning model evaluation
- Documentation of project findings

---

## 📄 License

This project is licensed under the MIT License.
