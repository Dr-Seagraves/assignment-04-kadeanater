# Assignment 04 Interpretation Memo

**Student Name:** Kade Hemmerling
**Date:** 2/13/2026
**Assignment:** REIT Annual Returns and Predictors (Simple Linear Regression)

---

## 1. Regression Overview

You estimated **three** simple OLS regressions of REIT *annual* returns on different predictors:

| Model | Y Variable | X Variable | Interpretation Focus |
|-------|------------|------------|----------------------|
| 1 | ret (annual) | div12m_me | Dividend yield |
| 2 | ret (annual) | prime_rate | Interest rate sensitivity |
| 3 | ret (annual) | ffo_at_reit | FFO to assets (fundamental performance) |

For each model, summarize the key results in the sections below.

---

## 2. Coefficient Comparison (All Three Regressions)

**Model 1: ret ~ div12m_me**
- Intercept (β₀): 0.1082 (SE: 0.0060, p-value: 0.0000)
- Slope (β₁): -0.0687 (SE: 0.0325, p-value: 0.0346)
- R²: 0.0018 | N: 2527

**Model 2: ret ~ prime_rate**
- Intercept (β₀): 0.2090 (SE: 0.0199, p-value: 0.0000)
- Slope (β₁): -0.0222 (SE: 0.0040, p-value: 0.0000)
- R²: 0.0118 | N: 2527

**Model 3: ret ~ ffo_at_reit**
- Intercept (β₀): 0.0973 (SE: 0.0092, p-value: 0.0000)
- Slope (β₁): 0.5770 (SE: 0.5675, p-value: 0.3093)
- R²: 0.0004 | N: 2518

*Note: Model 3 may have fewer observations if ffo_at_reit has missing values; statsmodels drops those rows.*

---

## 3. Slope Interpretation (Economic Units)

**Dividend Yield (div12m_me):**
- A 1 percentage point increase in dividend yield (12-month dividends / market equity) is associated with a -0.0687 change in annual return.
- Higher dividend yield is associated with lower returns, which might occur because REITs with high dividend yields could be distressed or facing financial difficulties, leading to lower stock performance.

**Prime Loan Rate (prime_rate):**
- A 1 percentage point increase in the year-end prime rate is associated with a -0.0222 change in annual return.
- The evidence suggests REIT returns are sensitive to interest rates, with higher rates associated with lower returns, likely due to increased borrowing costs and competition from fixed-income investments.

**FFO to Assets (ffo_at_reit):**
- A 1 unit increase in FFO/Assets (fundamental performance) is associated with a 0.5770 change in annual return.
- More profitable REITs (higher FFO/Assets) do not show a statistically significant association with higher returns in this simple regression.

---

## 4. Statistical Significance

For each slope, at the 5% significance level:
- **div12m_me:** Significant — The negative relationship between dividend yield and returns is statistically significant.
- **prime_rate:** Significant — The negative relationship between prime rate and returns is highly statistically significant.
- **ffo_at_reit:** Not significant — There is no statistically significant relationship between FFO/Assets and returns.

**Which predictor has the strongest statistical evidence of a relationship with annual returns?** The prime rate has the strongest statistical evidence, with the lowest p-value and highest t-statistic.

---

## 5. Model Fit (R-squared)

Compare R² across the three models:
- The prime rate explains the most variation in annual returns (R² = 1.18%), followed by dividend yield (0.18%) and FFO/Assets (0.04%). All R² values are low, suggesting that other unmeasured factors largely drive REIT returns.

---

## 6. Omitted Variables

By using only one predictor at a time, we might be omitting:
- Market returns: REITs are influenced by overall stock market performance, which could correlate with both predictors and returns.
- Inflation rates: Economic conditions affect both interest rates and REIT valuations.
- REIT-specific factors: Such as leverage, property type, or geographic concentration, which impact both profitability and returns.

**Potential bias:** If omitted variables like market returns are correlated with both the X variable (e.g., prime rate) and returns, our slope estimates may be biased toward zero, underestimating the true relationship.

---

## 7. Summary and Next Steps

**Key Takeaway:**
The prime rate shows the strongest relationship with REIT annual returns, with higher rates associated with lower returns, which is consistent with economic theory about interest rate sensitivity in real estate investments. Dividend yield also shows a significant negative relationship, while FFO/Assets does not demonstrate a reliable association. These findings suggest REITs are sensitive to macroeconomic conditions, particularly interest rates.

**What we would do next:**
- Extend to multiple regression (include two or more predictors)
- Test for heteroskedasticity and other OLS assumption violations
- Examine whether relationships vary by time period or REIT sector

---

## Reproducibility Checklist
- [x] Script runs end-to-end without errors
- [x] Regression output saved to `Results/regression_div12m_me.txt`, `regression_prime_rate.txt`, `regression_ffo_at_reit.txt`
- [x] Scatter plots saved to `Results/scatter_div12m_me.png`, `scatter_prime_rate.png`, `scatter_ffo_at_reit.png`
- [x] Report accurately reflects regression results
- [x] All interpretations are in economic units (not just statistical jargon)
