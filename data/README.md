# Data Files

This folder contains parameter outputs from the Phyllome vertical farm analysis.

## Included files (tracked in git)

| File | Size | Description |
|------|------|-------------|
| `gompertz_params.csv` | ~7 KB | Fitted Gompertz growth parameters for each mini-season (A, k, tᵢ, R²) |
| `vanthoor_params.csv` | <1 KB | Calibrated Vanthoor mechanistic model parameters (ε_LUE, K, SLA, Rm, DM) |

## Large files (not tracked — obtain from AgVia data pipeline)

| File | Size | Description |
|------|------|-------------|
| `tray_microclimate.csv` | ~2.3 MB | 8,424 trays × 27 features after anisotropic IDW interpolation |
| `production_clean.csv` | ~1.2 MB | Cleaned harvest records (yield_g, growth_days, season, etc.) |
| `air_clean.csv` | ~9.3 MB | Hourly air sensor readings (temp, humidity, CO₂, VPD) |
| `water_clean.csv` | ~794 KB | Irrigation & nutrient-solution logs (EC, pH, water_temp) |

To re-generate these files, run the data-preparation pipeline on the raw farm exports,
or contact **diegofg94@gmail.com** for access to the full dataset.
