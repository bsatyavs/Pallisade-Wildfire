# 🔥 Wildfire Building Damage Assessment using Machine Learning & GIS (Palisade Wildfire 2025)

This repository presents a machine learning and GIS-integrated framework to classify building damage caused by the 2025 Palisade Wildfire in California. Using pre- and post-fire satellite imagery, terrain and wind data, and land cover classification, the project implements and compares multiple supervised models to predict building damage. The top-performing model (XGBoost) is deployed through an interactive Folium-based web map.

---

## 📌 Project Highlights

- 🛰️ Inputs: High-resolution PlanetScope imagery, USGS DEM, NLCD, wind data
- 📦 Dataset: 9,543 buildings labeled as Damaged/Undamaged
- 🔁 Models: Random Forest, SVM, Logistic Regression, XGBoost
- 📊 Metrics: Accuracy, Precision, Recall, F1-score, Confusion Matrix
- 🗺️ Visualization: Interactive Folium web map with building footprint overlay
- 📁 Deployment: Hosted via GitHub Pages

---

## 🧠 Machine Learning Pipeline

1. Feature Extraction: ΔNDVI, ΔNBR, slope, wind speed, NLCD
2. Feature Engineering: Normalization, label encoding, class balancing
3. Model Training: RF, SVM, LR, XGBoost with stratified 80/20 split
4. Evaluation: Accuracy, F1-Score, Feature Importance
5. Deployment: Visualization using Folium + GitHub Pages

---

## 🗺️ Live Interactive Map

👉(https://github.com/bsatyavs/Pallisade-Wildfire/blob/main/XGBoost_Predicted_Map_with_Legend_and_DatasetType.html) 


---

## 📂 Repository Structure

| File Name                                                | Description                                       |
|----------------------------------------------------------|---------------------------------------------------|
| `pallisate_building_damage.ipynb`                        | Full workflow: preprocessing, modeling, analysis  |
| `XGBoost_Predicted_Map_with_Legend_and_DatasetType.html` | Exported interactive map (hosted via GitHub Pages)|
| `Pallisade_point_data.csv`                               | Input dataset with spatial and spectral features  |
| `README.md`                                              | Project documentation                             |

---

## 📊 Dataset Description

The dataset includes:
- 9,543 building records
- Binary classification labels: Damaged / Undamaged
- NDVI & NBR indices (pre/post)
- Terrain slope (from DEM)
- Wind data (Global Wind Atlas)
- Land cover (NLCD)

Dataset available here : "https://github.com/bsatyavs/Pallisade-Wildfire/blob/main/Pallisade_point_data.csv"
---

## 🧩 Dependencies and Libraries

```python
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split, GridSearchCV
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.ensemble import RandomForestClassifier, StackingClassifier
from sklearn.svm import SVC
from sklearn.linear_model import LogisticRegression
from xgboost import XGBClassifier
from sklearn.metrics import (classification_report, confusion_matrix,
                             accuracy_score, precision_score, recall_score, f1_score)
import geopandas as gpd
import folium
from folium import GeoJsonTooltip
import matplotlib.pyplot as plt
import seaborn as sns
