# 📊 Restaurant Revenue Seasonality & Forecasting Analysis

This project provides a complete, automated pipeline for **analyzing restaurant-level revenue data**, uncovering **seasonality patterns**, assigning **stability scores**, and **forecasting** future performance — all in a clean Excel format.

We built this solution using Python and Jupyter Notebooks, operating on a real-world dataset of over **37,000 rows** representing daily revenue data across multiple venues.

---

## 🚀 Objective

To empower non-technical stakeholders (like HR and ops teams) to:

- Understand **monthly performance trends**
- Identify **seasonal fluctuations** per restaurant
- Know which restaurants are **more predictable or volatile**
- Forecast **the next 6 months** of expected revenue per venue
- Access it all via clean, dropdown-driven Excel dashboards

---

## 🧩 Project Structure (5 Notebooks → Excel Outputs)

This pipeline is broken into **5 notebooks**, each building on the last:

---

### 1️⃣ `1_cleaning_and_structure.ipynb`  
**🔧 Goal:** Clean and prepare raw input from `Seasonality_Model.xlsx`

**What We Did:**

- Loaded over **37,000 rows** of daily revenue data
- Standardized column names
- Converted date strings to `datetime` objects
- Cleaned currency fields (GMV & Revenue), removing commas
- Removed nulls and invalid entries

**Why:** Raw business data is messy — this step ensures consistency before analysis.

**Output:**  
✅ `Cleaned_Seasonality_Data.xlsx`

---

### 2️⃣ `2_seasonality_indices.ipynb`  
**📈 Goal:** Quantify how seasonal each venue is on a month-by-month basis.

**What We Did:**

- Grouped data by **restaurant + month**
- Calculated **average monthly revenue**
- Computed the **Seasonality Index**:  
- Used this to highlight high vs. low revenue months per restaurant

**Why:** To uncover seasonal trends (e.g. peak in December, dip in Feb).

**Output:**  
✅ `Monthly_Seasonality_Indices.xlsx`

---

### 3️⃣ `3_score_assignment.ipynb`  
**🎯 Goal:** Assign a **Seasonality Score (1–5)** based on revenue stability

**What We Did:**

- Aggregated monthly revenue per restaurant
- Calculated the **coefficient of variation (CV)**:  
- Used **quantile binning** (`pd.qcut`) to assign scores:
- `1` = very stable
- `5` = highly volatile or seasonal

**Why:** This helps management identify risky or erratic venues.

**Output:**  
✅ `Seasonality_Scores.xlsx`

---

### 4️⃣ `4_forecast_model.ipynb`  
**🔮 Goal:** Predict the next 6 months of revenue for each restaurant

**What We Did:**

- Aggregated revenue by **Month-Year**
- Applied **Holt-Winters Exponential Smoothing**, adapting seasonality automatically:
- If ≥24 months: seasonal_periods = 12  
- If ≥12 months: seasonal_periods = 6  
- Otherwise: no seasonal pattern used
- Handled short time series with fallback logic
- **Set negative forecasts to 0** (since revenue can't be negative)

**Why:** To give HR/ops a reliable picture of future performance, venue-wise

**Output:**  
✅ `6_Month_Revenue_Forecast.xlsx`

---

### 5️⃣ `5_Summary_Report.ipynb`  
**📊 Goal:** Deliver the insights in a fully usable format to HR/stakeholders

**What We Did:**

- Merged:
- Forecasted revenue (next 6 months)
- Seasonality score
- Built an Excel report with:
- **Dropdown to filter by venue**
- **Dynamic chart updates** per selection

**Why:** Your HR team shouldn’t need Jupyter — we put the power into Excel.

**Output:**  
✅ `Restaurant_Performance_Summary.xlsx`

---

## 🛠️ Tools & Libraries Used

| Technology | Purpose |
|------------|---------|
| Python (pandas) | Data manipulation, aggregation |
| `statsmodels` | Time series forecasting (Holt-Winters) |
| `openpyxl` | Excel file creation |
| `ipywidgets` | Interactive dropdowns (for dev use) |
| Excel | Final stakeholder-facing reporting |

---

## 📁 Output Files Summary

| File Name                         | Description                                |
|----------------------------------|--------------------------------------------|
| `Cleaned_Seasonality_Data.xlsx`  | Cleaned base data (37,000+ rows)           |
| `Monthly_Seasonality_Indices.xlsx` | Month-wise trend patterns per venue     |
| `Seasonality_Scores.xlsx`        | Score (1–5) based on revenue variability   |
| `6_Month_Revenue_Forecast.xlsx`  | Forecasted revenue for next 6 months       |
| `Restaurant_Performance_Summary.xlsx` | Final interactive report (for HR)      |

---

## 📌 How to Use This Project

1. Clone this repo and run notebooks in sequence (1 to 5)  
2. All outputs are saved as Excel files  
3. Open `Restaurant_Performance_Summary.xlsx`  
4. Use dropdowns and charts to explore venue performance

---

## 👥 Built For

- **HR, Operations, and Strategy teams**
- Non-technical business users who need **clean insights, not raw code**
- Analysts needing a repeatable, end-to-end forecasting framework

---

## 👨‍💻 Built With ❤️ by [Your Name]

If you'd like to extend this to:
- Add cost/margin analysis  
- Build Power BI dashboards  
- Deploy forecasts via API  
→ Just ask 😉

---
