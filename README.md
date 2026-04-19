# Monte Carlo options pricing — PETR4

Monte Carlo simulation for European and American put option pricing on PETR4 (Petrobras) using Geometric Brownian Motion and the Longstaff-Schwartz algorithm.

## Research question

*How do European and American put prices compare for PETR4 under GBM assumptions, and what is the early exercise premium?*

## Approach

1. **Data** — PETR4 daily prices via yfinance, IPCA deflation via BCB API
2. **GBM calibration** — historical drift and volatility estimated from log-returns
3. **European put** — standard Monte Carlo with antithetic variates
4. **American put** — Longstaff-Schwartz least-squares regression for early exercise boundary
5. **Convergence analysis** — price stability as number of simulations increases

## Key results

- GBM parameters calibrated on real PETR4 price history
- American put price > European put price — early exercise premium quantified
- Convergence achieved with ~10,000 simulations
- Results robust to IPCA deflation of historical series

## Data

- Source: yfinance (PETR4.SA) · BCB API (IPCA)
- Frequency: daily
- Deflation: real prices using IPCA from Banco Central do Brasil

## Stack

Python · numpy · pandas · yfinance · matplotlib · scipy

## Structure

```
├── notebook.ipynb    ← main notebook
└── README.md
```

## How to run

```bash
pip install numpy pandas yfinance matplotlib scipy requests
jupyter notebook notebook.ipynb
```

## Structure
