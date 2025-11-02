# Rainfall Forecasting & Trend Analysis in Delhi NCR

## Project Overview

This project leverages satellite-derived monthly rainfall data to analyze, visualize, and predict rainfall patterns in Delhi NCR over a decade. Aimed at supporting water resource management, agriculture, and urban planning, the work offers scientifically-backed insights and forecasts.

## Why This Project?

Rainfall is a vital driver of agriculture, water supply, and disaster management. With climate variability, understanding long-term trends and anticipating future rainfall is crucial. This project combines remote sensing data, statistical trend detection, and machine learning to deliver an end-to-end rainfall analysis pipeline, empowering policymakers and stakeholders with actionable predictions.

## What Have I Used?

- **Data Source:** NASA GPM IMERG Monthly Satellite Data `NASA/GPM_L3/IMERG_MONTHLY_V07` (in mm/month) 
- **Tools & Libraries:**  
  - Google Earth Engine (GEE) for cloud-based data access  
  - Python, Pandas, NumPy, Matplotlib for data handling and visualization  
  - Scikit-learn, XGBoost, TensorFlow Keras for machine learning and deep learning models  
  - Geemap for interactive spatial mapping  
- **Approach:**  
  - Spatial-temporal analysis of rainfall patterns  
  - Trend detection with Mann-Kendall test  
  - Feature engineering for seasonality and lag effects  
  - Multi-model forecasting (RF, XGBoost, LSTM) for robust prediction  

## Why Is This a Good ML Project?

- **Real-World Relevance:** Tackles climate change impact and water management challenges  
- **Innovative Use of Satellite Data:** Transforms satellite raster data into actionable insights  
- **Integrated Pipeline:** From data acquisition and preprocessing to trend analysis and future prediction  
- **Interactivity & Visualization:** Clear maps and plots for stakeholder communication  
- **Reproducibility & Extensibility:** Modular ML models and open data access ensure adaptability for other regions or datasets

---

## Results & Analysis

### Rainfall Statistics (2004-2024)
- **Mean Annual:** 761.7 mm/year  
- **Range:** 543.7 - 1071.8 mm/year  
- **Monsoon Contribution:** ~610 mm (80% of annual rainfall)

### Trend Detection
```bash
# Annual Trend: No significant trend 
# January: Significant increasing trend (+1.69 mm/year, p = 0.015) — only statistically     significant month  
# Core Monsoon (Jun-Sep): Stable, no significant trends  
# High Variability Months: November, December, February (CV > 140%)  
# Most Stable Month: July (CV = 31%, mean = 227.8 mm)
```

### Machine Learning Performance

| Model | Test RMSE (mm) | Test R² | Best For |
|-------|---|---|---|
| LSTM | **31.95** | **0.859** | Best overall balance |
| XGBoost | 34.16 | 0.838 | Robust generalization |
| Random Forest | 36.89 | 0.811 | Feature importance |

**Best Model:** LSTM with R² = 0.859 on unseen test data

### Seasonal Patterns
| Season | Mean (mm) | Std Dev | Variability |
|--------|---|---|---|
| **Monsoon (Jun-Sep)** | 610 | 154 | Stable, reliable |
| Pre-monsoon (Mar-May) | 85 | 50 | Moderate variability |
| Post-monsoon (Oct-Nov) | 32 | 32 | High risk period |
| Winter (Dec-Feb) | 61 | 45 | High risk period |

---

## Key Findings

**Monsoon Reliability:** Core monsoon (June-September) shows strong stability — critical for agricultural planning  
**January Intensification:** Significant rainfall increase over 20 years — may indicate climate pattern shifts  
**July Predictability:** Lowest inter-annual variability makes July ideal for water resource budgeting  
**Winter Risk:** December-February shows high uncertainty — requires contingency planning  
**ML Forecasting:** LSTM model achieves 86% variance explanation on test data  

---

## Water Resource Implications

| Category | Details |
|----------|---------|
| **Most Predictable** | July (CV = 31%, mean = 228 mm) |
| **Most Unpredictable** | November (CV = 166%), December (CV = 144%) |
| **Agricultural Planning** | Rely on monsoon stability; supplement during winter/post-monsoon |
| **Urban Resilience** | High year-to-year variation requires adaptive water management |
| **Drought/Flood Risk** | Monsoon reliable; off-season periods require buffer capacity |

---

## Limitations

- Results localized to Delhi NCR; spatial generalization not recommended  
- Satellite data uncertainty (~±10-20% typical for IMERG)  
- 20-year record is relatively short for detecting long-term climate signals  
- Urban heat island and land-use changes may influence local patterns  
- ML models trained on historical patterns; future climate shifts not captured

---

## Repository Structure

```
results/
├── 01_exploratory_analysis.png        # Time series, climatology overview
├── 02_seasonal_trends.png             # Seasonal decomposition & trends
├── 03_coefficient_variation.png       # Variability analysis
├── 04_model_comparison.png            # ML model performance
├── trend_analysis_monthly.csv         # Month-wise Mann-Kendall results
├── variability_analysis.csv           # CV & inter-annual variability
├── model_comparison.csv               # ML metrics
├── future_rainfall_forecast.csv       # Forecast
└── annual_rainfall.csv                # Annual aggregates
```
---
![image](https://github.com/user-attachments/assets/9fed81a3-0fb1-4151-9709-2125689559df)
---

**Authors:** Ansh Gupta & Prakhar Prajapati  
**Data Period:** 2004-2024 (20 years, 240 months)  
**Last Updated:** November 2025
