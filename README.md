# StockSight-AI-Time-Series-Predictor

note: moved project over from my old github account. made in Dec 2024

Implemented a Transformer model with multi-head attention to predict AAPL stock price movements based on historical market
data using time series regression


## Features

- Utilizes the Transformer architecture with multi-head attention for time series regression.
- Predicts closing price movements for AAPL based on five market features: Open, High, Low, Close, Volume.
- Data sourced from Yahoo Finance.
- Data preprocessing includes MinMax scaling and dataset formatting for time series.
- Performance evaluated using RMSE, MAE, and R² coefficient.
- Easy to modify for other stocks/indices.

## Requirements

- Python 3.9 (tested with 3.9.12)
- numpy
- pandas
- matplotlib
- scikit-learn
- tensorflow
- yfinance

Install dependencies:
```sh
pip install numpy pandas matplotlib scikit-learn tensorflow yfinance
```



### Steps Performed in the Notebook

- Download AAPL historical data using yfinance.
- Scale features (`Open`, `High`, `Low`, `Close`, `Volume`) using MinMaxScaler.
- Format data with a sliding window (default 60 days) for input sequence.
- Split data into training and testing sets (default 80/20).
- Build the Transformer regression model.
- Compile the model with Mean Squared Error (MSE) loss and Mean Absolute Error (MAE) metrics.
- Train the model with early stopping.
- Evaluate predictions using RMSE, MAE, R².
- Visualize training loss and MAE over epochs.


## Evaluation

After training, metrics printed include:

- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² (Coefficient of Determination)

Typical output example (for 643 test samples):
```
Root Mean Squared Error (RMSE): 0.33
Mean Absolute Error (MAE): 0.31
R² (Coefficient of Determination): -6.84
```

## Modifying for Other Stocks

To adapt for other stocks, replace `'AAPL'` ticker in data loading lines:
```python
data = yf.download('AAPL', start='2010-01-01', end='2023-01-01')
```
Replace `'AAPL'` with your desired stock ticker.

## License

Feel free to use and modify for academic or personal use.
