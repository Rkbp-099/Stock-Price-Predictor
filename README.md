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
