# Mercury spectral metrics + PCA + Power BI dashboard

This repository contains a reproducible workflow to evaluate VIS–NIR spectral descriptors for Mercury surface units and visualize the results in a Power BI dashboard.

## Contents
- `notebooks/Code_Mercury.ipynb`  
  Runs the full methodology (feature/metric computation + PCA) starting from the input database `data/ana_groups.csv`.  
  It exports the processed dataset required by Power BI.

- `data/ana_groups.csv`  
  Input database required by the notebook.

- `data/groups_ana_features_bands_indicators_clean.csv`  
  Processed dataset exported by the notebook (and used by the dashboard).

- `dashboard/Mercury.pbix`  
  Power BI report. Requires `data/groups_ana_features_bands_indicators_clean.csv` to refresh.

## Quickstart

### 1) Create a Python environment and install dependencies
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt
