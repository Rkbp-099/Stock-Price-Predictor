# Stock-Price-Predictor

### Summary 
The aim of this study is to develop a real-time stock forecaster system using not only historical stock price data  but also incorporating some indicators used by intraday traders . 2 technical indicators i.e ema and vwap have been used in this study in addition to the stock price for making predictions. We had taken some stock prices of 15 mins frequency for training the model and predicting the stock price, i.e we predict the stock price after 15 minutes on the basis of current,previous few values of closing price,ema and vwap.

### Dataset Description
US stock markets historical data of intraday prices is available for free on many websites. For US stocks we will use AlphaVantage API which gives real-time stock prices as JSON objects and also historical data. We can get historical stock prices over a period of 5,10,15 minutes. A sample time-series is shown below. 
```json
{
    "2024-06-21": {
        "1. open": "173.9700",
        "2. high": "174.9600",
        "3. low": "171.4000",
        "4. close": "172.4600",
        "5. volume": "10182025"
    },
    "2024-06-20": {
        "1. open": "174.0800",
        "2. high": "174.2800",
        "3. low": "171.2200",
        "4. close": "173.9200",
        "5. volume": "4723078"
    },
}
```

### Results
#### Using CNN
| stock_symbol | train_rmse | test_rmse | train_mape | test_mape |
| ------------ | ---------- | --------- | ---------- | --------- |
| AAPL         | 0.18966    | 0.28142   | 0.07414    | 0.10955   |
| MSFT         | 0.43442    | 0.76339   | 0.09734    | 0.16676   |
| AMZN         | 5.38355    | 10.50368  | 0.09741    | 0.18189   |
| TSLA         | 3.20554    | 3.85980   | 0.32571    | 0.33540   |
| GOOGL        | 6.74588    | 9.73710   | 0.20111    | 0.26676   |
| NVDA         | 0.78250    | 1.05153   | 0.18070    | 0.29252   |
| BRK-B        | 0.39107    | 0.63105   | 0.09007    | 0.13602   |
| FB           | 1.20862    | 1.34771   | 0.31825    | 0.37715   |
| Average      | 2.29265    | 3.52196   | 0.17309    | 0.23325   |

#### Using MLP
| stock_symbol | train_RMSE | test_rmse | train_mape | test_mape |
| ------------ | ---------- | --------- | ---------- | --------- |
| AAPL         | 0.1856     | 0.2797    | 0.0805     | 0.1187    |
| MSFT         | 0.4576     | 0.8287    | 0.1028     | 0.1851    |
| AMZN         | 8.7015     | 15.6119   | 0.1691     | 0.3114    |
| TSLA         | 2.9172     | 3.6003    | 0.2671     | 0.2964    |
| GOOGL        | 4.3833     | 7.6320    | 0.1179     | 0.2004    |
| NVDA         | 0.5508     | 0.6999    | 0.1591     | 0.2086    |
| BRK-B        | 0.7627     | 1.1929    | 0.1989     | 0.2755    |
| FB           | 0.8991     | 1.3197    | 0.1987     | 0.3030    |
| Average      | 2.3572     | 3.8956    | 0.1618     | 0.2374    |

#### Using LSTM Bidirectional
| stock_symbol | train_RMSE | test_rmse | train_mape | test_mape |
| ------------ | ---------- | --------- | ---------- | --------- |
| AAPL         | 0.056      | 0.086     | 0.000      | 0.000     |
| MSFT         | 0.085      | 0.169     | 0.000      | 0.000     |
| AMZN         | 12.766     | 21.225    | 0.003      | 0.004     |
| TSLA         | 2.823      | 3.742     | 0.002      | 0.003     |
| GOOGL        | 7.357      | 12.794    | 0.002      | 0.003     |
| NVDA         | 0.354      | 0.367     | 0.001      | 0.001     |
| BRK-B        | 0.247      | 0.368     | 0.001      | 0.001     |
| FB           | 0.150      | 0.860     | 0.000      | 0.002     |
| Average      | 2.980      | 4.952     | 0.001      | 0.002     |

### Sample plot of price predicted and original price with time
![alt text](https://github.com/Rkbp-099/Stock-Price-Predictor/blob/main/Plots/Plot%20CNN%20LSTM.png?raw=true)

For more details please check out [report](https://github.com/Rkbp-099/Stock-Price-Predictor/blob/main/Report.pdf) for this project.