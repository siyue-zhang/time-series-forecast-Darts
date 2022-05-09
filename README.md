# time-series-forecast-Darts
Time series forecast is a very commen problem in many industries, like price forecast in financial investment, weather forecast for renewable energy production, sales forecast for business and so on. To solve this type of problem, the analyst usually goes through following steps: **explorary data analysis, data preprocessing, feature engineering, comparing different forecast models, model selection and evaluation**.

<image src=./images/workflow.JPG width=800>

## Case 1: Univariate Time-series Forecasting

The first case demonstrates a typical process of time series forecast of hourly wet bulb temperature in Singapore. Dataset is published by National Environment Agency, recorded at the Changi Climate Station from 1/1/1982 to 11/30/2021.

Link: https://data.gov.sg/dataset/wet-bulb-temperature-hourly

<image src=./images/sample.png>

## Case 2: Multivariate Time-series Forecasting

The second demonstrates a case study of multivariate time series forecast. It uses Jena Climate dataset recorded by the Max Planck Institute for Biogeochemistry. The dataset consists of 21 features such as temperature, pressure, humidity etc, recorded once per 10 minutes, from 01/01/2021 to 07/01/2021.

Link: https://www.bgc-jena.mpg.de/wetter/

Raw data include following parameters as example, the target is to predict future temperature:
* Temperature in Kelvin Tpot (K)
* Relative Humidityrh (%)
* Wind Speed wv (m/s)

<image src=./images/raw.png>

Correlation matrix indicates they are not highly correlated, thus not redundant.

<image src=./images/corr.JPG width=250>

Result shows the temperature forecast with three parameters does perform better than that with only one parameter.

<image src=./images/sample2.JPG width=700>

## Case 3: Probabilistic RNN Forecasting
  
Some models are able to do probabilistic forecasting by assigning likelihood function. By default `TimeSeries.plot()` shows the median as well as the 5th and 95th percentiles (of the marginal distributions, if the TimeSeries is multivariate). It is possible to control by setting low_quantile and high_quantile. Predicted object includes N_steps to forecast and N_samples to predicted at each step, as a data array of (N_steps, N_samples).
  
<image src=./images/prob.png>
  
## Darts

[darts](https://github.com/unit8co/darts) is a Python library for easy manipulation and forecasting of time series. It contains a variety of models, from classics such as ARIMA to deep neural networks. The library makes it easy to compare various models' performance, backtest models, and combine the predictions of several models and external regressors.

<p align=center>
<image src=https://github.com/unit8co/darts/raw/master/static/images/darts-logo-trim.png width=400>
</p>

Models available in DARTS: (7 Jan, 2022)
  
Model | Univariate | Multivariate | Probabilistic | Multiple-series training | Past-observed covariates support | Future-known covariates support | Reference
--- | --- | --- | --- | --- | --- | --- | ---
`ARIMA` | ✅ | | ✅ | | | ✅ |
`VARIMA` | ✅ | ✅ | | | | ✅ |
`AutoARIMA` | ✅ | | | | | ✅ |
`ExponentialSmoothing` | ✅ | | ✅ | | | |
`Theta` and `FourTheta` | ✅ | | | | | | [Theta](https://robjhyndman.com/papers/Theta.pdf) & [4 Theta](https://github.com/Mcompetitions/M4-methods/blob/master/4Theta%20method.R)
`Prophet` | ✅ | | ✅ | | | ✅ | [Prophet repo](https://github.com/facebook/prophet)
`FFT` (Fast Fourier Transform) | ✅ | | | | | |
`RegressionModel` (incl `RandomForest`, `LinearRegressionModel` and `LightGBMModel`) | ✅ | ✅ | | ✅ | ✅ | ✅ |
`RNNModel` (incl. LSTM and GRU); equivalent to DeepAR in its probabilistic version | ✅ | ✅ | ✅ | ✅ | | ✅ | [DeepAR paper](https://arxiv.org/abs/1704.04110)
`BlockRNNModel` (incl. LSTM and GRU) | ✅ | ✅ | ✅ | ✅ | ✅ | |
`NBEATSModel` | ✅ | ✅ | ✅ | ✅ | ✅ | | [N-BEATS paper](https://arxiv.org/abs/1905.10437)
`TCNModel` | ✅ | ✅ | ✅ | ✅ | ✅ | | [TCN paper](https://arxiv.org/abs/1803.01271), [DeepTCN paper](https://arxiv.org/abs/1906.04397), [blog post](https://medium.com/unit8-machine-learning-publication/temporal-convolutional-networks-and-forecasting-5ce1b6e97ce4)
`TransformerModel` | ✅ | ✅ | ✅ | ✅ | ✅ | | 
`TFTModel` (Temporal Fusion Transformer) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | [TFT paper](https://arxiv.org/pdf/1912.09363.pdf), [PyTorch Forecasting](https://pytorch-forecasting.readthedocs.io/en/latest/models.html)
Naive Baselines | ✅ | | | | | |
