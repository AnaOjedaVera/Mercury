# Mercury VIS–NIR Spectral Metrics, PCA, and Power BI Dashboard

## Summary
This project presents a reproducible methodology to compute and evaluate VIS–NIR spectral metrics from MESSENGER MASCS/VIRS reflectance spectra (0.4–1.45 µm), applied to 130 spectra sampling four Mercury surface units (LRM, HRP, LBP, Hollows). Metric relevance is assessed through (i) descriptor-based feature engineering (curvature, slopes, color indices, reflectance values, point-by-point spectral channels, and diagnostic band depths), (ii) variance-based statistical ranking, and (iii) PCA on standardized metrics to evaluate multivariate structure and separability. The workflow supports transparent metric prioritization and is paired with an interactive dashboard for unit-wise exploration; the dataset and code are provided in the project repository.

---

## Findings
- **Curvature metrics** dominate spectral variability and provide the strongest single-metric discrimination, with **ultraviolet curvature** (uv_curv) identified as the most effective individual parameter. Reported group means show strong separation (Hollows highest, LBP distinctly lower/negative). 
- Slope metrics show intermediate discriminative capability (useful but not definitive on their own), and are most informative when interpreted alongside curvature. 
- Color indices exhibit higher variability than absolute reflectance, but limited standalone separation across all units; they become more important in multivariate combinations. 
- PCA confirms clear separation in reduced space, with Hollows forming a compact, isolated cluster and minor/residual overlap among the plains units (explicitly: two LRM spectra and one HRP spectrum project within the LBP cluster). PC1 explains 91.02% and PC2 5.78% of total variance. 
- PCA loadings (|PC1|+|PC2|) are dominated by color indices and slope metrics, specifically the top contributors reported in Table 3: ci_750_415, ci_415_750, vn_sl, n_sl, uv_down, ci_750_950, v_sl, curv_300_600, W1415, W1365. This supports the paper’s point that correlated descriptors structure the PCA space even when curvature is the strongest individual discriminator. 
- Band-depth metrics show limited effectiveness in this MASCS/VIRS dataset: only weak Mg–S–CaS and Fe²⁺-related features are detected above threshold, with no visually prominent absorptions and no pyroxene-related detections across units. 
- Overall, the study delivers a reproducible metric-evaluation framework (variance ranking + PCA) that prioritizes robust, interpretable descriptors for surface-unit discrimination and is positioned as extendable to larger Mercury datasets and future observations. 

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
- **The Article**
  - `Revista_Mexicana_de_Astronomía_y_Astrofísica__RMxAA__LaTeX_template_and_guide_for_authors-R1.pdf`  

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
