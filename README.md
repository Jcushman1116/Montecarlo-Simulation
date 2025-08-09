# Monte Carlo Stock Price Simulation

This project simulates possible future stock price paths using the Monte Carlo method, assuming the stock follows a **Geometric Brownian Motion (GBM)** — a continuous time random walk with drift. The project demonstrates how to use historical data to estimate the parameters of GBM, and then generate thousands of possible future price paths for a chosen stock.

## Features

- **Data Download**: Automatically fetches historical price data using [yfinance](https://github.com/ranaroussi/yfinance).
- **Data Analysis**: Computes log returns, mean, variance, drift, and volatility.
- **Monte Carlo Simulation**: Generates a large number of possible future price paths using GBM.
- **Visualization**: Plots both historical prices and simulated paths for intuitive understanding.
- **Parameter Estimation**: Estimates drift and volatility directly from historical log returns.

## How It Works

1. **Download Historical Data**:  
   Uses `yfinance` to fetch historical closing prices for a chosen stock (e.g., AAPL).

2. **Calculate Log-Returns**:  
   Computes daily log-returns, which are more suitable for modeling in a GBM framework.

3. **Estimate Model Parameters**:  
   - Mean (`μ`) and variance (`σ²`) of log-returns.
   - Drift term: `μ - (σ²/2)`.
   - Volatility (`σ`): standard deviation of log-returns.

4. **Simulate Price Paths**:  
   - Generates random numbers from a standard normal distribution.
   - Uses the GBM formula:  
     ```
     S_t = S_0 * exp( (drift * t) + (σ * sqrt(t) * Z) )
     ```
     where `Z` is a standard normal random variable.

5. **Monte Carlo Simulation**:  
   - Repeats the process for thousands of paths (`iterations`), over a defined future time horizon (`t_intervals`).

6. **Visualization**:  
   - Plots the historical prices, log-returns, and simulated future price paths.

## Requirements

- Python 3
- numpy
- pandas
- matplotlib
- scipy
- yfinance

Install requirements with:
```bash
pip install numpy pandas matplotlib scipy yfinance
```

## Usage

Open and run `MonteCarlo_DifferentPaths.ipynb` in Jupyter Notebook.

### Example Outline

1. **Import Libraries**
2. **Download Historical Data**
3. **Compute Log Returns**
4. **Estimate Parameters (Mean, Variance, Drift, Volatility)**
5. **Monte Carlo Simulation (with user-defined number of paths and horizon)**
6. **Plot Results**

## Notes

- You can change the stock ticker, date range, number of simulation paths (`iterations`), and time horizon (`t_intervals`) easily in the notebook.
- The simulation assumes returns are normally distributed and independent between days — an assumption that may not always hold in real markets.

## References

- [Geometric Brownian Motion (Wikipedia)](https://en.wikipedia.org/wiki/Geometric_Brownian_motion)
- [Monte Carlo Methods in Finance](https://www.investopedia.com/terms/m/montecarloanalysis.asp)
- [yfinance Documentation](https://github.com/ranaroussi/yfinance)

---

**Author:** Jonathan Cushman  
**Repository:** [Montecarlo-Simulation](https://github.com/Jcushman1116/Montecarlo-Simulation)
