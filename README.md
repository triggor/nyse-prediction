# Stock Price Movement Prediction 

## Team Members

- Sidra Zain [SidraOB](https://github.com/SidraOB)
- Igor T. 
- Mehran Hassanzadeh 

## Project Overview

The goal of our project is to develop a predictive model that forecasts whether the closing price of an S&P 500 stock will increase or decrease on the next trading day based on opening price, highest price, lowest price, adjusted close price, and trading volume.

### Potential Users of the Predictive Model

## Data Description

We are using stock prices dataset from [New York Stock Exchange](https://www.kaggle.com/datasets/dgawlik/nyse?resource=download&select=prices-split-adjusted.csv)
The dataset covers the period from 2010 to the end of 2016 and includes stock data for 501 companies listed on the S&P 500 index. It consists of 851,264 individual data points, each representing daily stock market information for a specific company.

Key features used for prediction include:

- Opening Price
- Highest Price
- Lowest Price
- Adjusted Close Price
- Trading Volume

The dataset includes adjustments for 140 stock splits, recorded in the file `prices-split-adjusted.csv`. Past prices are retroactively adjusted to match the current scale of the stock price after all the splits during the 2010–2016 period. This ensures that the historical prices are comparable to today's prices, making it easier to analyze the stock's performance over time.

### Required Libraries

**Pandas:** For data manipulation and analysis.
**Numpy:** For numerical operations and handling arrays.
**Scikit-learn:** For building and evaluating machine learning models.
**Matplotlib.pyplot:** For creating visualizations like charts and plots.
**Seaborn:** For statistical data visualization, providing an interface for creating complex visualizations easily.
**Shap:** For model explainability, to analyze how individual features contribute to model predictions.

### Data Preprocessing

- Target variable is created to predict if the next day's closing price will be higher (1) or lower (0) than the current day's closing price.
- Addressed missing values, outliers, and inconsistencies within the dataset.
- Created new features daily_return and volatility to enhance the predictive model.
- Applied One Hot Encoding to encode the categorical column.

### Exploratory Data Analysis (EDA)

- Plotted histograms to visualize the distribution and identify patterns, skewness, or outliers in the data.
- Computed the correlation matrix for selected numerical features and the target variable.
- Visualized the correlations using a heatmap to understand relationships between features and the target.


### Model Development 

### Model Evaluation

### Results

### Conclusion