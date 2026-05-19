# Phyllome Crop Modelling

Predictive yield modeling and financial evaluation for the **Phyllome vertical farm** (AgVia SpA, Chile).  
Data: Jun 2024 – Dec 2025 · Crop: Spinach · Farm layout: 4 columns × 12 shelves × 18 rows (8,424 trays).

---

## Repository Structure

```
phyllome-crop-modelling/
├── phyllome_crop_modelling.ipynb   # Main analysis notebook
├── data/
│   ├── tray_microclimate.csv       # 8,424 trays × 27 features (IDW-interpolated)
│   ├── production_clean.csv        # Cleaned harvest records
│   ├── gompertz_params.csv         # Fitted Gompertz growth parameters per tray
│   ├── vanthoor_params.csv         # Vanthoor mechanistic model parameters
│   ├── air_clean.csv               # Hourly air sensor data
│   ├── water_clean.csv             # Irrigation / nutrient-solution records
│   └── raw/                        # Raw exports from the farm system
├── requirements.txt
└── LICENSE
```

---

## Notebook Sections

| # | Section | Key Output |
|---|---------|-----------|
| 1 | Data Loading & Quality Control | Cleaned microclimate + harvest tables |
| 2 | Anisotropic IDW Interpolation | 8,424-tray microclimate map (α=3 vertical) |
| 3 | Exploratory Data Analysis | Correlation heatmap, PPFD vs. yield scatter |
| 4 | OLS Regression | R²=0.61, VIF diagnostics |
| 5 | Random Forest + LOSO-CV | Feature importance (permutation + MDI) |
| 6 | Gompertz Growth Curves | Per-tray k, A, t₀ with 95% CI |
| 7 | Vanthoor Mechanistic Model | MAPE=31.3%, ε_LUE=1.673, K=0.80 |
| 8 | Financial Bridge | R/m²/yr = Y×P − OPEX − CAPEXamort |
| 9 | Monte Carlo Simulation | Profitability probability, tornado chart |
| 10 | Operating Window Optimization | PPFD × Photoperiod → viable region |

---

## Financial Framework

$$R_{m^2/yr} = Y \times P - \text{OPEX} - \text{CAPEX}_{amort}$$

| Parameter | Value |
|-----------|-------|
| P (spinach price) | $8 /kg |
| OPEX | $120 /m²/yr |
| CAPEX amortisation | $45 /m²/yr |
| **Break-even yield Y\*** | **20.6 kg/m²/yr** |

**Key findings:**
- PPFD 180 µmol/m²/s → mean Y ≈ 11 kg/m²/yr → **not viable**
- PPFD 310 µmol/m²/s → mean Y ≈ 26 kg/m²/yr → **viable (~$43/m²/yr)**

---

## Installation

```bash
pip install -r requirements.txt
jupyter notebook phyllome_crop_modelling.ipynb
```

Python 3.9+ recommended.

---

## Citation

If you use this work, please cite:

> Fernández, D. (2026). *Phyllome Vertical Farm Crop Modelling*. AgVia SpA, Chile.  
> GitHub: https://github.com/diegofg94/phyllome-crop-modelling

---

## License

MIT — see [LICENSE](LICENSE).
