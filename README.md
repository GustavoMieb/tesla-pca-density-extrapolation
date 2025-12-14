# PCA, Density Modeling and Polynomial Extrapolation (Tesla Deliveries 2015–2025)

Multivariate analysis project applying Principal Component Analysis (PCA) to a Tesla
deliveries/production dataset (2015–2025). The project includes:

- EDA and correlation analysis
- PCA implemented **from scratch** (standardization, covariance, eigendecomposition)
- Loadings-based interpretation of components (PC1, PC2, ...)
- Continuous **PDF/CDF estimation for PC1** using polynomial fitting + Simpson integration
- Polynomial extrapolation to explore technical and environmental scenarios

## Dataset
Monthly records with:
- Deliveries, production, avg price
- Battery capacity and range
- CO2 saved and charging stations
- Labels (Year, Month, Model, Region) used for interpretation

## Key Findings
- Strong correlations justify PCA (e.g., production vs deliveries, battery vs range).
- PC1 behaves as an operational intensity index (volume + CO2 impact).
- PC1 shows near-zero correlation with time (ρ ≈ 0.01), suggesting a synthetic time pattern.

## Methods
- PCA from scratch: z-score standardization, covariance matrix, eigenvalues/eigenvectors, projection, explained variance, loadings.
- Density/CDF for PC1:
  - histogram midpoint sampling
  - polynomial fit via Vandermonde + least squares
  - normalization by Simpson composite integration (∫pdf ≈ 1)
- Extrapolation:
  - battery capacity → range (degree-2 polynomial)
  - production → CO2 saved (degree-1 vs degree-2 comparison)

## Project Structure
```
tesla-pca-density-extrapolation/
├── README.md
├── requirements.txt
├── data/
│   ├── tesla_deliveries_dataset_2015_2025.csv
│   └── README.md
├── notebooks/
│   ├── ProyyectoTesla.ipynb
│   └── README.md
└── docs/
    └── PropuestraFinal2proyMMCD.pdf

```
## How to Run
pip install -r requirements.txt
Run notebooks/tesla_pca_analysis.ipynb 

