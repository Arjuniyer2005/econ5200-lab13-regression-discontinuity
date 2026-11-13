# econ5200-lab13-regression-discontinuity
# Regression Discontinuity: Bandwidth Selection, Manipulation and Local Treatment Effects

## Objective

I examined how regression discontinuity (RD) estimates depend on bandwidth selection, potential manipulation around the cutoff, and the assumptions needed for causal identification.

## Methodology

- **Bandwidth Selection:** Compared global polynomial and local linear regressions using simulated grant data with a known treatment effect.
- **Bias-Variance Trade-off:** Evaluated seven bandwidths and used 300 simulations to compare their bias, variance, and RMSE.
- **Manipulation Testing:** Applied density tests to detect sorting around the treatment cutoff.
- **Covariate Continuity:** Tested whether pre-treatment characteristics changed discontinuously at the cutoff.
- **Lee (2008) Replication:** Examined the effect of narrow Democratic election victories on subsequent legislative voting scores.
- **Manual RD Estimation:** Implemented a local linear regression using triangular kernel weights and verified it against `rdrobust`.

## Key Findings

- **Polynomial Bias:** The global quadratic estimated an effect of 0.0357, compared with the true effect of 0.08. The local linear estimate was much closer at 0.0789.
- **Bandwidth Selection:** A bandwidth of 20 produced the lowest RMSE (0.0127), demonstrating the trade-off between bias and variance.
- **Manipulation:** The clean sample passed the density test (p = 0.965), while the manipulated sample failed (p = 0.0022).
- **Lee (2008):** Narrow Democratic victories increased subsequent ADA voting scores by approximately 46.49 points, highlighting the impact of party affiliation on legislative representation.
- **Verification:** My manual RD implementation reproduced the local linear estimates from `rdrobust`.

## Tools Used

Python, NumPy, Pandas, Statsmodels, Matplotlib, `rdrobust`, `rddensity`, and Google Colab.
