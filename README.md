# Mercury VIS–NIR Spectral Metrics, PCA, and Power BI Dashboard

## Article summary
This project evaluates a broad set of VIS–NIR spectral descriptors to determine how well they differentiate major Mercury surface units using reflectance spectra. The methodology combines (i) descriptor-based feature engineering (e.g., curvature, slopes, color indices, reflectance channels, and band-depth indicators when applicable), (ii) variance-based statistical screening to identify strong individual discriminators, and (iii) Principal Component Analysis (PCA) to assess multivariate structure and separability in a reduced space. The outcome is a reproducible pipeline that produces a cleaned, feature-rich dataset and PCA outputs, and then delivers an interactive exploration of the results through a Power BI dashboard.

---

## What is included in this repository
- **Jupyter Notebook (main workflow)**
  - `Code_Mercury.ipynb`  
  Runs the full methodology end-to-end, including feature computation and PCA.
- **Input database**
  - `ana_groups.csv`  
  Required input dataset for the notebook.
- **Processed / exported database (Power BI input)**
  - `groups_ana_features_bands_indicators_clean.csv`  
  Exported by the notebook and used by the Power BI report.
- **Power BI dashboard**
  - `Mercury.pbix`  
  Interactive report that requires the exported CSV above to refresh.

> **Important:** The Power BI dashboard depends on the CSV exported by the notebook, but I attached the CSVs needed in any case. 

---

## Workflow (recommended order)
1. **Run the notebook** (`Code_Mercury.ipynb`) using the input dataset `ana_groups.csv`.
2. The notebook **exports** the processed dataset:  
   `groups_ana_features_bands_indicators_clean.csv`
3. **Open the Power BI file** (`Mercury.pbix`) and **Refresh** to load the exported CSV.

---

## Requirements
### Python
- Python **3.9+** recommended (3.10/3.11 also OK)

### Python packages
Install the minimal dependencies needed to run the notebook (included in the firsts steps)

### Power BI
- **Power BI Desktop** (Windows) to open `Mercury.pbix` and refresh the data.

---
