# Spatial Modeling of Plant Functional Group Vulnerability and Biodiversity Intactness in Savanna Ecosystems

This repository contains the full analytical pipeline, spatial datasets, Google Earth Engine (GEE) feature extraction scripts, and Python workflows for modeling non-linear Biodiversity Intactness Index (BII) responses across plant functional groups (**All Plants, Trees, Forbs, and Graminoids**) in North Central Nigeria.

The primary analysis is executed using XGBoost coupled with **5-fold spatial block cross-validation** to account for spatial autocorrelation and **TreeSHAP** to quantify non-linear tipping points and feature interactions.

---

## Repository Structure

```text
savanna-functional-groups-land-use/
├── LICENSE
├── README.md
├── Savanna_Functional_Groups_Vulnerability_Analysis.ipynb   # Main Jupyter/Colab notebook
├── Data/
│   ├── CSV/
│   │   ├── North_Central_Nigeria_OptionA_ML_Dataset.csv     # 9,001 out-of-fold sample points
│   │   └── Readme.md
│   ├── GEE_Scripts/
│   │   ├── GEE EXTRACTION SCRIPT FOR ALL VARIABLES.txt     # Earth Engine sampling workflow
│   │   └── REadme.md
│   ├── Maps/                                                # Spatial prediction rasters (PNG)
│   │   ├── BII_ALL_PLANTS_MAP.png
│   │   ├── BII_TREES_MAP.png
│   │   ├── BII_FORBS_MAP.png
│   │   ├── BII_GRAMINOIDS_MAP.png
│   │   ├── LUI_MAP.png
│   │   ├── ELEVATION_MAP.png
│   │   ├── RAINFALL_MAP.png
│   │   ├── SLOPE_MAP.png
│   │   └── Readme.md
│   └── Shapefile/                                           # Regional boundary files
│       ├── NORTH_CENTRAL_NG.*
│       └── NORTH_CENTRAL.*
└── Results/
    ├── Figures/
    └── Summary_Text/

# Comprehensive Usage & Reproduction Guide

This guide provides step-by-step instructions to execute the code, run the machine learning pipelines, and reproduce the analytical figures and spatial results from the **Savanna Plant Functional Groups Biodiversity Intactness Index (BII)** study.

---

## 1. System Requirements & Environment Setup

### Software Requirements
* Python 3.9+
* Google Earth Engine (GEE) Account (Optional: only needed if re-extracting spatial data)
* Jupyter Notebook or Google Colab environment

### Python Library Dependencies
The core pipeline requires the following packages:

```bash
pip install numpy pandas scikit-learn xgboost shap matplotlib seaborn geopandas rasterio
