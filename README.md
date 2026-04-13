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
# 🌿 Vegetation Productivity Modelling Pipeline

A machine learning pipeline for predicting vegetation productivity using multi-source remote sensing and climate variables.

---

## 📁 Project Structure

---

## 🔄 Pipeline Overview

### 1. 📊 Exploratory Data Analysis
- Distribution plots and trend analysis across all variables
- Correlation heatmap to identify multicollinearity and key predictors

---

### 2. 🧪 Feature Engineering
Seven derived features were constructed to enrich the predictor set:

| Feature | Description |
|--------|-------------|
| `VHI` | Vegetation Health Index |
| `Canopy_Efficiency` | GPP / LAI |
| `Rain_Temp_Ratio` | Rainfall ÷ Temperature |
| `NDVI_FAPAR` | NDVI × FAPAR interaction |
| `SMI_Rainfall` | SMI × Rainfall interaction |
| `EVI_NDVI_Ratio` | EVI / NDVI |
| `Year_Norm` | Normalised year (temporal scaling) |

---

### 3. 🗂️ Temporal Train/Test Split
- **Train:** All years except 2020–2021
- **Test (held-out):** 2020–2021 — simulates real-world temporal generalization

---

### 4. 🤖 Model Training — 5-Fold Cross-Validation

Thirteen models evaluated using 5-fold CV:

| Category | Models |
|----------|--------|
| Linear | Linear Regression, Ridge, Lasso, ElasticNet |
| Instance-Based | K-Nearest Neighbours (KNN) |
| Tree-Based | Decision Tree, Bagging, Random Forest, Extra Trees |
| Boosting | Gradient Boosting, AdaBoost, XGBoost |
| Kernel-Based | Support Vector Regression (SVR) |
| Optional* | LightGBM, CatBoost |

> *LightGBM and CatBoost are included if the packages are installed in your environment.

---

### 5. ⚙️ Hyperparameter Tuning
- Method: `RandomizedSearchCV`
- Iterations: **60**
- Applied to shortlisted top-performing models from cross-validation

---

### 6. 🔍 Explainability
- **Feature Importance** — model-native importance scores
- **SHAP Analysis** — global and local interpretability using SHapley Additive exPlanations

---

### 7. 🏆 Final Leaderboard

Models are ranked on the held-out test set (2020–2021) using four metrics:

| Metric | Description |
|--------|-------------|
| **R²** | Proportion of variance explained |
| **RMSE** | Root Mean Square Error |
| **MAE** | Mean Absolute Error |
| **MAPE%** | Mean Absolute Percentage Error |

---

## 🚀 Getting Started

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
pip install -r requirements.txt
jupyter notebook notebooks/pipeline.ipynb
```

---

## 📦 Requirements
numpy
pandas
scikit-learn
xgboost
shap
matplotlib
seaborn
lightgbm # optional
catboost # optional

---

## 📄 License
This project is licensed under the MIT License.

## 🧰 Tech Stack

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-1.3-orange?style=for-the-badge&logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-red?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-2.0-purple?style=for-the-badge&logo=pandas)
![SHAP](https://img.shields.io/badge/SHAP-Explainability-purple?style=for-the-badge)

