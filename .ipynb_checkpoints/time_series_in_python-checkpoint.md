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
|no| description|
|---|---|
|1. |set a goal.
|2. |determine what must be forecasted to achieve our goal.
|3. |set the horizon of the forecast.
|4. |gather the data.
|   |`iteration step`|
|5. |develop a forecasting model.|
|6. |deploy to production.|
|7. |monitor.|
|8. |collect new data.|

the difference between time-series forecasting and regression analysis:
1. time-series have an order.
2. time-series sometimes don't have features.

> berenti di halaman 14

the only way to know that a model is good or performant is to compare it to a baseline. baseline model is a trivial solution to your forecast problem it relies on on heuristics or simple statistics and usually the simplest solution.

> berenti di halaman 30

# going on random walk

random walk is a series whose first difference is stationary and uncorrelated. this means the process moves completely at random.

how to identify random walk:
1. gather data
2. is data stationary? if no, apply transformation.
3. plot acf
4. is there autocorrelation? if no, then random walk. if yes, not a random walk.

if the mean, variance, and autocorrelation doesn't change over time, then the time series dataset is stationary. transformation in time series is a mathematical operation applied to a time series in order to make it stationary. differenecing is the tranformation that calculates the change from one timestep to another.

augmented dickey-fuller test helps us to determine if time series is stationary or not. the null hyphotesis: there is a unit root present in a time series. if the test reject the null hyphotesis, the dataset is stationary.

autocorrelation function measures linear relationship between lagged values of a time series.

~~~python
from statsmodels.tsa.stattools import adfuller
from statsmodels.graphics.tsaplots import plot_acf

series = # time series dataset
stat, p = adfuller(series)

if p > 0.05:
    print(f'we fail to reject null hyphotesis. the dataset is not stationary')
else:
    print(f'we reject null hypothesis. the dataset is stationary.')

plot_acf(series, lags=20)
~~~

