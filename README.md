# stata-panel-did-analysis
Difference-in-differences analysis of a policy’s impact on country-level outcomes (7 countries, 1990-1999) using Stata.
# Stata Project for Econometrics II (2026) | Lahore School of Economics

## Research Question
Did a policy intervention change the target outcome variable `y` in treated countries relative to control countries?

## Data
- Dataset: `Panel101.dta` (Standard Stata panel dataset exercise)
- Sample: 7 countries (4 control countries: A, B, C, D; 3 treated countries: E, F, G)
- Period: 1990 to 1999 (10 consecutive years, strongly balanced panel)
- Total Observations: N = 70 (7 countries × 10 years)
- Policy Start: 1994 (`time = 1` for years 1994–1999)

## Method
- Difference-in-Differences (DID) estimation using linear regression in Stata (`reg y time treated did, vce(robust)`).
- Parallel trends assumption checked visually across the pre-treatment period (1990–1993).
- Regression models estimated using heteroskedasticity-robust standard errors (`vce(robust)`).

## Results
The policy implementation is associated with an estimated reduction of 2.52 billion units in outcome variable `y` for treated countries relative to control countries ($\hat{\beta}_{did} = -2.52 \times 10^9$). However, this effect is not statistically significant at the 5% level ($p = 0.088$), though it is significant at the 10% level.

## Limitations
- Small sample size (only 7 cross-sectional units / countries), leading to large standard errors and limited statistical power.
- The parallel trends assumption was evaluated visually rather than through formal statistical testing or pre-trend lead/lag interaction models.
- Standard errors were estimated with `vce(robust)` rather than clustered at the country level (`vce(cluster country)`), which may fail to account for within-panel serial correlation.

## Files
- `lab_assignment.do`: Complete Stata script containing data loading, variable generation, crosstabulations, graphing, and regression models and their explanations.
- `parallel_trends.png`: Line plot of group mean outcome variables over time (1990–1999).

## How to Run
1. Open `lab_assignment.do` in Stata 15 or higher.
2. Set the working directory to the folder containing `Panel101.dta`.
3. Execute the `.do` file from top to bottom.

## Author
Romaisa Kashif  
Undergraduate Student, BSc (Hons) Mathematics & Data Analytics  
Lahore School of Economics
