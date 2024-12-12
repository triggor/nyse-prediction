# Stock Trend Analysis Using Deep Learning

## Project Overview

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
- The training process is conducted over a maximum of 300 epochs with a batch size of 512.

![image](https://github.com/user-attachments/assets/889573ac-72a4-4a1f-88b1-c4dc2e300c4e)

## Main Findings

### Results

- As training progresses, both the training and validation loss gradually decrease, indicating that the model is learning and improving.
- The validation accuracy shows a steady improvement, although it is still below 60%. This suggests that the model is able to make reasonable predictions, but there is room for improvement.
- The training accuracy also shows a steady increase, reaching about 60% by epoch 153, while the validation accuracy stabilizes around 58%.

#### Plotting Learning Curve

![ROC curve](https://github.com/user-attachments/assets/11ef17f3-d664-40bd-b47f-292043d3c596)

The training accuracy increases steadily, reflecting the model's improving performance on the training data but the validation accuracy increases upto a certain point (around epoch 50) and then stabilizes. The gap between the traing and validation loss/accuracy suggests some level of overfitting. 

#### Model Evaluation

![LSTM model evaluation metrics](https://github.com/user-attachments/assets/7e5d274e-35a8-44b4-92c4-643862073e50)

The overall performance metrics showed that the model is not well optimized yet. Recall is particularly low. ROC-AUC being near 0.5 indicates the model struggles to differentiate between classes effectively.

#### Confusion Matrix

![Confusion Matrix](https://github.com/user-attachments/assets/d7e59ca4-7cae-4017-be41-6a87c106fe78)

The model struggles to identify "Increase (1)" cases, as shown by the high number of false negatives (40,407).
The imbalance between true positives and false negatives suggests poor recall for class "Increase (1)."

#### ROC Curve

![ROC](https://github.com/user-attachments/assets/97a18251-fbb7-43aa-ac06-26c0b3b1d40c)

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
