# Forecasting France's Solar Electricity Production

Time Series Analysis project (EPF Montpellier) comparing **ETS**, **SARIMA** and **Prophet** on monthly French solar electricity production (2014–2025), with a full methodological comparison (MSE/RMSE/MAE/MAPE/MASE, rolling-origin cross-validation, Diebold-Mariano test) and a 2026 forecast.

**Authors:** Enzo Augié, Etienne Girard

## Contents

- `TSA_Forecasting_France's_Solar_Electricity_Production_GIRARD_AUGIE.ipynb` — main notebook (data loading, EDA, decomposition, ETS/SARIMA/Prophet, comparison, 2026 forecast, business recommendations, conclusion, references, glossary)
- `requirements.txt` — Python dependencies
- `data/production-regionale-mensuelle-filiere.csv` — source dataset (see below)

## Data

- Source: ODRÉ / RTE, *Monthly regional electricity production by source*, [data.gouv.fr](https://www.data.gouv.fr/datasets/production-regionale-mensuelle-delectricite-par-filiere)
- Place the downloaded CSV at `data/production-regionale-mensuelle-filiere.csv` (or adjust the path in the first data-loading cell of the notebook).

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python -m ipykernel install --user --name=tsa-solar --display-name "Python (TSA solar)"
jupyter notebook
```

Then open the notebook and select the **Python (TSA solar)** kernel.

## Methods

ETS (Holt-Winters, AIC-selected) · SARIMA (ADF/KPSS, ACF/PACF, grid search by AIC, Ljung-Box) · Prophet (changepoints, Fourier seasonality) · seasonal-naive baseline · rolling-origin cross-validation (4 folds, 2022–2025) · Diebold-Mariano significance test.

## License

Academic project — EPF Montpellier, 2026.
