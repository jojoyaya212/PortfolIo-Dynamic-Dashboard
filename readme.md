# Dynamic Portfolio Simulation Dashboard

This project implements an **interactive portfolio simulation dashboard** for exploring the distributional and risk properties of a multi-asset portfolio under **correlated Geometric Brownian Motion (GBM)** dynamics.

Built in **Python using Jupyter Notebook and ipywidgets**, the dashboard allows users to dynamically adjust simulation parameters and instantly visualize how portfolio outcomes change. The focus is on **risk interpretation, scenario analysis, and intuitive exploration of uncertainty** rather than static modeling.

---

## Dashboard Preview

![Dynamic Portfolio Simulation Dashboard](assets/images/dashboard.png)

*Example output showing the distribution of final portfolio values, summary risk metrics, and system information rendered directly on the chart.*

---

## 1. Project Overview

The dashboard is designed to help users understand how portfolio outcomes depend on:
- Asset selection
- Correlation structure
- Simulation horizon
- Return frequency
- Portfolio weights
- Number of Monte Carlo repetitions

By adjusting these parameters interactively, users can observe how risk measures and outcome distributions respond in real time.

---

## 2. Data and Modeling Framework

### Data
- Historical price data is retrieved using **Yahoo Finance (`yfinance`)**
- Users can specify a custom set of tickers
- Returns are computed as **log returns**
- Supported return frequencies:
  - Daily
  - Weekly
  - Monthly

### Model
- Prices are simulated using **multivariate Geometric Brownian Motion**
- Drift and covariance are estimated from historical data
- **Cholesky decomposition** is used to generate correlated shocks
- Portfolio value is constructed from weighted individual asset paths
- Simulation is performed over a user-defined horizon

---

## 3. Interactive Dashboard Features

### Parameter Controls
The dashboard provides interactive controls for:
- Asset tickers (comma-separated)
- Portfolio weights (comma-separated, automatically normalized)
- Return frequency (daily / weekly / monthly)
- Simulation horizon (30, 120, 250, or 500 days)
- Number of simulation runs
- Histogram bin count

All parameters can be modified without restarting the notebook.

---

## 4. Dynamic Outputs and Risk Metrics

Each simulation run produces:
- A histogram of final portfolio values
- Mean of the final portfolio value
- Standard deviation of the final portfolio value
- Probability of a loss greater than 10%
- A summary of the selected assets and portfolio weights

All outputs update dynamically when the simulation is re-run.

---

## 5. System and Environment Transparency

For reproducibility, the dashboard displays **system and environment information directly on the output chart**, including:
- Operating system
- Python version
- NumPy version
- Pandas version
- yfinance version

This makes results easier to replicate across different environments.

---

## 6. Usage

1. Open the notebook in **Jupyter Notebook or JupyterLab**
2. Run all cells
3. Adjust parameters using the interactive controls
4. Click **Run simulation**
5. Explore how the distribution and risk metrics change

No external web server is required.

---

## 7. Design Notes

- `ipywidgets` are used for tight integration with Jupyter and fast iteration
- Input validation ensures robustness to invalid tickers or weights
- Cholesky-based correlation preserves realistic cross-asset dependence
- The dashboard emphasizes interpretability and user interaction over model complexity

---

## 8. Disclaimer

This project is for **research and demonstration purposes only**.

- Simulation results depend on historical data and modeling assumptions
- Geometric Brownian Motion is a simplified model and does not capture jumps, volatility clustering, or regime changes
- Outputs should not be interpreted as investment advice or forecasts

---

## 9. Author

**Ke Zhang**  
Portfolio Simulation & Risk Analysis Project
