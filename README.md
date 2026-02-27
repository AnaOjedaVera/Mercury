# Mercury VIS–NIR Spectral Metrics, PCA, and Power BI Dashboard

## Summary
This project evaluates a broad set of VIS–NIR spectral descriptors to determine how well they differentiate major Mercury surface units using reflectance spectra. The methodology combines (i) descriptor-based feature engineering (e.g., curvature, slopes, color indices, reflectance channels, and band-depth indicators when applicable), (ii) variance-based statistical screening to identify strong individual discriminators, and (iii) Principal Component Analysis (PCA) to assess multivariate structure and separability in a reduced space. The outcome is a reproducible pipeline that produces a cleaned, feature-rich dataset and PCA outputs, and then delivers an interactive exploration of the results through a Power BI dashboard.

---

## Findings
- Continuum-shape descriptors are the most informative for discriminating Mercury surface units in these subtle VIS–NIR spectra. In particular, **curvature metrics** provide the strongest single-metric separation, with the **UV curvature** parameter consistently showing the clearest differences across units.
- Slope metrics contribute useful, but weaker, discrimination compared with curvature. They help refine separability when used alongside curvature-related descriptors.
- Color indices are highly variable but not sufficient on their own to separate all units cleanly; however, they become important when combined with other metrics in multivariate space.
- PCA confirms multivariate separability, with Hollows forming a compact, clearly isolated cluster and residual overlap among the plains units (e.g., LRM/LRblueP/HRredP), consistent with transitional materials and mixing rather than sharp spectral boundaries.
- PCA loadings show that correlated behavior matters: despite curvature being the best individual discriminator, the dominant contributors to the reduced PCA structure are mainly color indices and slope-related metrics, indicating that multivariate separation is driven by combinations of correlated descriptors.
- Band-depth metrics are largely ineffective in this dataset: only weak detections (notably Mg–S–CaS and Fe²⁺-related parameters) exceed the threshold, with no visually prominent absorptions, so band depths provide limited discriminatory power for MASCS/VIRS spectra in this context.
- Overall, the paper delivers a reproducible metric-evaluation workflow (descriptor computation + variance ranking + PCA) that helps prioritize robust and interpretable features for classification and mapping, and is extendable to larger Mercury datasets and future VIS–NIR observations.

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
