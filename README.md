# Advanced-Crop-Prediction-using-ML
Predicting groundnut (peanut) yield in Gujarat, India using satellite vegetation indices (NDVI, EVI, LAI, GPP, FAPAR) and climatic variables with 13+ ML models, XGBoost tuning, SHAP explainability, and feature engineering.

# 🌱 Groundnut Yield Prediction — Gujarat, India
A complete end-to-end machine learning pipeline to predict
**groundnut (peanut) crop yield (tonnes/ha)** across five districts
of Gujarat, India, using multi-year satellite-derived vegetation
indices and climatic variables.
---
## 📌 Overview
Accurate crop yield prediction is critical for food security planning,
insurance risk assessment, and agricultural policy. This project
replaces expensive and time-consuming ground surveys with a
**remote sensing + ML approach** — combining freely available
satellite data (MODIS) with district-level agricultural statistics
to forecast yield before harvest.
---
## 📦 Dataset
| Variable | Source | Description |
|----------|--------|-------------|
| `NDVI` | MODIS MOD13A3 | Normalized Difference Vegetation Index |
| `EVI`  | MODIS MOD13A3 | Enhanced Vegetation Index |
| `FAPAR` | MODIS MOD15A2H | Fraction of Absorbed PAR |
| `GPP`  | MODIS MOD17A2H | Gross Primary Productivity |
| `LAI`  | MODIS MOD15A2H | Leaf Area Index |
| `Rainfall` | IMD | District-average kharif rainfall (mm) |
| `Temperature` | IMD | Growing-season temperature (K) |
| `SMI` | Derived | Soil Moisture Index |
| `Area` | Govt. of Gujarat | Net sown area (lakh ha) |
| `Production` | Govt. of Gujarat | Total production (lakh tonnes) |
- **Coverage:** 5 districts — Junagadh, Rajkot, Amreli, Jamnagar, Bhavnagar
- **Period:** 2000 – 2021 (22 years)
- **Target:** `Yield_(tonnes/ha)`
---
## 🛠️ Pipeline
