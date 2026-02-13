# AI Audit Appendix (Assignment 04)

## Tool(s) Used
- GitHub Copilot (integrated in VS Code)

## Task(s) Where AI Was Used
- Implementing OLS regression functions in assignment04_regression.py (estimate_regression, save_regression_summary, plot_scatter_with_regression, print_key_results)
- Filling out the coefficient comparison table in assignment04_report.md
- Completing the interpretation sections in assignment04_report.md (slope interpretation, statistical significance, model fit, omitted variables, summary)

## Prompt(s)
- "Fit simple linear regressions using statsmodels - Extract and interpret regression coefficients - Visualize relationships with scatter plots - Save results for the interpretation memo"
- "correct the error"
- "Model 1: ret ~ div12m_me** - Intercept (β₀): 0.1082 (SE: 0.006, p-value: 18.073) - Slope (β₁): [value] (SE: [value], p-value: [value]) - R²: [value] | N: [value] correct any errors and fill out the rest of this chart"
- "You estimated **three** simple OLS regressions of REIT *annual* returns on different predictors: [table]"

## Output Summary
- Generated complete Python code for fitting OLS regressions using statsmodels, saving summaries, creating scatter plots with regression lines, and printing key results
- Provided exact numerical values from regression output to fill the report tables
- Wrote economic interpretations for each predictor's relationship with REIT returns
- Identified statistical significance and model fit comparisons

## Verification & Modifications (Disclose • Verify • Critique)
- **Verify:** Ran the regression script to ensure it executes without errors, checked that output files are created, and validated regression coefficients match the statsmodels results
- **Critique:** Initial code had missing package installations in virtual environment (ModuleNotFoundError), and report had incorrect p-value (was t-stat instead)
- **Modify:** Installed required packages in .venv, corrected p-value in report, and accepted all other AI-generated code and interpretations as accurate
