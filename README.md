# Solar PPA Pricing, Risk Analysis & Hedging Optimization

A Python project exploring how an offtaker can price and hedge a pay-as-produced solar Power Purchase Agreement (PPA) while managing price, volume, shape and capture risks.

## Objective

The project addresses the following question:

> **How should an offtaker price and hedge a solar PPA while managing price, volume and shape risks?**

Using public European power-market data, the analysis will model the hourly economics of a solar PPA, quantify its main market risks and compare alternative hedging strategies.

## Project Scope

### 1. Market Data & Solar Profile

- Collect and clean hourly day-ahead electricity prices
- Build or retrieve an hourly solar generation profile
- Align price and generation time series
- Analyze seasonality and negative-price periods
- Study the relationship between solar generation and power prices

### 2. PPA Valuation

The project will calculate:

- Solar capture price
- Capture rate
- Production-weighted market revenues
- Historical merchant revenues
- PPA cash flows
- Price-generation correlation

Capture price is defined as:

**Capture Price = Σ(Pₜ × Qₜ) / ΣQₜ**

where:

- **Pₜ** = hourly electricity price
- **Qₜ** = hourly solar generation

Capture rate is defined as:

**Capture Rate = Solar Capture Price / Baseload Price**

### 3. Risk Analysis

The analysis will quantify the main risks of a pay-as-produced solar PPA:

- **Price risk** — changes in wholesale electricity prices
- **Volume risk** — deviations in solar production
- **Shape risk** — mismatch between the generation profile and standard hedge products
- **Capture risk** — deterioration of solar capture prices relative to baseload prices
- **Price-volume correlation risk** — high solar generation coinciding with lower electricity prices
- **Negative-price risk** — exposure to hours with negative day-ahead prices

### 4. Hedging Strategies

The project will compare:

1. **Unhedged exposure**
2. **Baseload forward hedge**
3. **Monthly / shaped hedge**
4. **Optimized hedge**

For each strategy, the analysis will compare:

- Cash-flow volatility
- Residual market exposure
- Hedge effectiveness
- Value at Risk (VaR)
- Conditional Value at Risk (CVaR)
- Downside performance

### 5. Hedge Optimization

Hedge ratios will be optimized using approaches such as:

- Variance minimization
- CVaR minimization
- Hedge-volume constraints
- Stress testing

The optimized strategies will be evaluated using out-of-sample historical backtesting.

## Methodology

Historical spot prices are used to study capture risk and to backtest hedging strategies.

**Historical spot prices are not treated as forward curves or executable PPA pricing inputs.**

A commercially executable PPA valuation would require contemporaneous forward curves, shaping assumptions, liquidity estimates, transaction costs, credit adjustments and other market inputs that may not be publicly available.

This project therefore focuses on **historical risk analysis, hedge design and quantitative methodology**, rather than presenting historical backtests as tradable forward valuations.

## Technology

- Python
- pandas
- NumPy
- SciPy
- statsmodels
- cvxpy
- Matplotlib
- Plotly
- Jupyter

## Repository Structure

    solar-ppa-pricing-hedging/
    ├── README.md
    ├── requirements.txt
    ├── notebooks/
    │   ├── 01_market_data_and_capture.ipynb
    │   ├── 02_ppa_valuation_and_risk.ipynb
    │   └── 03_hedging_and_optimization.ipynb
    ├── src/
    │   ├── data.py
    │   ├── valuation.py
    │   ├── risk.py
    │   ├── hedging.py
    │   └── optimization.py
    ├── data/
    ├── tests/
    └── reports/

## Planned Outputs

The final project will include:

- Hourly market and solar datasets
- Capture-price and capture-rate analysis
- Negative-price analysis
- PPA cash-flow model
- Risk decomposition
- Baseload and shaped hedging strategies
- Optimized hedge ratios
- VaR and CVaR analysis
- Stress testing
- Out-of-sample backtesting
- Executive summary of commercial conclusions

## Data

The project will use only public or openly accessible market data.

Potential sources include European power-market transparency platforms and publicly available solar-generation datasets.

No proprietary trading data, internal company models or confidential information will be used.

## Disclaimer

This project is for educational and research purposes only.

It does not constitute investment advice, a tradable market quotation or a commercial PPA valuation.
