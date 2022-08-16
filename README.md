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

Therefore, both the sample autocovariance (acf) and sample autocorrelation functions are considered as measured of dependency for stationary time-series data. Overall, a simple structural time series model, is the additive decomposition model. Furthermore, in financial time series there are often changes which are long term. Thus, the long term level of $(X_t)$ at time t is a stochastic process and is assumed to be a function of present and past values of $X_t$, $X_{t-1}$,.... Moreover, at time t there will also be a fluctuation component ft which represents new behaviour at time $t$ additional to the existing previous level at time $t-1$, which is assumed to be stationary, that is, none of its statistical properties change with time. 

$$X_t = \ell_{t-1} ( X_{t-1}, X_{t-2},... ) + f_t ( X_{t-1}, X_{t-2}, ...., \epsilon_t,  \epsilon_{t-1}).$$

Therefore, the above equation can only be seen as a proper stochastic process model, if using the innovations, the equation can sequentially generate a series. 
In terms of modelling assumptions we assume the presence of covariance stationary processes with innovation terms that are independently and identically distributed. The particular assumption can be relaxed, however in those cases that the innovation sequences do not follow the i.i.d assumption special considerations regarding the asymptotic theory of statistics and sample moments could apply. 



## Remarks

The above aspects are considered to be the fundamental assumptions in time series models. However, often these assumptions could vary depending on both the econometric model under consideration as well as on the empirical data application. For example, when modelling stock returns the presence of serial correlation  has an important interpretation in the financial economics literature. Specifically, incorporating serial correlation in models of stock prices and expected returns can provide additional evidence on the validity of the efficient market hypothesis and explain other market anomalies. For instance, Lewellen (2002) explains that momentum can arise in three ways: (i) positive autocorrelation due to investors expectations of high-performing firms, (ii) negative cross-sectional correlation of a firm with respect to the cross-section of the same industry, and (iii) under the assumption of absence of time-series predictability since momentum strategies are based on unconditional means, positive profits are expected for investing in stocks with the
highest unconditional expected returns (see, section 2 of Lewellen (2002)). Therefore, the assumption of serial correlation provides not only a more realistic representation on investors behaviour (e.g., as explained by momentum strategies) but also captures important features in financial markets especially for models of portfolio loss or risk. In this teaching page we focus on time-series modelling under the assumption of stationarity and ergodicity. 

# 2.  Time Series Models for Univariate Series

## Example 1: Signal-Plus-Noise Model

$$X_t = D_t + U_t, \ \ \ \ i = 1,...,n$$  

where $U_t$ is the stochastic component and $d_t$ is the deterministic component, which can take the form of a constant slope such that $D_t = \mu$ or a constant slope and a trend such that $D_t = \mu + \beta t$. 

## Example 2: Stationary AR(1) Model

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

The family of ARCH and GARCH models are commonly used parametric models for capturing important stylized features of financial time series such as long memory, volatility clustering, fat tails in the distribution of stock returns etc. In particular, the GARCH(1,1) model or AR(1)-GARCH(1,1) model have repeatedly proved to provide robust parsimonious representations of market volatility (see Hansen (2005)). 

Let $\eta_t$ be a real-valued discrete-time stochastic process on some information set $I_t$ which includes all information up to time $t$. Then the GARCH(p,q) model representation is given by 

$$ \sigma^2_t = \alpha_0 + \sum_{i=1}^{q} \alpha_i \ \epsilon^2_{t-1} + \sum_{i=1}^{p} \beta_i  \sigma^2_{t-1}, \ \ \ \epsilon_t \sim N(0,\sigma^2_t),$$

where $a_0 \geq 0$, $\alpha_i \geq 0$ and $\beta_i \geq 0$ and $E(\epsilon_0^4) < \infty$. The conditional variance of $\sigma^2_t$ (estimated volatility) can be estimated by substituting the values of the fitted parameters. Furthermore, appropriate model selection (selection of the lag parameters p and q) can include the use of methods such as autocorrelation and partial autocorrelation functions to identify and check the behaviour of the conditional variance equation of the GARCH model. 

