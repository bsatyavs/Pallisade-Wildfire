# 🔥 Wildfire Building Damage Assessment using ML & GIS (Palisade Wildfire 2025)

This project presents a GIS-integrated machine learning framework to assess wildfire-induced building damage. The case study focuses on the 2025 Palisade Wildfire in California, leveraging high-resolution satellite imagery, terrain, wind, and land cover data.

## 📌 Overview

Using building-level point data, the workflow computes vegetation loss and burn severity (ΔNDVI and ΔNBR), merges them with environmental features (slope, wind, NLCD), and applies four supervised ML models to classify buildings as **Damaged** or **Undamaged**.

## 🧠 Models Used
- Random Forest
- Support Vector Machine (SVM)
- Logistic Regression
- XGBoost (Best performing model - 83.2% accuracy)

## 🗺️ Interactive Folium Map

The XGBoost-predicted building damage classifications are overlaid on an interactive map using **Folium**.

👉 [View Live Map] (https://github.com/bsatyavs/Pallisade-Wildfire/blob/main/XGBoost_Predicted_Map_with_Legend_and_DatasetType.html)
## 📁 Files

| File                              | Description                                       |
|-----------------------------------|---------------------------------------------------|
| `pallisate_building_damage.ipynb` | Jupyter Notebook with complete ML + GIS workflow |
| `XGBoost_Predicted_Map_with_...`  | Exported Folium HTML map                         |
| `Pallisade_point_data.csv`        | Building-level dataset with spatial + damage data |
| `README.md`                       | Project overview and instructions                |


## 📊 Dataset

The dataset includes:
- 9,543 building points
- Damage labels (Ground truth)
- ΔNDVI & ΔNBR indices
- Slope (from DEM), Wind Speed (Global Wind Atlas)
- NLCD land cover classification

## 🧭 Dependencies
- Python 3.9+
- pandas, geopandas, scikit-learn, xgboost, folium, matplotlib

```bash
pip install -r requirements.txt
