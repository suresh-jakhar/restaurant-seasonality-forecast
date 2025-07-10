# Restaurant Seasonality Forecast and Analysis

This project analyzes historical daily revenue data from restaurant venues to uncover seasonality patterns, assign variability scores, and forecast future revenue performance. It delivers clean datasets, actionable insights, and ready to present Excel reports.

---

## Objective

- Identify monthly seasonality trends across restaurants
- Score restaurants based on revenue variability
- Forecast revenue for the next 6 months
- Provide business recommendations based on findings

---

## Process Overview

### 1. Data Cleaning
Raw data from Excel was cleaned to ensure consistency:
- Standardized column names
- Parsed dates correctly
- Removed rows with missing or corrupt revenue and GMV values
- Converted currency fields from string to float



---

### 2. Seasonality Index Calculation
For each restaurant:
- Monthly average revenue was calculated
- Overall average revenue was computed
- Seasonality Index = (Monthly Avg Revenue / Overall Avg Revenue)



---

### 3. Seasonality Score Assignment
Each venue’s monthly revenue was aggregated to calculate:
- Mean revenue
- Standard deviation
- Coefficient of Variation (CV)

Restaurants were scored from 1 (most stable) to 5 (most seasonal) based on CV distribution.



---

### 4. Revenue Forecasting
Applied Holt-Winters Exponential Smoothing:
- Automatically handled seasonality based on available data
- Forecasted revenue for the next 6 months per restaurant
- Skipped restaurants with insufficient data



---

### 5. Strategic Recommendations and Summary
For each restaurant:
- Identified top 2 peak months based on seasonality index
- Merged with seasonality scores
- Suggested business actions based on variability

Excel summary includes:
- Executive overview
- Top 10 most seasonal venues
- Top 10 most stable venues
- All venue insights



---

## Final Touch

All Excel files were manually reviewed and compiled. Interactive charts were added to the summary report for visual clarity and presentation purposes.

---

## Tools Used

- Python (Pandas, NumPy, Statsmodels, OpenPyXL)
- Excel (for final visualization and interaction)
- Jupyter Notebook (development environment)

---

## Key Insights Delivered

- Revenue trends by month and venue
- Stability score for each restaurant
- Actionable suggestions for operations and marketing
- Forward looking revenue projections

---






## This project was conceptualized, built, and executed by **Suresh Jakhar**, using publicly available Python libraries and Excel for final reporting.  The work was completed as part of a data analysis and forecasting assignment focused on restaurant performance optimization.