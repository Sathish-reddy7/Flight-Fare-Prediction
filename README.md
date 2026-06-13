# Flight Fare Prediction

## Overview
This project predicts flight ticket prices based on 
features like airline, source, destination, duration 
and number of stops.

## Problem Statement
Flight ticket prices are highly unpredictable and vary 
based on multiple factors. This project uses machine 
learning to help customers plan their journeys by 
predicting fares in advance.

## Dataset
- 10,683 flight records
- Features: Airline, Date_of_Journey, Source, Destination, 
  Route, Dep_Time, Arrival_Time, Duration, Total_Stops, 
  Additional_Info
- Target: Price (in INR)

## Approach
- Exploratory Data Analysis (EDA)
- Heavy Feature Engineering:
  - Extracted day/month from journey date
  - Extracted hour/minute from departure and arrival times
  - Converted duration to total minutes
  - Converted stops to numeric values
- One Hot Encoding for categorical features
- Trained and compared 3 models: Linear Regression, 
  Random Forest, XGBoost

## Results
| Model | R² Score | MAE | RMSE |
|---|---|---|---|
| XGBoost (tuned) | 0.8538 | 1186.00 | 1758.89 |
| XGBoost (default) | 0.8467 | 1151.72 | 1801.09 |
| Random Forest | 0.8085 | 1178.65 | 2013.39 |
| Linear Regression | 0.6150 | 1982.57 | 2854.37 |

**Best Model:** XGBoost (Tuned) — selected for production 
due to highest R² score and lowest RMSE.

## Key Insight
Flight prices have non-linear relationships with features 
like total stops, airline type and journey duration — tree 
based models significantly outperform linear models.

## Tech Stack
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost
