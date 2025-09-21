# Quant‑Lab

End‑to‑end quantitative finance and scientific computing in **Python, C++, SQL, R, Julia, and Java**.  
Focus: **research‑grade models, production‑style engineering, and reproducible results**.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Core Modules](#core-modules)
- [Project Catalog](#project-catalog)
- [Repository Layout](#repository-layout)
- [Getting Started](#getting-started)
- [Run & Test](#run--test)
- [Engineering Standards](#engineering-standards)
- [Reproducibility & Data Policy](#reproducibility--data-policy)
- [Roadmap Snapshot](#roadmap-snapshot)
- [License](#license)

---

## Executive Summary

**Quant‑Lab** is a multi‑language workspace that demonstrates:
- **Trading research**: backtesting, factor research, portfolio construction, microstructure.
- **Derivatives & rates**: pricing libraries, volatility modeling, curve building.
- **Risk**: VaR/ES, factor risk, scenario engines.
- **ML for markets**: leakage‑safe pipelines, tree/sequence models, meta‑labeling.
- **Infrastructure**: CI‑ready testing, configuration discipline, report generation, and data pipelines.

> Everything is organized for **clarity**, **tests**, and **one‑command reproducible reports**.

---

## Core Modules

- **Event‑Driven Backtester (Python)** — orders/fills, P&L, slippage/fees, walk‑forward evaluation.
- **Derivatives Pricing (C++)** — Black–Scholes + Greeks, CRR/American binomial, Monte Carlo (antithetic/stratified).
- **Portfolio Optimizer (Python + SQL)** — mean‑variance, constraints/turnover, transaction costs, report export.
- **High‑Frequency LOB Simulator (C++)** — price/time priority, inventory control, latency knobs, microstructure stats.
- **Risk Engine (Python + SQL)** — Parametric/Hist/MC VaR, ES; Kupiec/Christoffersen backtests.
- **Time‑Series & Volatility Lab (R/Julia/Python)** — ARIMA toolkit, GARCH family, Kalman/state‑space models.
- **SABR Surface Calibration (C++/Julia)** — α, β, ρ, ν fitting; Hagan expansion vs Monte Carlo validation.
- **Microstructure Studies (Python)** — time/volume/dollar bars, imbalance bars, trade‑sign autocorrelation.
- **ML Alpha Lab (Python)** — leakage‑safe feature stores, tree & sequence models for returns/volatility, meta‑labeling.
- **Backtest → Report CLI (Python)** — one command to run, score, and export HTML dashboards.

---

## Project Catalog

### 0) Practice Rhythm
- Daily LeetCode (general + quant sets), probability drills, mental‑math speed sessions.

### 1) Python — Core Buildout
- **Monte Carlo Option Pricer** — GBM paths, Greeks; numerically stable estimators (Welford); online updates.
- **Event‑Driven Backtester v1** — crossover/Bollinger/MACD; orders/fills, P&L, stats; commissions; walk‑forward.
- **Risk Metrics Pack** — CAGR, vol, Sharpe/Sortino, Calmar, max drawdown, hit rate; rolling & duration analytics.
- **Portfolio Plumbing** — weights→returns, turnover, transaction costs; constraints (leverage, sectors).
- **Factor Loader** — exposures to MKT/SMB/HML/MOM/QMJ/BAB; rolling betas; factor attribution; Bayesian shrinkage (opt.).

### 2) C++ — Performance & Pricing
- **Black–Scholes & Greeks** — pricing + Δ/Γ/Θ/vega/rho; parity tests; implied vol via Brent/Newton; unit tests.
- **Binomial/American Pricer** — CRR, early exercise; trinomial (opt.); Greeks via bump‑and‑revalue.
- **Monte Carlo Engine (C++ vs Python)** — RNGs, variance reduction; Sobol quasi‑MC; barrier options.
- **Limit Order Book Simulator** — event‑driven, queue priority; latency controls; microstructure statistics.

### 3) SQL — Data Engineering
- **Trade Warehouse** — star schema for trades/orders/positions; P&L by desk/strategy/instrument/day; window VaR.
- **ETL DAG** — raw→clean→feature store; idempotent loads; late data handling; slowly‑changing dimensions.
- **Query Optimizer Lab** — EXPLAIN plans, indexes, partitions; before/after runtime reports; materialized views.

### 4) Integrated Systems
- **Portfolio Optimizer** — pull data (Py), store (SQL), optimize (Py), export reports.
- **High‑Frequency Simulation** — C++ LOB core + Python analytics.
- **Risk System** — SQL trade store; Python VaR (var‑cov, historical, MC).
- **Full Trading System Backtester** — ingest→strategy→store→dashboard pipeline.
- **Derivatives Pricing Library (C++)** — BS/Binomial/MC/Greeks.
- **ML Project** — volatility/return forecasting via time‑series models.

### 5) Time‑Series & Volatility
- **ARIMA Toolkit** — ACF/PACF, MLE; walk‑forward evaluation; seasonality/holiday effects.
- **GARCH(1,1)+** — vol forecasting; VaR backtests (Kupiec/Christoffersen); EGARCH, t‑innovations.
- **State‑Space + Kalman** — trend/level/AR state models; smoothing vs filtering; time‑varying betas.

### 6) Derivatives / Rates
- **Yield Curve Bootstrap** — deposits/futures/swaps → zero & forward curves; monotone splines (PCHIP).
- **SABR Surface Calibrator** — surface fits across maturities; Hagan vs MC checks.
- **Greeks Heatmaps** — Δ/Γ/vega grids by K,T; risk‑neutral density extraction (opt.).

### 7) Risk / Attribution
- **Multi‑Method VaR** — parametric, historical, MC; consistent backtesting; stressed VaR/ES.
- **Factor Risk Model (from scratch)** — cross‑sectional factor returns & betas; GLS, shrinkage; attribution.
- **Scenario Engine** — shock curves/FX/vol; portfolio repricing; correlated shocks (copulas).

### 8) Portfolio Construction / Optimization
- **Mean‑Variance Suite** — frontier, tangency, constraints; turnover & cost models; Black–Litterman (opt.).
- **Kelly / Fractional Kelly** — sizing under uncertainty; drawdown vs growth; Bayesian Kelly (opt.).
- **Hierarchical Risk Parity** — HRP vs MVO vs equal‑risk; regime‑switching variants (opt.).

### 9) Alpha Research / Signal Craft
- **Momentum & Reversal** — rank/weight/neutralize; industry/β‑neutral variants; decay/half‑life studies.
- **Seasonality Almanac** — DOW/turn‑of‑month; multiple testing (BH); cross‑asset meta‑analysis.
- **News/Sentiment (Light NLP)** — headline sentiment → event windows; leakage guardrails; CARs.

### 10) High‑Frequency / Microstructure
- **Trade‑Sign Autocorrelation** — signed order flow memory; impact vs volume; Hasbrouck lambda (opt.).
- **Tick‑to‑Bar Aggregation** — time/volume/dollar bars; imbalance bars; robustness tests.
- **Queue‑Aware Execution** — join vs take; fill‑probability models; POV/TWAP/IS comparisons.

### 11) ML for Markets
- **Feature Store v1** — leakage‑free pipelines; lagged returns, vol, microstructure, factors.
- **Tree Models (XGB/LGBM)** — cross‑sectional ranks → portfolio; group CV; SHAP stability checks.
- **RNN/Temporal CNN** — vol forecasting; calibration curves; multi‑horizon w/ quantile loss.
- **Meta‑Labeling** — CUSUM labeling, barrier outcomes; bet‑sizing via prob calibration.

### 12) Alternative Data / NLP
- **Earnings Call Embeddings** — FinBERT/embeddings; event‑aligned t‑stats; topic drift (NMF/LDA).
- **Web‑Scraped Macro Proxy** — simple proxy vs macro series; out‑of‑sample predictive tests.

### 13) Math / Numerics
- **Root‑Finding & Optimization Kit** — Brent/Newton/BFGS/ADAM; line search; mini auto‑diff lib.
- **Covariance Estimators Zoo** — sample vs Ledoit‑Wolf vs Oracle; downstream portfolio stability; graphical lasso.
- **Stochastic Calculus Playground** — Euler‑Maruyama/Milstein; GBM/Heston paths; strong vs weak order.

### 14) Infrastructure / Production
- **Backtest → Report CLI** — one command: run tests & export HTML.
- **Realtime Pipeline Mock** — ingest→feature→signal→order→risk; failure modes; latency budgets.
- **Config & Secrets Discipline** — YAML configs, env secrets, logging; deterministic seeds; run manifests.
- **Experiment Tracking** — minimal tracker (e.g., MLflow‑style) for runs & metrics.

### 15) Light “Drill” Projects
- Pure‑NumPy regression (no loops), O(n) rolling max drawdown, winsorize/clip, anti‑survivorship joins,
  return bucketing, discrete delta‑hedging P&L, IV surface interpolation, Greeks unit tests,
  SQL window‑function kata, calendars/holidays, outlier detection, Sharpe CIs (block bootstrap),
  transaction‑cost models, position sizers (vol‑targeting), regime detection (Markov switching),
  Kelly vs risk parity, copula samplers (Gaussian/t), robust skew/kurtosis, PACF (Durbin‑Levinson),
  CUSUM filter, leakage unit tests, resampling (time/volume/dollar), Dockerfile+Makefile.

---

## Repository Layout

```
Quant-Lab/
├─ python/        # strategies, analytics, ML, reporting
├─ cpp/           # pricing libraries, simulators, HPC tools
├─ sql/           # schemas, ETL DAGs, window-function analytics
├─ r/             # econometrics, forecasting, risk
├─ julia/         # scientific computing, optimization, autodiff
├─ java/          # concurrent components, optimizers
├─ notes/         # short design docs & references
└─ README.md
```

Each project includes:
```
project/
  ├─ src/         # implementation
  ├─ tests/       # unit tests (pytest / Catch2 / GoogleTest)
  ├─ data/        # small samples or pull script
  └─ README.md    # goal • method • results • reproduce
```

---

## Getting Started

Clone and enter:
```
git clone https://github.com/<user>/Quant-Lab.git
cd Quant-Lab
```

---

## Run & Test

**Python**
```
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pytest -q
```

**C++**
```
cmake -S . -B build
cmake --build build
ctest --test-dir build --output-on-failure
```

**R / Julia / Java**
- See project-level READMEs (e.g., `renv`/`packrat`, `Project.toml`, Gradle/Maven).

---

## Engineering Standards

- **Tests** — unit tests in `tests/`; CI‑ready layout.
- **Reproducibility** — fixed seeds; scripted data pulls; deterministic configs.
- **Clean History** — universal `.gitignore` excludes builds, caches, secrets.
- **Documentation** — per‑project README with run steps and results.
- **Security** — no credentials committed; use local `.env` files outside version control.

---

## Reproducibility & Data Policy

- Public repos use **tiny samples or synthetic data** for examples; large or proprietary datasets are excluded.
- Notebooks are exportable to HTML/PDF; reports render with fixed seeds for deterministic comparison.
- Where licenses apply (e.g., index constituents), only derived metrics or pointers are included.

---

## Roadmap Snapshot

Upcoming improvements: frontier visualizations & Greeks heatmaps; regime‑switching HRP; order‑book latency benchmarks; unified report CLI across languages; lightweight experiment tracker.

---

## License

Released under the **MIT License**. See `LICENSE`.
