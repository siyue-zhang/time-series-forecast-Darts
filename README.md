# time-series-forecast-Darts
Time series forecast using darts Python library, which contains a variety of models

![](./images/workflow.jpg)

## Darts

[darts](https://github.com/unit8co/darts) is a Python library for easy manipulation and forecasting of time series. It contains a variety of models, from classics such as ARIMA to deep neural networks. The library also makes it easy to backtest models, and combine the predictions of several models and external regressors.

<p align=center>
<image src=https://github.com/unit8co/darts/raw/master/static/images/darts-logo-trim.png width=400>
</p>

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
