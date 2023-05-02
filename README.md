# Variance Swap Introduction

A variance swap is a forward contract on annualized variance, the square of the realized volatility.  The holder of a variance swap at expiration receives a notional amount of dollar for every point by which the stock’s realized variance has exceeded the variance delivery price.  

Valuation of the swap involves decomposition of the contract into two periods, one that has become historical, and the other with stock prices still unknown.  The unknown variance from the value date to the swap maturity can be replicated by a portfolio of call and put options.  Volatility skew can be incorporated into pricing of these options through bi-linear interpolation.

We developed pricing models for equity log forward contracts and variance swaps. The model for variance swaps can be used to calculate P&L and risk numbers.

Suppose there are n consecutive trading days  .  At the maturity of a variance swap, the realized variance is defined as

where N is the notional amount and   is the delivery price for variance.

Let t be the value date,  .  If  , the stock prices at   have become historical.  We then have

and the second term   is the future realized variance.  This future realized variance can be replicated by a portfolio of call and put options with appropriate weights.  In brief, the expectation of   can be written as

where   is the drift of the stock price process,   is the forward price of stock at time t with expiration at T,   is the a reference strike price,   is the discount factor, and   is the present value of the portfolio, given by

Here, P and C are put and call option prices.  We suppose that we can trade all options with strikes   such that   and put options with strikes   such that  .  

Weights of the portfolio can be determined by many approaches.  One such approach is called the slope method, described as follows.  Define a function

weights are then given by

We have also proposed another approach, named the K-squared method.

We provide a few test cases for variance swaps.  In the first test case, a flat volatility for the underlying stock is provided.  Theoretically the computed realized volatility should be the same as the flat volatility used.  The second case instead specifies a volatility skew file.  Both these two cases have no historical variances.  Test cases 3 and 6 have historical variance, and valuation is carried out right on   and one minute after  .  The stock price at the latter has become historical.  The reference strike price and option data are specified in cases 1 to 6, and are not specified in cases 7 to 10.


Reference:

https://finpricing.com/lib/IrCurve.html
