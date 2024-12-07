# Stock Trend Analysis Using Deep Learning

## Project Overview

The goal of our project is to develop a predictive model that forecasts whether the closing price of an S&P 500 stock will increase or decrease on the next trading day based on opening price, highest price, lowest price, adjusted close price, and trading volume.

### Target Audience

- Financial Analysts and Traders looking for data-driven insights to enhance investment strategies and make more informed trading decisions.
- Investors seeking tools to predict market trends and make well-informed decisions about their investments.

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

## Methodology

#### Data Preprocessing

- Target variable is created to predict if the next day's closing price will be higher (1) or lower (0) than the current day's closing price.
- Addressed missing values, outliers, and inconsistencies within the dataset.
- Created new features daily_return and volatility to enhance the predictive model.
- Applied One Hot Encoding to encode the categorical column.
- Numerical features are scaled using the StandardScaler to ensure that all features contribute equally to the model.

#### Exploratory Data Analysis (EDA)

- Plotted histograms to visualize the distribution and identify patterns, skewness, or outliers in the data.
- Computed the correlation matrix for selected numerical features and the target variable.
- Visualized the correlations using a heatmap to understand relationships between features and the target.

#### Model Selection and Training

- An **LSTM-based neural network** is used for binary classification, where the model predicts whether the closing price will increase (1) or decrease (0) on the next day.
- The model consists of two LSTM layers with dropout for regularization, followed by dense layers and a final sigmoid activation for binary classification.
- The model is trained with early stopping to prevent overfitting. 
- The training process is conducted over a maximum of 50 epochs with a batch size of 128.

## Main Findings

### Results

- As training progresses, both the training and validation loss gradually decrease, indicating that the model is learning and improving.
- The validation accuracy shows a steady improvement, although it is still below 60%. This suggests that the model is able to make reasonable predictions, but there is room for improvement.
- The training accuracy also shows a steady increase, reaching about 57% by epoch 25, while the validation accuracy stabilizes around 56%.

#### Plotting Learning Curve

![ROC curve](https://github.com/user-attachments/assets/11ef17f3-d664-40bd-b47f-292043d3c596)

#### Challenges

### Conclusion

### Credits
This project was developed collaboratively by the following team members:

- **Igor T.**

- Developed and set up the GitHub repository for the project.
- Enhanced data cleaning and feature selection code, refining indicators to improve model performance.
- Contributed to the preparation of visualizations for model results and performance metrics.

- **Mehran Hassanzadeh**

- Built the deep learning model using LSTM (Long Short-Term Memory) for stock price prediction.
- Applied advanced techniques for model optimization and tuning to improve prediction accuracy.
- Implemented additional evaluation methods (e.g., cross-validation, hyperparameter tuning) to better assess and compare the models' performance.
- Designed and executed comprehensive Exploratory Data Analysis (EDA) to visualize data patterns, identify trends, and select key features for model building.

- **Sidra Zain [SidraOB](https://github.com/SidraOB)**

- Assisted in preprocessing the dataset.
- Coordinated and contributed to the final testing and model deployment process.
- Authored the README documentation to clearly communicate the project setup, implementation steps, and model evaluation.
