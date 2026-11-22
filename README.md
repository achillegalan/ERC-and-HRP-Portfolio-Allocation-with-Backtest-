# EURO STOXX 50 Portfolio Backtest

A Python backtest comparing **Equal Risk Contribution (ERC)** and **Hierarchical Risk Parity (HRP)** on EURO STOXX 50 equities. The project examines how covariance estimation and hierarchical clustering affect portfolio allocation, concentration, and realized risk.

## Methodology

Portfolios are rebalanced monthly using a rolling window of **504 trading days**. At each rebalance, assets must have observed returns on at least **95%** of the days in the estimation window to qualify.

- **Portfolio construction.** Compare ERC and HRP using sample covariance, constant-correlation shrinkage, and single-factor market shrinkage.
- **HRP sensitivity.** Compare four linkage methods and two allocation schemes, with optional removal of the first principal component before clustering.
- **Evaluation.** Compare cumulative returns, annualized volatility, and maximum drawdown. Track capital concentration with the Herfindahl–Hirschman Index, changes in target weights with L1 distance, and month-to-month cluster stability with the Rand index.

## Run the notebook

From the repository root, install the dependencies and open the notebook:

```bash
python -m pip install numpy pandas scipy scikit-learn matplotlib notebook
python -m notebook ex4b_notebook.ipynb
```

The notebook expects a daily price CSV at `data/sx5e_underlyings.csv`, with a `Date` column and one column per ticker. Run the cells in order to generate the portfolio weights, backtests, and charts.

## Repository structure

- [`ex4b_notebook.ipynb`](ex4b_notebook.ipynb) — Portfolio construction, experiments, and results.
- [`utilities/`](utilities/) — Covariance estimation, clustering, portfolio allocation, and backtesting functions.

## Credits

Developed for the Financial Engineering Buy-Side Laboratory at Politecnico di Milano.
