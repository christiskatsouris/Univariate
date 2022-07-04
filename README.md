# Univariate

The field of Time Series Econometrics focuses on the develompent of econometric methodologies for time series models. A crucial component for understanding the properties of such models is to study the time series properties of regressors and their associated underline stochastic processes. Related properties include the integration order, the degree of persistence and the memory of the process. In particular, the memory of the process makes the corresponding time series bounded in probability in large samples.   

Economic time series are often decomposed into a deterministic trend and a stochastic process which is the main idea upon which various time-series regression models are implemented. Furthermore, a second aspect of concern is to distinguish "short-run" from "long-run" relationships. In particular, these long-run relationships are closely linked to the concepts of equilibrium relationships in economic theory and of persistence co-movements of economic time sereis in econometrics.     

## Introduction 

### Preliminary Concepts on Stochastic Processes

A stochastic process is an ordered sequence of random variables 

$$X_t : t \in \mathbb{N}.$$

such that 

$$X_1, X_2, X_3,...$$

is a strictly stationary process with covariance function obtained as explained below. 

### Time-Series Stationary Processes: Covariance Stationarity

Consider a time-series Xt with autocovariance function given by

$$\gamma (k) = \mathbb{E} ( X_t . X_{t-k} ) \equiv \text{Cov} ( X_t , X_{t-k} ).$$

Similarly the autocorrelation function of the time-series is given by 

$$\rho ({k}) = \frac{ \text{Cov} ( X_t , X_{t-k} ) }{ \sigma^2 }.$$

Therefore, both the sample autocovariance (acf) and sample autocorrelation functions are considered as measured of dependency for stationary time-series data. Overall, a simple structural time series model, is the additive decomposition model. Furthermore, in financial time series there are often changes which are long term. Thus, the long term level of {Xt} at time t is a stochastic process and is assumed to be a function of present and past values of Xt, Xt-1,.... Moreover, at time t there will also be a fluctuation component ft which represents new behaviour at time t additional to the existing previous level at time t-1, which is assumed to be stationary, that is, none of its statistical properties change with time. 

$$X_t = \ell \ell_{t-1} ( X_{t-1}, X_{t-2},... ) + f_t ( X_{t-1}, X_{t-2}, ...., \epsilon_t,  \epsilon_{t-1}).$$

Therefore, the above equation can only be seen as a proper stochastic process model, if using the innovations, the equation can sequentially generate a series. 

## Example 1

Consider a financial time series sequence and obtain the autocovariance and autocorrelation functions. 

## References

- Lo, A. W. (1991). Long-term memory in stock market prices. Econometrica: Journal of the Econometric Society, 1279-1313.

## Further Reading

- Tsay, R. S. (2005). Analysis of financial time series. John wiley & sons. (Chapter 1: Financial Time Series and Their Characteristics)

