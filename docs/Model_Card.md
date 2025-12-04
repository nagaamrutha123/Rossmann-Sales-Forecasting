
# Model Card — Rossmann Weekly Sales Forecasting

## 1. Model Overview
**Final Model:** XGBoostRegressor  
**Benchmark Model:** RandomForestRegressor  
**Task:** Weekly sales forecasting for all Rossmann stores  
**Forecast Horizon:** 6 weeks ahead  
**Explainability:** SHAP (global + local explanations)  
**Fairness Checks:** Per-store MAE error analysis  

## 2. Intended Use
- Inventory management  
- Workforce planning  
- Promotion strategy  
- Revenue forecasting  

Model should be used with **human oversight**.  
Decisions with financial or operational impact should be reviewed by analysts or managers.

## 3. Performance Summary
- **R²:** 0.9549  
- **MAE:** 2486.5852  
- **RMSE:** 3581.6115  

Performance is highest for stores with stable historical patterns.  
Errors increase for stores with sparse or irregular data.

## 4. Data Sources
- `train.csv` — historical store-level daily sales  
- `store.csv` — store metadata  
- Data aggregated into **weekly** format for forecasting  

No customer-level (PII) data is used.

## 5. Ethical Considerations
- Privacy preserved via aggregated, non-personal data  
- Fairness checked via per-store error distributions  
- Explainability available via SHAP  
- Human-in-the-loop recommended for major operational decisions  
- Monitor performance drift and retrain periodically  

## 6. Limitations
- Does not include external factors such as weather, holidays, or competition  
- Long-term forecasts (>6 weeks) become less reliable  
- Stores with little data may have higher errors  

## 7. Maintenance Recommendations
- Retrain monthly or when new data is available  
- Add new features and run SHAP checks after updates  
- Keep logs of predictions and monitor error drift  

---

Generated automatically by the Rossmann Forecasting Notebook.
