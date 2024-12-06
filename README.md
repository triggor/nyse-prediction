# Predicting After Tax Return on Equity (ROE) for NYSE listed Companies 

## Team Members

- Sidra Zain [SidraOB](https://github.com/SidraOB)
- Igor T.
- Mehran Hassanzadeh

## Project Overview

The primary goal of this project is to develop a predictive model for After Tax Return on Equity (ROE) using key financial metrics. This analysis will focus on understanding how various financial indicators, including Accounts Payable, Accounts Receivable, Additional Income/Expense Items, Capital Expenditures, Capital Surplus, and Cash Ratio, influence ROE for companies listed on the New York Stock Exchange (NYSE).

### Data Preprocessing

- Addressed missing values, outliers, and inconsistencies within the dataset.
- Ensured uniformity across different companies and time periods by standardizing metrics.

### Exploratory Data Analysis (EDA)

- Conducted EDA to uncover trends, correlations, and patterns within the data.
- Created visualizations to illustrate the relationships between financial metrics and ROE, highlighting potential drivers of performance.

### Feature Selection

- #### Tree-Based Feature Importance
Utilized tree-based models to assess the correlation between various features and target variable.
- #### Linear Regression for Non-Linearity
Applied linear regression to capture non-linear relationships among the features.

#### Selected Features 

Accounts Payable, Accounts Receivable, Additional Income/Expense Items, Capital Expenditures, Capital Surplus, Cash Ratio

#### Target
After Tax ROE

### Predicting Return on equity (ROE) Using Multivariable Linear Regression Model

- Split the dataset into 75% training and 25% test sets to evaluate the model's performance.
- Developed a multivariable linear regression model to predict ROE based on selected features.
**Model equation:** The equation for the multivariable regression is:

$$
\text{After Tax ROE} = b_0 + b_1 \times (\text{Accounts Payable}) + b_2 \times (\text{Accounts Receivable}) + b_3 \times (\text{Add'l income/expense items})+ b_4 \times (\text{Capital Expenditures})+ \\ 
b_5 \times (\text{Capital Surplus})+ b_6 \times (\text{Cash Ratio})+ b_7 \times (\text{Pre-Tax ROE})+ b_8 \times (\text{Profit Margin})+ b_9 \times (\text{Pre-Tax Margin})\\+ b_{10} \times (\text{Misc. Stocks})+ b_{11} \times (\text{Changes in Inventories})+ b_{12} \times (\text{Inventory})+ b_{13} \times (\text{Other Financing Activities})\\ +b_{14} \times (\text{Current Ratio})+b_{15} \times (\text{Gross Margin})+b_{16} \times (\text{Income Tax})+b_{17} \times (\text{Minority Interest})+b_{18} \times (\text{Net Income})\\+b_{19} \times (\text{Net Income Applicable to Common Shareholders})+b_{20} \times (\text{Operating Margin})\\ +b_{21} \times (\text{Equity Earnings/Loss Unconsolidated Subsidiary})
$$

where:

- $b_0$ is the Return on equity when all the predictors are 0 (the intercept).
- $b_1$ is how much the ROE increases/decreases for each unit increase in Accounts Payable (the slope for Accounts Payable).
- $b_2$ is how much the ROE increases/decrease for each change in Accounts Receivable (the slope for Accounts Receivable) and similar for other predictors.

- Fitted the regression model to the training dataset.

- Evaluated the model’s performance using Root Mean Squared Prediction Error (RMSPE). RMSPE of 8.51% indicates that the model predicting ROE for NYSE-listed companies is fairly accurate, but the error margin means there’s an average deviation of 8.51% between actual and predicted ROE values. Predicting ROE with 8.51% accuracy may be acceptable for broader market insights, but it could be considered high for high-frequency trading or risk management.

- Analyzed the regression coefficients to understand how each variable influences ROE. Positive coefficients for Accounts payable, Add'l income/expense items, Capital Surplus, Cash Ratio, Pre-Tax ROE, Profit Margin, Misc. Stocks, Other Financing Activities, Net Income Applicable to Common Shareholders, Operating Margin, Equity Earnings/Loss Unconsolidated Subsidiary indicate that an increase in these predictors is associated with higher ROE.
