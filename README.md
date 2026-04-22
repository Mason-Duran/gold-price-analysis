# Gold Price Analysis: Macroeconomic Drivers and Regime Shifts

This repository contains a statistical analysis of the factors influencing gold prices between 2011 and 2018. The project utilizes Multiple Linear Regression and One-Way ANOVA to evaluate the predictive power of the S&P 500, EUR/USD exchange rates, and crude oil prices. A significant portion of this work is dedicated to model diagnostics and the identification of structural breaks in financial time-series data.

## Key Technical Objectives
* **Feature Significance:** Quantified the inverse relationship between the S&P 500 and Gold prices.
* **Diagnostic Forensics:** Identified a major structural break in 2013 via residual analysis, uncovering distinct market regimes.
* **Assumption Validation:** Verified OLS and ANOVA requirements, including homoscedasticity, independence, and normality of errors.

## Technology Stack
* **Language:** Python
* **Libraries:** pandas, statsmodels, scipy, seaborn, matplotlib
* **Data Source:** Kaggle Gold Price Prediction Dataset

## Analysis Summary

### 1. Multiple Linear Regression
The model was optimized by removing silver to mitigate multicollinearity, allowing for a clearer assessment of broader macroeconomic drivers. 
* **S&P 500:** Identified as the primary predictor ($p < 0.001$). For every 1 standard deviation increase in the S&P 500, gold prices dropped by approximately $11.60.
* **EUR/USD & Oil:** Confirmed significant correlations, with the Euro showing a positive relationship and Oil showing a moderate inverse relationship during this period.

### 2. Seasonal ANOVA
A One-Way ANOVA was conducted to test for price variance across fiscal quarters.
* **Findings:** A statistically significant difference was found specifically between Q1 and Q4. 
* **Investor Insight:** With 95% confidence, gold prices averaged $2.79 to $11.14 lower in Q4 compared to Q1.

## Model Diagnostics and Limitations

The most critical insight from this analysis involves the bimodal residual distribution identified during validation. 

By color-coding the residuals by date, the data revealed two distinct "ribbons" separated by the 2013 gold market crash. 

* **Pre-2013 Regime:** High safe-haven demand resulted in systematic under-prediction by the linear model.
* **Post-2013 Regime:** The market established a new, lower baseline valuation relative to equities.

This diagnostic suggests that a standard linear approach struggles with long-term financial forecasting across different market regimes. Future iterations would benefit from regime-switching models or interaction terms to account for these shifts.

## Repository Structure
```text
├── data/               # 1,000-day random sample (CSV)
├── notebooks/          # Data cleaning and statistical modeling scripts
├── images/             # Residual plots and scatter matrix visualizations
├── results/            # Technical paper with formal results
└── requirements.txt    # Environment dependencies
```

This project was completed as part of the Applied Data Analytics program at Boston University
