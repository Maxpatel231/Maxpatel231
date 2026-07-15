# Hi, I'm Max

**MS Financial Mathematics @ University of Chicago · ex–Morgan Stanley Fixed Income · quantitative research & systematic trading**

I build research projects at the intersection of **systematic trading, market microstructure, fixed income, and portfolio risk**, pairing financial theory with careful statistical modeling and fully reproducible Python.

Before graduate school I was a **Fixed Income Analyst at Morgan Stanley**, supporting trading across U.S. Treasuries, mortgage-backed securities, and investment-grade credit. That desk experience shapes how I approach research: I care as much about avoiding look-ahead bias, modeling transaction costs, and validating out-of-sample as I do about the headline result.

📍 Graduating **December 2026** · recruiting for full-time **QR / QT / systematic / market-risk** roles.

---

## Projects at a Glance

| Project | Focus | Core methods |
|---|---|---|
| [Market Impact from Position Accumulation](https://github.com/Maxpatel231/Crypto-Market-Impact) | Execution / microstructure | Sweep aggregation, constrained NLS, trade-clock returns, OOS cross-validation |
| [Levered FX Carry](https://github.com/Maxpatel231/FX-Carry-Strategy) | Systematic macro / rates | Zero-curve bootstrapping, cross-currency funding, return attribution |
| [Financial Ratio Quantile Strategies](https://github.com/Maxpatel231/Financial-Ratio-Quantile-Strategies) | Cross-sectional equity | Point-in-time factors, long-short deciles, multi-factor combination |
| [CDS–Equity Predictive Modeling](https://github.com/Maxpatel231/cds-equity-predictive-model) | Credit relative value | Rolling regressions, residual isolation, regime analysis |

---

## Quantitative Research Projects

### [Estimating Market Impact from Position Accumulation](https://github.com/Maxpatel231/Crypto-Market-Impact)

Estimated the temporary price impact function $I(V)$ of aggressive crypto trades from high-frequency SOL-USDT and ETH-USDT data across multiple exchanges.

* Processed 100M+ nanosecond-resolution trade messages; aggregated fragmented fills into economically meaningful parent sweeps (VWAP, 1ms same-side grouping)
* Fit competing **square-root** ($r \sim \mu_0\sqrt{V}$) and **generalized power-law** ($r \sim \mu_1 V^{\mu_2}$) impact models via constrained nonlinear least squares
* Measured returns on a **trade-count clock** to normalize for non-uniform activity and multi-venue clock skew
* Validated out-of-sample with leave-one-day-out and quantile-range holdouts

**Result:** the estimated exponent $\mu_2$ clusters near **0.5** across both assets and venues (Bouchaud's square-root law holds in crypto spot), and impact is **temporary**, reverting within ~50–100 subsequent trades. Exchange liquidity shifts the *level* of impact but not its functional *shape*.

**Areas:** market microstructure · execution · nonlinear estimation · liquidity · high-frequency data
**Tools:** Python · Polars · Pandas · NumPy · SciPy · scikit-learn · Matplotlib

---

### [Levered FX Carry: Cross-Currency Bond Strategy](https://github.com/Maxpatel231/FX-Carry-Strategy)

Built a systematic emerging-market FX carry backtest structured as a leveraged cross-currency fixed-rate bond strategy.

* Constructed local-currency bond positions across **TRY, NGN, BRL, and ZAR**, funded via GBP borrowing linked to the Bank of England overnight rate
* Bootstrapped zero curves from swap yields and repriced bonds on updated curves with accrued-coupon cash flows
* Decomposed P&L into **rates, FX, and funding** components
* Stress-tested leverage, liquidity, transaction-cost, and crisis-correlation risk

**Areas:** FX carry · fixed income · curve construction · cross-currency funding · systematic macro
**Tools:** Python · Pandas · NumPy · SciPy · Bloomberg and public market data

---

### [Financial Ratio Quantile Strategies](https://github.com/Maxpatel231/Financial-Ratio-Quantile-Strategies)

Built and evaluated long-short equity strategies from accounting and valuation signals across **2,461 U.S. equities** (Jan 2018 – Jun 2023).

* Constructed debt-to-market-cap, return-on-investment, and price-to-earnings signals, then combined them into a multi-factor score
* Aligned fundamentals on **filing dates** (`merge_asof`) to eliminate look-ahead bias
* Formed monthly long-short decile portfolios; ran robustness across universe size, position sizing, and subperiods
* Evaluated annualized return, Sharpe, Sortino, drawdown, and win rate, with long/short attribution

**Result:** the combined multi-factor score delivered the **best risk-adjusted performance** of the signals tested, and standalone factors that were economically intuitive (e.g. low leverage) still failed in isolation, a clean illustration of why signal combination and honest out-of-sample evaluation matter.

**Areas:** cross-sectional equity research · factor investing · portfolio construction · backtesting
**Tools:** Python · Pandas · NumPy · PyArrow · Nasdaq Zacks Fundamentals

---

### [CDS–Equity Predictive Modeling](https://github.com/Maxpatel231/cds-equity-predictive-model)

Investigated whether idiosyncratic CDS spread movements carry information about subsequent equity returns.

* Removed broad equity-market exposure via rolling CAPM regressions; hedged CDS returns against equity and CDS-index factors to isolate firm-specific residuals
* Compared rolling **boxcar** and **exponentially weighted** predictive regressions
* Assessed coefficient stability, directional accuracy, and non-normal tail behavior

**Result:** after stripping systematic exposures, firm-specific CDS widening tends to precede weaker idiosyncratic equity returns, economically consistent with structural credit intuition, but the relationship is **regime-dependent**, strengthening in credit-stress periods.

**Areas:** credit markets · relative value · predictive regressions · time-varying relationships

**Tools:** Python · Polars · Pandas · NumPy · Numba · SciPy · statsmodels

---

## Technical Skills

**Languages:** Python (primary) · SQL · R · C++ (developing)

**Quantitative methods:** time-series analysis · regression · portfolio optimization · PCA · Monte Carlo simulation · volatility modeling · factor research · statistical backtesting

**Python ecosystem:** Pandas · NumPy · SciPy · Polars · statsmodels · scikit-learn · Numba · Matplotlib · Jupyter

**Financial domains:** fixed income · systematic trading · market microstructure · portfolio risk · derivatives · foreign exchange

**Research workflow:** point-in-time data alignment · out-of-sample cross-validation · transaction-cost awareness · Git/GitHub · reproducible pipelines · Bloomberg Terminal

---

## Research Interests

The through-line across my projects is how information and liquidity move between markets: credit leading equity, trade impact propagating across venues, and carry decomposing into rates, FX, and funding. I approach these with a fixed-income desk perspective, and across the full path from finding a signal, to executing it, to building it into a systematic strategy, to decomposing where its risk actually sits. What I trust are results that survive transaction costs, crisis regimes, and out-of-sample testing.


---

## Connect

[LinkedIn](https://www.linkedin.com/in/max-patel-mv1) · [Email](mailto:madhavf@uchicago.edu)
