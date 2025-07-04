# 📦 Inventory Forecasting Script

This contains the code used to forecast monthly inventory levels at the **plant-material** level using machine learning. The results are prepared for integration with Power BI for warehouse capacity monitoring and material flow suggestions.

---

## 📂 Input Files

- `cleaned_Inventory.csv`  
- `cleaned_Inbound.csv`  
- `cleaned_Outbound.csv`  
- `MaterialMaster.csv`  

Each file includes `PLANT_NAME`, `MATERIAL_NAME`, date fields, and quantity metrics. Units are converted to **KT (kiloton)** as part of preprocessing.

---

## 🔧 Key Steps in Script

### 📌 1. Data Preparation
- Convert dates to monthly periods.
- Aggregate monthly stock, inbound, and outbound quantities per plant-material.
- Merge with material master (includes `SHELF_LIFE_IN_MONTH`).
- Create **lag features** for previous month’s inventory, inbound, outbound.
- Add **cyclical features** for month (sin, cos).

### 📌 2. Model Training
- Uses `GradientBoostingRegressor` from `sklearn.ensemble`.
- Hyperparameters tuned with `GridSearchCV` and `TimeSeriesSplit` (5-fold).
- Evaluation metric: **Mean Absolute Error (MAE)**.

### 📌 3. Recursive Forecasting
- Forecasts the next **3 months** for each plant-material using latest lag values.
- Forecasted inventory is updated and reused as lag for future steps.

### 📌 4. Warehouse Summary
- Aggregate forecasted inventory by warehouse and month.
- Compare to manual capacity limits:
  ```python
  manual_capacity = {
      "CHINA-WAREHOUSE": 70.0,
      "SINGAPORE-WAREHOUSE": 53.5
  }
