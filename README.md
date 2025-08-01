### Stock Market Prediction Model

**Sritha Kondragunta**

#### Executive summary

This project explores the use of Random Forest classification models to predict short-term and medium-term stock price movements for FAANG stocks (AAPL, AMZN, GOOGL, META, NFLX). By engineering features like RSI, OBV, and detrended price data, we train models to classify whether a stock will move up, down, or remain neutral over a 1-day and 30-day period. The performance of individual stock models is compared against a market-wide model, and feature importances are analyzed to interpret model decisions.

#### Rationale

Stock market forecasting is notoriously difficult, but even small improvements in classification accuracy can provide a significant edge in financial trading and risk management. By identifying which technical indicators are most predictive, this project adds transparency to the modeling process and explores whether models trained on one stock can generalize to others.

#### Research Question

Can we accurately classify and predict stock price direction (up, down, neutral) over 1-day and 30-day horizons using use historical financial and economic data?

#### Data Sources

All historical stock data was retrieved directly from Yahoo Finance using the open-source Python library yfinance. The dataset includes daily Open, High, Low, Close, and Volume (OHLCV) data for FAANG companies. This data was then used to compute technical indicators and generate the classification targets for model training.

#### Methodology
What methods are you using to answer the question?

1. Data Preparation:
    - Load and clean data (remove NaNs, filter per stock).
    - Engineer target labels for 1-day and 30-day classification.
2. Model Training:
    - Use RandomForestClassifier to predict target movement for each stock individually.
    - Train a "market-wide" model using all stock data combined.
3. Evaluation:
    - Accuracy is used to assess performance.
    - Compare stock-specific vs. general models.
    - Perform cross-stock testing to evaluate generalization.
4. Feature Importance Analysis:
    - Extract and plot feature importances from trained models.

#### Results
What did your research find?

The project produced two types of models: individual models trained per stock and a full market model trained on all available data.

The full market model achieved:
- 49.05% accuracy for 1-day predictions
- 69.33% accuracy for 30-day predictions

When the full model was tested on individual stocks (META, AMZN, AAPL, NFLX, GOOGL), performance improved significantly:
- 1-day prediction accuracies ranged from 88.79% to 90.93%
- 30-day prediction accuracies ranged from 93.16% to 94.48%

Cross-stock testing (e.g., testing AMZN data on a model trained on META) showed modest generalization:
- Most 1-day accuracies ranged from 47% to 53%
- 30-day accuracies ranged from 49% to 65%

These results suggest that while individual stock models perform very well on their own data, generalization across stocks is limited — indicating stock-specific behavior is important for prediction.


#### Next steps

- Incorporate LSTM Models: Long Short-Term Memory (LSTM) networks are designed to handle sequential data and may capture temporal patterns in stock prices better than tree-based models. 
- Perform rolling-window validation.

# Capstone
