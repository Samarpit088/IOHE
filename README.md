# 🌾 Impact of Extreme Weather Events on Crop Yield Using ML Models

> **COOP-II (22CS421) – Internal Evaluation III**  
> Department of Computer Science & Engineering  
> Chitkara University Institute of Engineering & Technology  
> BE-CSE Batch 2022 | 8th Semester (Zeta Cluster)

---

## 👥 Team Members

| Name | Email |
|------|-------|
| Samarpit Sharma | samarpit2235.be22@chitkara.edu.in |
| Akanksha Chopra | akanksha1212.be22@chitkara.edu.in |
| Rohit Mahajan | rohit2179.be22@chitkara.edu.in |
| Surya Dev Singh | surya2423.be22@chitkara.edu.in |
| Dr. Shikha Tuteja | shikha.1290@chitkara.edu.in |

---

## 📌 Problem Statement

Extreme weather events (floods, droughts, heatwaves) driven by climate change pose severe threats to agricultural productivity in India. This project builds a **machine learning pipeline** to predict crop yield under varying and extreme weather conditions across **10 Indian states (1997–2020)**, with a focus on quantifying the impact of extreme rainfall events.

---

## 🚀 How to Run

1. Open [Google Colab](https://colab.research.google.com/)
2. Upload `crop_yield_extreme_weather.ipynb`
3. Run


> ✅ No external data files needed — the dataset is generated synthetically within the script.

---

## 📊 Dataset Overview

| Property | Value |
|----------|-------|
| Total records | 5,000 |
| States covered | 10 (Punjab, Haryana, Maharashtra, Karnataka, Tamil Nadu, UP, AP, Gujarat, Rajasthan, West Bengal) |
| Crops | 8 (Rice, Wheat, Maize, Cotton, Sugarcane, Soybean, Groundnut, Barley) |
| Time period | 1997 – 2020 |
| Input features | 15 |
| Target variable | `yield_kgha` (crop yield in kg/ha) |
| Extreme weather events | ~12% of records (rainfall > 350 mm) |

### Features Used

| Feature | Description |
|---------|-------------|
| `year` | Year of observation |
| `avg_temp_c` | Average temperature (°C) |
| `total_rainfall_mm` | Total annual rainfall (mm) |
| `avg_humidity_pct` | Average relative humidity (%) |
| `N`, `P`, `K` | Soil macronutrients (kg/ha) |
| `ph` | Soil pH |
| `area_ha` | Cultivated area (ha) |
| `fertilizer_kg` | Fertilizer applied (kg/ha) |
| `pesticide_kg` | Pesticide applied (kg/ha) |
| `crop` | Crop type (encoded) |
| `season` | Growing season (Kharif/Rabi/Zaid, encoded) |
| `state` | Indian state (encoded) |
| `extreme_weather` | **Binary flag** – 1 if rainfall > 350 mm, else 0 |

---

## 🤖 ML Models

| Model | Type | Key Config |
|-------|------|-----------|
| Linear Regression | Baseline | Default |
| Random Forest | Ensemble (Bagging) | 200 estimators, random_state=42 |
| Gradient Boosting | Ensemble (Boosting) | 200 estimators, random_state=42 |

### Results (Test Set – 1,000 samples)

| Model | RMSE (kg/ha) | MAE (kg/ha) | R² Score |
|-------|-------------|------------|---------|
| Linear Regression | 286.26 | 228.76 | 0.0720 |
| **Random Forest** | **283.56** | **225.95** | **0.0894** |
| Gradient Boosting | 285.80 | 227.59 | 0.0750 |

> 🏆 **Random Forest** achieved the best performance across all three metrics.

---

## 📈 Visualizations Produced

1. **Correlation Heatmap** – Feature correlations with yield target
2. **State × Year Heatmap** – Yield trends across states and years
3. **Rainfall vs Yield Scatter** – Quadratic trend, extreme events highlighted
4. **Temperature vs Yield Scatter** – Optimal temperature range visualization
5. **Box + Violin Plots** – Yield under normal vs extreme conditions; yield by crop type
6. **Pair Plot** – Pairwise relationships of key predictors
7. **Model Comparison Bar Chart** – RMSE, MAE, R² across all three models
8. **Actual vs Predicted + Residual Plot** – Random Forest prediction quality
9. **Feature Importance Chart** – Top predictors ranked by RF importance
10. **Temporal Yield Trend (1997–2020)** – Yield gap under extreme vs normal weather

---

## 🔑 Key Findings

- **Random Forest** outperformed Linear Regression and Gradient Boosting
- **Fertilizer** and **soil nitrogen (N)** are the top yield predictors (importance > 0.12)
- The engineered **`extreme_weather`** binary feature ranked in the **top 8** of 15 features
- Extreme rainfall events (> 350 mm) caused a **statistically significant drop** in median yield
- Optimal temperature range for crop yield: **22°C – 33°C**
- Both yield trend lines show an **upward trend** over 1997–2020, but the yield gap between normal and extreme years **widens** over time (consistent with IPCC climate projections)

---

## 🔭 Future Scope

- Incorporate **satellite vegetation indices** (NDVI, EVI) from Sentinel-2/MODIS
- Experiment with **XGBoost, LightGBM, Stacked Generalization**
- Apply **LSTM / Temporal Convolutional Networks** for multi-step yield forecasting
- Use **Bayesian calibration** for crop-specific extreme weather thresholds
- Integrate **CMIP6 climate projections** for forward-looking SSP2/SSP5 scenarios
- Build a **web-based advisory system** with district-level weather APIs

---

## 📄 Research Paper

This project is accompanied by a research paper:

> *"Impact of Extreme Weather Events on Crop Yield Using ML Models"*  
> Samarpit Sharma, Akanksha Chopra, Rohit Mahajan, Surya Dev Singh, Dr. Shikha Tuteja   
> Chitkara University, Punjab, India

---

## 📚 Key References

1. FAO, *The State of Food and Agriculture 2021*, Rome, 2021.
2. IPCC, *Climate Change 2021: The Physical Science Basis*, Cambridge University Press, 2021.
3. Van Klompenburg et al., *Crop yield prediction using machine learning: A systematic literature review*, Computers and Electronics in Agriculture, vol. 177, 2020.
4. Breiman, L., *Random forests*, Machine Learning, vol. 45, no. 1, pp. 5–32, 2001.
5. Pedregosa et al., *Scikit-learn: Machine learning in Python*, JMLR, vol. 12, 2011.

---

## ⚖️ License

This project was developed for academic purposes as part of COOP-II (22CS421) at Chitkara University. All rights reserved by the authors.
