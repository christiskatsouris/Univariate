# Univariate

The field of Time Series Econometrics focuses on the develompent of econometric methodologies for time series models. A crucial component for understanding the properties of such models is to study the time series properties of regressors and their associated underline stochastic processes. Related properties include the integration order, the degree of persistence and the memory of the process. In particular, the memory of the process makes the corresponding time series bounded in probability in large samples.   

Economic time series are often decomposed into a deterministic trend and a stochastic process which is the main idea upon which various time-series regression models are implemented. Furthermore, a second aspect of concern is to distinguish "short-run" from "long-run" relationships. In particular, these long-run relationships are closely linked to the concepts of equilibrium relationships in economic theory and of persistence co-movements of economic time sereis in econometrics.     

## Introduction 

### Preliminary Concepts on Stochastic Processes

A stochastic process is an ordered sequence of random variables 

$$X_t : t \in T.$$


### Time-Series Stationary Processes: Covariance Stationarity

Consider a time-series Xt with autocovariance function given by

$$\gamma (k) = \mathbb{E} ( X_t . X_{t-k} ) \equiv \text{Cov} ( X_t , X_{t-k} ).$$

Similarly the autocorrelation function of the time-series is given by 

$$\rho ({k}) = \frac{ \text{Cov} ( X_t , X_{t-k} ) }{ \sigma^2 }.$$

Therefore, both the sample autocovariance (acf) and sample autocorrelation functions are considered as measured of dependency for stationary time-series data.    

## Example 1

Consider a financial time series sequence and obtain the autocovariance and autocorrelation functions. 

## References

- Lo, A. W. (1991). Long-term memory in stock market prices. Econometrica: Journal of the Econometric Society, 1279-1313.

## Further Reading

- Tsay, R. S. (2005). Analysis of financial time series. John wiley & sons. (Chapter 1: Financial Time Series and Their Characteristics)

