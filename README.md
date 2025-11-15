# 🏙️ Geospatial Analysis of Housing Data — Brasília (DF)

How do structural features, geographic location, and proximity to urban amenities influence real estate prices in Brasília?
This project combines **GeoPandas**, **OpenStreetMap (OSM)** data, and **Machine Learning** to investigate how spatial and non-spatial factors shape property values in Brazil’s capital.

---

## 📌 Objectives

* Analyze how **intrinsic features** (area, rooms, suites, parking spaces) relate to price.
* Evaluate the impact of **geographical location** on real estate value.
* Compute distances to key **Points of Interest (POIs)** such as schools, hospitals, parks and embassies.
* Compare predictive performance of:

  * Linear Regression
  * Multiple Linear Regression (OLS)
  * Random Forest Regressor
* Assess improvements after adding **geospatial variables**.

---

## 🗂️ Project Structure

```
├── ANALISYS_DATA/          
├── GEO_DATA_FILE/          
├── MODEL_RESULTS/          
├── REAL_STATE_DATA/        
│
├── Geospatial_Analysis_of_Housing_Data.ipynb
├── requirements.txt
└── README.md
```

---

## 🧭 Data Overview

* **23k+ properties** with geographic coordinates
* **IBGE boundary** for Federal District
* **64k+ POIs** from OSM
* Metro/BRT infrastructure
* Cleaned, validated and clipped to Brasília’s boundaries
* Exported as a unified **GeoPackage (.gpkg)**

---

## 📊 Main Findings (Non-Spatial Models)

### 🔹 Linear Regression

* R² ≈ **0.24**
* Captures only basic patterns

### 🔹 Multiple Linear Regression (OLS)

* R² ≈ **0.34**
* Relevant predictors: usable area, suites, parking spaces
* Strong multicollinearity observed
* Non-normal residuals

### 🔹 Random Forest (No POIs)

* R² ≈ **0.70**
* Handles nonlinear relationships
* Best baseline performance

---

## 🌍 Impact of Geospatial Features (POIs)

### ✔️ OLS with POIs

* R² increases dramatically: **0.34 → 0.64**
* Captures:

  * neighborhood effects
  * accessibility to services
  * local urban context
* Still affected by multicollinearity

### ✔️ Random Forest with POIs

* Further improvement: **R² = 0.722**
* Lower MAE and RMSE
* Highlights importance of:

  * suites
  * usable area
  * neighborhood (Lago Sul)
  * proximity to embassies, theatres, residential clusters

> **Conclusion:** Location and access to urban amenities strongly influence property prices in Brasília.

---

## 🧠 Final Conclusions

* Real estate value depends on **what a property is** *and* **where it is**.
* Spatial context dramatically enhances predictive accuracy.
* POIs provide meaningful insights into Brasília’s urban dynamics.
* Random Forest was the most robust model overall, especially with geospatial features.

---

## 🔧 Tech Stack

* Python (GeoPandas, Shapely, StatsModels)
* Scikit-Learn (RandomForestRegressor)
* Matplotlib / Seaborn
* OpenStreetMap + IBGE spatial data
* R-tree / STRtree for spatial indexing

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 📄 License

MIT License — free to use and modify.



