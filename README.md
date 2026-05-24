# NFL Fantasy Football — Coefficient of Variation Analysis

**Type:** Team Project · STATS 406

## Overview
Analyzed 14,283 player seasons of NFL PPR fantasy data from 2000-2023 using Monte Carlo simulation, bootstrapping, and Jackknife resampling to compare coefficient of variation (CV) across QB, RB, WR, and TE positions. Built Bayesian hierarchical models to predict 2023 season performance and provide data-driven fantasy draft strategy recommendations.

## Hypothesis
- **Null:** CV of all positions are the same (θQB = θRB = θWR = θTE)
- **Alternative:** CV of positions are significantly different

## Methods
| Method | Purpose |
|---|---|
| Monte Carlo (10,000 draws) | Estimate theoretical CV distributions per position |
| Bootstrap (1,000 iterations) | Estimate CV confidence intervals non-parametrically |
| Jackknife (5-fold) | Assess precision of bootstrap estimates |
| Bayesian GLM (brms/Stan) | Predict 2023 PPR scores with player random effects |

## Key Findings
- **Rejected the null hypothesis** — p < 2e-16 across all position pairs
- **QBs** have the lowest CV (most consistent) — any QB performs similarly, so draft late
- **TEs** have the highest CV and jackknife variance — elite TEs like Travis Kelce provide an outsized edge worth an early pick
- **WRs** offer the best combination of high posterior mean and manageable variance — optimal early-round targets
- Bayesian models achieved **94-100% credible interval coverage** across all four positions

## CV Results
| Position | Bootstrap CV | 95% CI |
|---|---|---|
| QB | ~0.51 | (0.48, 0.53) |
| WR | ~0.81 | (0.79, 0.83) |
| RB | ~0.86 | (0.84, 0.89) |
| TE | ~0.96 | (0.93, 0.99) |

## Draft Strategy Recommendation
1. Target standout WRs in rounds 1-2 — low CV, high point ceiling
2. Prioritize consistent positions (QB) over variable ones (TE) early
3. Draft TEs late but target elite options — the drop-off from best to second-best is statistically extreme

## Tech Stack
`R` `Monte Carlo Simulation` `Bootstrap` `Jackknife` `Bayesian Modeling` `brms` `Stan` `ggplot2`

## Files
- `NFL_Group_Project_Writing_Sample.pdf` — Full research paper with methodology, simulations, and analysis
