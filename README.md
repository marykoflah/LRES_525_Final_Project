# LRES 525 SWE Prediction Workflow

This repository supports the final project for LRES 525, focused on predicting Snow Water Equivalent (SWE) and Snow Depth (SNWD) in the Absaroka-Beartooth Wilderness using machine learning and remote sensing techniques.

---

## 📁 Repository Structure

```
├── Beartooth Shapefiles/                 # ✅ AOI shapefiles for clipping rasters and defining study region
│   └── Absaroka_Beartooth.shp            # Required shapefile for the AOI
│
├── GoogleEarthEngineCode                 # JavaScript code for GEE NDVI/NDSI export and processing
│
├── LRES525SWEPredictionWorkflow.ipynb    # Main Python notebook for SWE modeling with CatBoost, LightGBM, XGBoost
│
├── LICENSE                                # Licensing info
│
└── README.md                              # Project overview and instructions (you’re reading it!)
```

---

## 📌 Project Purpose

This workflow predicts SWE and SNWD across the mountainous Absaroka-Beartooth region using:

* **Remote Sensing Indices**: NDVI & NDSI from Sentinel-2
* **Topography**: Elevation, slope, aspect from DEMs
* **Atmospheric Variables**: HRRR reanalysis (temperature, wind, radiation, precipitation)
* **Ground Truth**: SWE & SNWD from SNOTEL stations (5 km buffer zone)

---

## 🧪 Workflow Summary

1. **Google Earth Engine**: Export NDVI, NDSI, and elevation by SNOTEL buffers
2. **Data Aggregation**: Combine CSVs and assign season/year
3. **Modeling**: Run CatBoost, LightGBM, and XGBoost
4. **Prediction**: Export rasterized SWE predictions and clip using the AOI shapefile

---

## 🧷 Prerequisites

Ensure the following are installed in your environment:

```bash
pandas
numpy
geopandas
rasterio
matplotlib
scikit-learn
xgboost
lightgbm
catboost
```

---

## 🗺️ Study Area

* **Location**: Absaroka-Beartooth Wilderness, Montana, USA
* **Shapefile Required**: Make sure `Beartooth Shapefiles/Absaroka_Beartooth.shp` is present and used in all spatial operations.

---

## 🔁 Future Work

* Add Slope and Aspect as features
* Evaluate models using spatial cross-validation
