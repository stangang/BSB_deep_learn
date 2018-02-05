## Training a high-dimensional neural network to build a predictive model for hedging using real world data
### Machine Learning/Finance/Mathematics
#### Timothy Burt

##### This proof-of-concept generates parameters utilizing nonlinear PDE Black-Scholes-Barenblatt equation which can be used to determine when to buy or sell a derivative stock & its volatility. In addition it could be expanded to use other PDEs and data from other sources.

### Outline

Nonlinear highly dimensional data is becoming increasingly common in today's world. It is becoming increasingly difficult to building predictive models that accurately predict or even describe this highly chaotic data and linear approximations for dimensionality reduction such as principal component analysis (PCA) may destroy useful information. 

### For this project I would employ the deep2BSDE (second-order backward stochastic differential equation) algorithm [1] to train a neural network to build a model for derivative securities (swap/option contracts, futures, forwards). 

The nonlinear PDE Black-Scholes-Barenblatt equation from Arbitrage Pricing Theory [2] allows for the modeling of option prices with uncertain volatility and interest rates given appropriate boundary conditions. It may be represented as

$$\frac{1}{2} \sigma^2 (S,t) S^2 \frac{\partial ^2 V}{\partial S^2}+r(S,t)S \frac{\partial V}{\partial S}-r(S,t)V-\frac{\partial V}{\partial t}=0 \label{eq:bsb}$$

where $\sigma$ is the variable volatility, r is the market (risk-free) interest rate, S is the asset price, and t is the time.

The deep2BSDE algorithm utilizes a stochastic gradient descent method to train a neural network to find the parameters for a specific equation by analyzing many example datasets.

### The goal of this project would be to deliver a web application or GUI where users can select a particular type of derivative and historical data pulled at runtime from online databases. The ideal case for a future derivative of that type (mean-field approximation) would be displayed along with the Black-Scholes equation parameters, which a user can vary to look at other cases. The best and worst case scenarios would also be displayed to the user based on the maximum and minimum volatilities from the model. 

### The power of machine learning can be heavily exploited and a plethora of enlightening visualization schemes utilized with a model such as this. The cross correlation between types of derivative securities or for any other time-dependent y(t) series of data which could be provided by the user could be computed and shown realtime. A causality chain could be generated showing the most heavily dependent securities on other ones to perturbation of the asset price, allowing better estimates on the potential profit/loss it can bring. The deep2BDSE model is high adaptable as it is a nonlinear PDE solver, meaning this project could also be used to model disease proliferation, crop yields, and crime statistics. 

### It could also possibly give theoretical insight into the possible "missing physics" from a particular PDE used in those models [3]. It would allow mathematicians to develop better PDEs to model events, and with the enormous number of sensors gathering physical data woldwide correlations between the physics and social sciences could be found which may lead to event/disaster prediction and the better understanding of the connection between physics & life.
