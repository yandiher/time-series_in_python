``` time series in python by Marco Peixeiro```

# understanding time series forecasting

a time-series is a set of data points ordered in times.
the dataset was recorded at every hour, minute, month, or quarter. the examples of time series are a stock, a household's electricity consumption, or temperature outside.

there are three componenets of time series. there are trends, seasonal components, and residuals. seperating a time series dataset components is called decomposition. in decomposition, y is value and x is time.
- trends represent slow moving change in a time series. 
- seasonality components represent the pattern of season in time series.
- residuals represent the behaviour that cannot be explained by trends and seasonality componensts.

> berenti di halaman 8

forecasting is predicting future based on historical data and knowledge of future events that might affect forecast. roadmap time-series forecasting:
1. set a goal.
2. determine what must be forecasted to achieve our goal.
3. set the horizon of the forecast.
4. gather the data.
`repeat`
5. develop a forecasting model.
6. deploy to production.
7. monitor.
8. collect new data.

the difference between time-series forecasting and regression analysis:
1. time-series have an order.
2. time-series sometimes don't have features.

> berenti di halaman 14
