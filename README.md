# Ledoit-Wolf covariance matrix estimator of stock returns

The estimation of the covariance matrix of stock returns is required for portfolio optimization.
The standard statistical method is to gather a history of past stock returns and compute their sample covariance matrix. 
Unfortunately this creates problems when the number of stocks under consideration is large, especially relative to the 
number of historical return observations available, the sample covariance matrix is estimated with a lot of error. It 
implies that the most extreme coefficients in the matrix thus estimated tend to take on extreme values not because this 
is "the truth", but because they contain an extreme amount of error. The mean-variance optimization software will place 
its biggest bets on those coefficients which are the most extremely unreliable.

This implementation of the covariance matrix estimator use Ledoit-Wolf shrinkage to constant correlation unequal 
variance target and is based on [Honey, I Shrunk the Sample Covariance Matrix](http://www.ledoit.net/honey.pdf) and was 
proposed to solve the problem of unreliable sample covariance.

# Why not sklearn?

LedoitWolf Estimator from [sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.covariance.LedoitWolf.html)
use Ledoit-Wolf shrinkage to zero correlation equal variance target and implies no systematic risk and equal total risk 
of all stocks.

# Special thanks to:
 
[Evgeny Pogrebnyak](https://github.com/epogrebnyak).