A GARCH(1,1) regression process is given by the following equations

$$y_t = \mu + \eta_t , \ \eta_t = \sigma_t \epsilon_t  \ \text{with} \ \epsilon_t \sim N(0,1) \ \text{and} \ \sigma^2_t = \omega + \alpha \epsilon^2_{t-1} + \beta \sigma^2_{t-1}$$

An AR(1)-GARCH(1,1) regression process is given by 

$$y_t = \mu + \rho y_{t-1} + \eta_t , \ \eta_t = \sigma_t \epsilon_t \ \text{with} \ \epsilon_t \sim N(0,1) \ \text{and} \ \sigma^2_t = \omega + \alpha \epsilon^2_{t-1} + \beta \sigma^2_{t-1}.$$

The above non-linear models are valid under certain regulatory conditions which include $\omega , \alpha, \beta \geq 0$ and $\alpha + \beta < 1$ in order to avoid the existence of IGARCH effects. The recursively estimated sequences $(\sigma^2_t)$ for $t=0 ,..., + \infty$ are assumed to be non negative with probability 1 and common unconditional local mean given by $\sigma^2=\frac{\omega}{1 - \alpha - \beta}$. 

Furthermore, statistical estimation can be done by imposing certain parametric assumptions. A commonly used methodology in the literature is the implementation of the QMLE. The use of QML estimation can restore any inefficient model estimations (i.e., existence of negative coefficients or out of bounds persistence) and allows for higher estimation precision since the proposed methodology is less restrictive in the moment assumptions of the observed process (no restriction on normality assumption - which induces distribution-free inference). 

Let $\mathbf{\theta}=(\omega,\alpha,\beta)$ be the parameter to be estimated based on a sample $y_1,...,y_N$ and is $\sqrt{N}$ consistent i.e., $\sqrt{N}|\hat{\mathbf{\theta}} - \theta | = O_p(1)$. Let the conditional log-likelihood function of GARCH(1,1) given by

$$L_N(\theta) \equiv L_N(\theta ; \epsilon_1,...,\epsilon_N) = \prod_{t=1}^N \frac{1}{\sqrt{2 \pi \hat{\sigma}^2_t } }\exp \bigg( - \frac{\epsilon^2_t}{2 \hat{\sigma}^2_t  } \bigg), \hat{\sigma}^2_t = \omega + \alpha \epsilon^2_{t-1} + \beta \hat{\sigma}^2_{t-1}.$$   

and the QMLE for the set of model parameters $\theta=\{\omega, \alpha, \beta \}$ of GARCH(1,1) to be  

$$\hat{\theta}_N = \underset{ \theta \in \Theta}{\text{argmax}} \ L_N(\theta)$$

which is equivalent to 

$$ \underset{\theta \in \Theta}{\text{argmin}} \ \hat{l}_N(\theta), \ \text{where} \ \hat{\ell}_N(\theta) = \sum_t \bigg( \log[\hat{\sigma}^2_t] + \frac{\epsilon^2_t}{\hat{\sigma^2_t}}  \bigg).$$

Then asymptotic normality holds, which implies that, 

$$\displaystyle{ \sqrt{N}(\hat{\theta}_N - \theta_0^{*}) \overset{d}{\to} N(\mathbf{0}, \mathbf{V_0} )}, \ \mathbf{V_0}=\mathbf{B_0^{-1}A_0 B_0^{-1}}.$$


```R

## Estimation Examples in R 

# Simulating an ARCH(1) model series

n     <- 100
omega <- 0.25
alpha <- 0.85

simARCH <- function( n = n, omega = omega, alpha = alpha )
{# begin-of-function
  
  eta        <-rnorm(n)
  ht         <-as.numeric(n)
  epsilon    <-as.numeric(n)
  epsilon[1] <- sqrt(omega)*eta[1]
  
  for (t in 2:n) 
  {
    ht[t]=omega+alpha*epsilon[t-1]^2
    epsilon[t]<-sqrt(ht[t])*eta[t]
   }
  
  return( epsilon[1:n] )

}# end-of-function
```


