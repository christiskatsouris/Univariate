# Univariate

The field of Time Series Econometrics focuses on the develompent of econometric methodologies for time series models. A crucial component for understanding the properties of such models is to study the time series properties of regressors and their associated underline stochastic processes. Related properties include the integration order, the degree of persistence and the memory of the process. In particular, the memory of the process makes the corresponding time series bounded in probability in large samples.   

$\textbf{Motivation:}$ Economic time series are often decomposed into a deterministic trend and a stochastic process which is the main idea upon which various time-series regression models are implemented. Furthermore, a second aspect of concern is to distinguish "short-run" from "long-run" relationships. In particular, these long-run relationships are closely linked to the concepts of equilibrium relationships in economic theory and of persistence co-movements of economic time series in econometrics.     

# 1. Introduction 

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

Therefore, both the sample autocovariance (acf) and sample autocorrelation functions are considered as measured of dependency for stationary time-series data. Overall, a simple structural time series model, is the additive decomposition model. Furthermore, in financial time series there are often changes which are long term. Thus, the long term level of $(X_t)$ at time t is a stochastic process and is assumed to be a function of present and past values of $X_t$, $X_{t-1}$,.... Moreover, at time t there will also be a fluctuation component ft which represents new behaviour at time t additional to the existing previous level at time t-1, which is assumed to be stationary, that is, none of its statistical properties change with time. 

$$X_t = \ell_{t-1} ( X_{t-1}, X_{t-2},... ) + f_t ( X_{t-1}, X_{t-2}, ...., \epsilon_t,  \epsilon_{t-1}).$$

Therefore, the above equation can only be seen as a proper stochastic process model, if using the innovations, the equation can sequentially generate a series. In terms of modelling assumptions we assume the presence of covariance stationary processes with innovation terms that are independently and identically distributed. The particular assumption can be relaxed, however in those cases that the innovation sequences do not follow the i.i.d assumption special considerations regarding the asymptotic theory of statistics and sample moments could apply. 

## Remarks

The above aspects are considered to be the fundamental assumptions in time series models. However, often these assumptions could vary depending on both the econometric model under consideration as well as on the empirical data application. For example, when modelling stock returns the presence of serial correlation  has an important interpretation in the financial economics literature. Specifically, incorporating serial correlation in models of stock prices and expected returns can provide additional evidence on the validity of the efficient market hypothesis and explain other market anomalies. For instance, Lewellen (2002) explains that momentum can arise in three ways: (i) positive autocorrelation due to investors expectations of high-performing firms, (ii) negative cross-sectional correlation of a firm with respect to the cross-section of the same industry, and (iii) under the assumption of absence of time-series predictability since momentum strategies are based on unconditional means, positive profits are expected for investing in stocks with the
highest unconditional expected returns (see, section 2 of Lewellen (2002)). Therefore, the assumption of serial correlation provides not only a more realistic representation on investors behaviour (e.g., as explained by momentum strategies) but also captures important features in financial markets especially for models of portfolio loss or risk. In this teaching page we focus on time-series modelling under the assumption of stationarity and ergodicity. 

# 2.  Time Series Models for Univariate Series

## Example 1: Stationary AR(1) Model

Consider the stationary AR(1) model. Write an expression that generates sequenentially the series.  

$$X_t = \rho X_{t-1} + u_t, X_0 = 0, \ \ \text{then} \ \ \  X_t = \rho^t X_0 + \sum_{j=1}^t \rho^{t-j} u_j.$$

where the information set, that is, the natural filtration at time t is denoted with $\mathcal{F}_t$ and it holds that

$$ \ \ \ \mathbb{E} \left(  u_t | \mathcal{F}_{t-1} \right) = 0, \ \ \ \ \mathsf{Var} \left(  u^2_t | \mathcal{F}_{t-1} \right) = \sigma^2.$$

Hence, or otherwise obtain the autocovariance and autocorrelation functions. 

## Remarks

1. Notice that although the main assumption regarding the innovation sequence of the the stationary AR(1) time series model is that $u_t$ is an i.i.d sequence with mean zero and known variance, this assumption can be further relaxed to incorporate weakly or strongly dependent error sequences. In particular, by imposing a linear process representation then we can introduce the notation of weakly dependent errors 

$$u_t = \sum_{j=0}^{\infty} c_j \epsilon_{t-j}, \ \ c_0 = 1, \epsilon_t \overset{ i.i.d }{ \sim } ( 0, \sigma^2 ), \ \ \ \text{where} \ \{ c_j \}, \ \  j=1,...,+\infty, \ \ \text{are real coefficients},$$

and it holds that 

