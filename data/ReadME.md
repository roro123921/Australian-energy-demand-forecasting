# Dataset

## Overview

This project combines electricity demand data from the **Australian Energy Market Operator (AEMO)** with weather observations from the **Australian Bureau of Meteorology (BoM)** to investigate how weather and temporal factors influence electricity demand.

The dataset covers the five major East Coast Australian states:

- New South Wales (NSW)
- Victoria (VIC)
- Queensland (QLD)
- South Australia (SA)
- Tasmania (TAS)

The data covers the period **2000–2019** with half-hourly observations.

---

# Raw Data

## Electricity Demand Data (AEMO)

The raw electricity demand data was provided as separate CSV files for each state and month.

Example file naming format:

```
DATA200001_NSW1.csv
DATA200001_VIC1.csv
DATA200001_QLD1.csv
DATA200001_SA1.csv
```

Each file contains half-hourly electricity market information.

### Raw demand structure

| REGION | SETTLEMENTDATE | TOTALDEMAND | RRP | PERIODTYPE |
|--------|---------------|------------:|----:|------------|
| NSW1 | 2000/01/01 00:30 | 6763.57 | 15.64 | TRADE |
| NSW1 | 2000/01/01 01:00 | 6386.10 | 14.06 | TRADE |
| NSW1 | 2000/01/01 01:30 | 5990.80 | 14.30 | TRADE |

Key variables:

- `TOTALDEMAND` — electricity demand (MW)
- `RRP` — regional reference price
- `SETTLEMENTDATE` — half-hourly timestamp

---

## Weather Data (BoM)

Weather observations were sourced from the Bureau of Meteorology Automatic Weather Station (AWS) datasets.

The raw weather files contained half-hourly observations from weather stations located in each state's capital city.

### Raw weather structure

| Date/Time | Precipitation | Air Temperature | Humidity | Wind Speed |
|-----------|--------------:|----------------:|---------:|-----------:|
| 2000-01-01 00:00 | 0.0 | 22.4 | 81 | 13.0 |
| 2000-01-01 00:30 | 0.0 | 22.0 | 75 | 13.0 |
| 2000-01-01 01:00 | 0.0 | 21.7 | 78 | 11.2 |

Relevant weather variables:

- Precipitation (mm)
- Air temperature (°C)
- Relative humidity (%)
- Wind speed (km/h)

---

# Data Processing

The raw datasets required cleaning and transformation before modelling.

Processing steps included:

- Converted timestamps into consistent datetime format.
- Extracted relevant weather variables.
- Removed unnecessary quality flags and metadata columns.
- Matched electricity demand and weather observations using timestamps.
- Combined datasets separately for each state.
- Added state identifiers.
- Created a final combined dataset containing all states.

---

# Final Dataset

The final dataset contains aligned electricity demand and weather observations across all five states.

Each row represents a half-hour observation.

### Final dataset structure

| State | Datetime | Total Demand | RRP | Precipitation (mm) | Air Temp (C) | Humidity (%) | Wind Speed (km/h) |
|-------|----------|--------------:|----:|-------------------:|--------------:|-------------:|------------------:|
| NSW | 2000/01/01 01:00 | 6386.10 | 14.06 | 0.0 | 17.4 | 62 | 0.0 |
| NSW | 2000/01/01 01:30 | 5990.80 | 14.30 | 0.0 | 16.8 | 73 | 0.0 |
| NSW | 2000/01/01 02:00 | 5655.98 | 14.28 | 0.0 | 16.5 | 71 | 0.0 |

---

## Final Features Used

The final modelling dataset included:

| Feature | Description |
|---------|-------------|
| State | Australian state identifier |
| Datetime | Half-hourly timestamp |
| Total Demand | Electricity demand target variable |
| RRP | Electricity market price |
| Precipitation | Rainfall amount |
| Air Temperature | Temperature measurement |
| Humidity | Relative humidity |
| Wind Speed | Wind speed measurement |

Additional temporal features were created during modelling:

- Hour of day
- Month
- Year
- Weekend indicator

---

## Notes

The raw datasets contain thousands of individual files across multiple states and years. The processed dataset used for modelling was generated through the data preparation notebook.