# 3.  Statistical Testing


Following the work of Granger and Andersen (1978) for a linear stationary process it holds that 

$$\mathsf{Corr} \left( X^2_t, X^2_{t-k} \right) = [ \mathsf{Corr} \left( X_t, X_{t-k} \right) ]^2$$

for some time series $X_t$ across all k. Therefore, departures from the above expression indicate the presence of nonlinearity in time series. In particular, using the squared residuals from a linear model we can apply a standard Box-Ljung Portmanteau test for serial correlation (see, Lee, White and Granger (1993)). In other words, the BLP test is sensitive to departures from linearity in mean which implies the presence of ARCH structure in the data, making it a suitable test for detecting the presence of ARCH effects. 

### Remarks

- Notice that nonlinearity in mean should not be confused with a Nonlinear time series model, in which case for the purpose of this course, we refer to a threshold model. Additionally statistical testing for the presence of both nonlinearity and nonstationarity is also a different stream of literature. 

- Many of the aspects we discuss in this teaching page regarding some of the stylized facts of univariate time series are useful for the subsequent stages of time series analysis such as model fitting and estimation, inference as well as forecasting. An overview of forecasting applications is presented in the recently published review of Petropoulos et al. (2022) at the International Journal of Forecasting.  


## References

- Berkes, I., Gombay, E., Horváth, L., & Kokoszka, P. (2004). Sequential change-point detection in GARCH (p, q) models. Econometric theory, 20(6), 1140-1167.
- Granger, C. W. (1980). Long memory relationships and the aggregation of dynamic models. Journal of Econometrics, 14(2), 227-238.
- Horvath, L., & Kokoszka, P. (2003). GARCH processes: structure and estimation. Bernoulli, 9(2), 201-227.
- Lewellen, J. (2002). Momentum and autocorrelation in stock returns. The Review of Financial Studies, 15(2):533-564.
- Lo, A. W. (1991). Long-term memory in stock market prices. Econometrica: Journal of the Econometric Society, 1279-1313.
- Lee, T. H., White, H., & Granger, C. W. (1993). Testing for neglected nonlinearity in time series models: A comparison of neural network methods and alternative tests. Journal of Econometrics, 56(3), 269-290.
- Osborn, D. R. (1984). Causality testing and its implications for dynamic econometric models. The Economic Journal, 94, 82-96.
- Petropoulos, F. et al. (2022). Forecasting: theory and practice. International Journal of Forecasting, 705-871.

### Other

Lecture Notes of the course: 'Finacial Time Series (2011-2012), Department of Statistics, University of Warwick taught by [Professor Tony Lawrance](https://warwick.ac.uk/fac/sci/statistics/staff/academic-research/lawrance/personal/)

# Reading List

$\textbf{[1]}$ Tsay, R. S. (2005). Analysis of financial time series. John Wiley & Sons. (Chapter 1: Financial Time Series and Their Characteristics)

$\textbf{[2]}$  Hamilton, J. D. (1994). Time series analysis. Princeton University Press. (Chapter 2: Lag Operators)

$\textbf{[3]}$  Hayashi F. (2002). Econometrics. Princeton University Press. (Chapter 6: Serial Correlation)


# Disclaimer

The author (Christis G. Katsouris) declares no conflicts of interest.

The proposed Course Syllabus is currently under development and has not been officially undergone quality checks. All rights reserved.

Any errors or omissions are the responsibility of the author.

# Historical Background

$\textbf{Clive Granger}$  (4 September 1934 – 27 May 2009) was a British econometrician who made significant contributions to the field of nonlinear time series analysis. In particular, Professor Clive Granger was awarded the Nobel Memorial Prize in Economic Sciences in 2003 in recognition of the contributions that he and his co-winner, Robert F. Engle, had made to the analysis of time series data. This work fundamentally changed the way in which economists analyse financial and macroeconomic data (Source: Wikipedia).

