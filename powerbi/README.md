# 📊 Inventory Overview Dashboard

This Power BI dashboard provides a comprehensive view of warehouse inventory health and material flow recommendations using predictive analytics and business-driven scoring.

---

## 📁 Overview

The **Inventory Overview Dashboard** enables supply chain and operations teams to:

- Monitor past and forecasted inventory levels.
- Identify overflow and underflow risks.
- Take proactive action with **buy/sell recommendations** for top materials based on risk and value metrics.

---

## 🧭 Features

### 🔍 Filters
- **Year-Month Selector**: Filter by specific time periods.
- **Warehouse Toggle**: Compare performance across different warehouses (e.g., `CHINA-WAREHOUSE`, `SINGAPORE-WAREHOUSE`).

### 📦 Inventory Summary
- **Status Card**: Indicates whether the plant inventory is *Healthy*, *Overflowing*, or *Underflowing*.
- **Inventory Level (KT)**: Current or forecasted stock in kilotons.
- **Utilization Gauge**: Shows % of capacity used.

### 📈 Monthly Inventory Trend
- Clustered column chart showing:
  - **Past inventory** (gray bars)
  - **Predicted inventory** (blue bars)
  - **Max capacity** (black dashed line)
  - **Overflow/Underflow thresholds** (red/orange dashed lines)

### 🧾 Material Flow Suggestions
- **BUY / SELL Toggle**: Switch between top 5 materials to purchase or reduce.
- **Top Material Cards**: Ranks materials by priority with labels (e.g., `Rank 1`, `Rank 2`, etc.).

---

## ⚙️ How It Works

### 🔮 Forecasting
- Monthly inventory is forecasted using ML models such as **Gradient Boosting Regressor** with lag-based features and recursive prediction.

### 🚨 Utilization & Risk
- Forecasted inventory is compared to maximum plant capacity to flag:
  - `Overflow` if utilization > 80%
  - `Underflow` if stock is critically low
  - `Healthy` otherwise

### 🏷️ Buy/Sell Material Ranking

Material flow recommendations are ranked using a weighted scoring approach based on:

- **ABC Classification**: Categorizes materials by value and consumption importance.
- **Value at Risk**: Calculates potential financial risk if inventory goes obsolete or is overstocked.
- **Potential Lost Revenue**: Estimates loss due to stockouts or insufficient supply coverage.

---

## 🧠 Use Case

This dashboard empowers decision-makers to:

- Avoid inventory issues before they occur.
- Optimize warehouse space and capital investment.
- Make informed procurement and distribution decisions.

---

## 📌 Notes

- All inventory values are displayed in **kilotons (KT)**.
- Dashboard integrates data from actuals, forecasts, material master, and cost sheets.
- Visuals and insights are dynamically updated by filters and selections.

---

## 🛠️ Built With

- **Power BI Desktop / Power BI Service**
- **Python (for forecasting)**
- **DAX Measures and Calculated Tables**
- **Supply Chain Domain Knowledge**

---

## 📸 Screenshot

![Inventory Overview Dashboard](./path-to-your-screenshot.png)

---

## 👤 Authors

> Add your name or team info here.

---

## 📄 License

This project is for educational/hackathon purposes. Please update this section if deploying in production or using external data.

