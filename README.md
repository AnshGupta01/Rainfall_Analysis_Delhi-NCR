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
# Final Summary of the Project 💻

## Overview

The annual Mann-Kendall test showed no significant trend, but the month-wise analysis reveals important seasonal patterns masked in annual aggregation.

## Methodology

- **Linear Regression**: Trend slope (mm/year) for each month using 11-year data (2013-2023)  
- **Significance Testing**: p-value < 0.05 considered significant  
- **Coefficient of Variation (CV)**: (Std Dev / Mean) × 100 to assess inter-annual variability  

## Key Findings

### Significant Trends

| Month   | Slope (mm/year) | P-value | Notes                          |
|---------|-----------------|---------|-------------------------------|
| January | +2.23           | 0.0099  | Only significant increasing trend |
| October | +1.825          | 0.0532  | Near-significant increase, possible monsoon extension |

### Monsoon Stability (June-September)

| Month    | Slope (mm/year) | P-value |
|----------|-----------------|---------|
| June     | -1.021          | 0.573   |
| July     | +1.974          | 0.447   |
| August   | -1.983          | 0.505   |
| September| -0.715          | 0.823   |

Core monsoon period remains stable.

### Other Months

Pre-monsoon (March-May) and remaining winter/post-monsoon months show near-zero trends.

## Conclusions

- January shows a significant increasing trend.  
- October shows marginally significant increase.  
- Core monsoon (June-September) remains stable.  
- All months show high inter-annual variability.  
- July is the most reliable month.

## Water Resource Implications

- **Most Predictable**: July (for water budgeting)  
- **Most Unpredictable**: November, October, February (risk periods)  
- **Drought/Flood Risk**: High year-to-year variation across all months  
- **Agricultural Planning**: Consider variability in winter and post-monsoon periods  
- **Monsoon Reliability**: Core monsoon (July-August) is relatively consistent  

## Limitations

- Results localized to Delhi NCR; may not generalize.  
- Satellite data may have inherent uncertainties.  
- Urban effects (heat island, land-use changes) may impact local rainfall patterns.  

---

**Author:** Ansh Gupta & Prakhar Prajapati<br>