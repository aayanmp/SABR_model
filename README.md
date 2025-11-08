# SABR Caplet Pricing and Calibration

This project implements and calibrates a **SABR model** for pricing caplets under the risk-neutral forward measure.  
It was developed as part of the **ERDOS Institute Fall 2025 Quant Finance Bootcamp**.

---

### Overview

The project:
- Simulates **SABR** forward and volatility paths via Monte Carlo,
- Benchmarks against the **Black-76** and **Hagan (2002)** analytic approximations,
- Generates synthetic “market” data from a **Heston model**, and  
- Calibrates SABR parameters $(\alpha, \nu, \rho, \beta)$ to fit the observed (or simulated) volatility smile.

---

### Methodology

1. **SABR Simulation:** stochastic volatility model for the forward rate  
   \(df_t = \sigma_t f_t^{\beta} dW_t,\quad d\sigma_t = \nu \sigma_t dZ_t,\; \text{Corr}(dW_t,dZ_t)=\rho\)

2. **Monte Carlo Pricing:** simulate forward paths, compute discounted caplet payoffs.

3. **Black-76 Benchmark:** invert prices to implied volatilities.

4. **Hagan (2002) Approximation:** analytic link between SABR parameters and Black-style implied vol.

5. **Calibration:** minimize RMSE between model and “market” implied vols.
