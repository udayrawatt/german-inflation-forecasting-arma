# Forecasting Monthly German Inflation Using ARMA(1,1)

**Course:** Dynamic & Financial Econometrics  
**Institution:** Wroclaw University of Economics (Erasmus Exchange)  
**Author:** Uday Rawat  
**Grade:** 1.0 (highest distinction — German grading scale)   
**Date:** January 2026  

---

## Overview

This project investigates whether a univariate time-series model can 
reliably forecast monthly inflation in Germany. Using 358 monthly 
observations of Germany's Harmonized Index of Consumer Prices (HICP) 
from Eurostat (1996–2025), I specify, estimate, and evaluate an 
ARMA(1,1) model using Gretl.

---

## Research Question

Can a parsimonious ARMA(1,1) model capture the dynamics of German 
monthly inflation and produce accurate short-term out-of-sample forecasts?

---

## Key Findings

- Monthly German inflation is **stationary** (ADF test: τ = −7.64, 
  p < 0.001), justifying direct ARMA modelling in levels
- ARMA(1,1) estimated on 1996–2023 data with all coefficients 
  statistically significant:
  - AR(1) = −0.638 → strong mean reversion
  - MA(1) = +0.528 → shock persistence
- Out-of-sample forecast accuracy (2024:01–2025:11, 23 observations):
  - Mean Absolute Error: **0.293 percentage points**
  - Theil's U2: **0.645** → 35% improvement over naïve benchmark
- Main limitation: model over-smooths volatility and cannot anticipate 
  structural shocks (e.g. energy price surges)

---

## Methodology

| Step | Method |
|------|--------|
| Data transformation | Month-on-month % change in HICP |
| Stationarity testing | Augmented Dickey-Fuller (ADF) test |
| Model selection | ACF/PACF analysis + AIC/SC information criteria |
| Estimation | Exact Maximum Likelihood via Kalman Filter |
| Forecast evaluation | MAE, RMSE, Theil's U2 (out-of-sample) |

---

## Data Source

**Eurostat / FRED** — Germany HICP Monthly Index  
Series: `CP0000DEM086NEST`  
Link: https://fred.stlouisfed.org/series/CP0000DEM086NEST  
Sample: January 1996 – November 2025 (358 observations)

---

## Files

| File | Description |
|------|-------------|
| `inflation_monthly.csv` | Constructed monthly inflation series |
| `germany_hicp_fred.xlsx` | Raw HICP index data from FRED |
| `forecast_gretl_.xlsx` | ARMA(1,1) forecasts vs actuals (2024–2025) |
| `assignment_dfe.gretl` | Gretl script — full model estimation |
| `Inflation_Forecasting_Uday_Rawat.pdf` | Full empirical paper |
| `figures/` | Gretl output: ACF/PACF, ADF results, forecast plots |

---

## Tools

- **Gretl** — econometric estimation and forecasting
- **Microsoft Excel** — data construction and transformation
- **Eurostat / FRED** — data source

---

## Limitations & Further Research

The ARMA(1,1) is a useful baseline but has clear limits:
- Cannot incorporate exogenous variables (oil prices, exchange rates)
- Struggles with structural breaks (2021–2022 inflation surge)
- Extensions: SARIMA, VAR, regime-switching models

---

*Part of coursework for Dynamic & Financial Econometrics,  
Wroclaw University of Economics, Erasmus Exchange Programme 2025–2026*  
*Grade: 1.0 (highest distinction, German grading scale)*
