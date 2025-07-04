# 📦 Inventory Forecasting & Risk Recommendation – Hackathon Project

This project was built for a supply chain optimization hackathon and consists of two integrated components:

1. **🔍 Forecasting & Risk Detection (Python ML)**  
   - Predicts 3-month-ahead inventory at the plant-material level using Gradient Boosting  
   - Flags warehouse utilization risk: **Overflow**, **Underflow**, or **Healthy** based on capacity thresholds  

2. **📊 Dashboard & Action Recommendation (Power BI)**  
   - Visualizes predicted inventory, utilization %, and warehouse risk over time  
   - Ranks recommend materials for **Buy/Sell** action using a weighted scoring method based on:
     - ABC classification (stock value contribution)
     - Value at Risk
     - Potential Lost Revenue

---