$$\sum_{j=0}^{\infty} | c_j | < + \infty \ \ \ \text{and} \ \ \ \sum_{j=0}^{\infty} c_j \neq 0.$$

2. Notice that the above conditions provide related summability conditions so that the corresponding sums of innovations weakly converge almost surely. Furthermore, the absolute summability condition is considered to be stronger that square-summability.

3. Notice that, we consider autoregressive processes which belong to the class of covariance-stationary processes (which are in the class of causal processes). 


## Example 2: Stationary ARMA(p,q) Model 

```R

## Estimation Examples in R 




```

## Remarks

Notice that many time series exhibit "long memory", which implies that the autocorrelation function decays slowly with respect to the lag. In general such a time series characteristic traditionally has been modelled in the literature with unit roots (using nonstationary asymptotics), nonlinear dynamics (or regime switching) as well as structural breaks. In particular, in this course we examine the aspect of nonstationarity focusing on two different modelling approaches, that is, (i) the econometric identification of structural breaks and (ii) nonlinear time series modelling such as the threshold regression model (see, [Nonstationary](https://github.com/christiskatsouris/Nonstationary)). We leave the study of unit root testing and the corresponding asymptotic theory for a course on "Nonstationary Time Series Econometrics" (to be developed in the future).    


## Example 3: Autoregressive Models of Conditional heteroscedasticity 

```R

## Estimation Examples in R 




```


# 3.  Statistical Testing


Following the work of Granger and Andersen (1978) for a linear stationary process it holds that 

$$\mathsf{Corr} \left( X^2_t, X^2_{t-k} \right) = [ \mathsf{Corr} \left( X_t, X_{t-k} \right) ]^2$$

for some time series $X_t$ across all k. Therefore, departures from the above expression indicate the presence of nonlinearity in time series. In particular, using the squared residuals from a linear model we can apply a standard Box-Ljung Portmanteau test for serial correlation (see, Lee, White and Granger (1993)). In other words, the BLP test is sensitive to departures from linearity in mean which implies the presence of ARCH structure in the data, making it a suitable test for detecting the presence of ARCH effects. 

### Remarks

- Notice that nonlinearity in mean should not be confused with a Nonlinear time series model, in which case for the purpose of this course, we refer to a threshold model. Additionally statistical testing for the presence of both nonlinearity and nonstationarity is also a different stream of literature. 

- Many of the aspects we discuss in this teaching page regarding some of the stylized facts of univariate time series are useful for the subsequent stages of time series analysis such as model fitting and estimation, inference as well as forecasting. A holistic discussion on forecasting applications is presented in the recent review of Petropoulos et al. (2022).  


## References

- Granger, C. W. (1980). Long memory relationships and the aggregation of dynamic models. Journal of econometrics, 14(2), 227-238.
- Petropoulos, F. et al. (2022). Forecasting: theory and practice. International Journal of Forecasting, 705-871.
- Lewellen, J. (2002). Momentum and autocorrelation in stock returns. The Review of
Financial Studies, 15(2):533-564.
- Lo, A. W. (1991). Long-term memory in stock market prices. Econometrica: Journal of the Econometric Society, 1279-1313.
- Lee, T. H., White, H., & Granger, C. W. (1993). Testing for neglected nonlinearity in time series models: A comparison of neural network methods and alternative tests. Journal of Econometrics, 56(3), 269-290.
- Osborn, D. R. (1984). Causality testing and its implications for dynamic econometric models. The Economic Journal, 94, 82-96.

# Reading List

$\textbf{[1]}$ Tsay, R. S. (2005). "Analysis of financial time series". John Wiley & Sons. (Chapter 1: Financial Time Series and Their Characteristics)

$\textbf{[2]}$  Hamilton, J. D. (1994). "Time series analysis". Princeton University Press. (Chapter 2: Lag Operators)

$\textbf{[3]}$  Hayashi F. (2002). "Econometrics". Princeton University Press. (Chapter 6: Serial Correlation)

# Historical Background

$\textbf{Clive Granger}$ was a British econometrician who made significant contributions to the field of nonlinear time series analysis. In particular, Professor Clive Granger was awarded the Nobel Memorial Prize in Economic Sciences in 2003 in recognition of the contributions that he and his co-winner, Robert F. Engle, had made to the analysis of time series data. This work fundamentally changed the way in which economists analyse financial and macroeconomic data (see wikipedia).

# Disclaimer

The author (Christis G. Katsouris) declares no conflicts of interest.

The proposed Course Syllabus is currently under development and has not been officially undergone quality checks. All rights reserved.

Any errors or omissions are the responsibility of the author

# How to Cite a Website

See: https://www.mendeley.com/guides/web-citation-guide/

