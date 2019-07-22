
# Linear Relationships and Prediction

The idea of _correlation_ is the simple idea that variables often change _together_. For a simple example, cities with more buses tend to have higher populations.

We might observe that, as one variable X increases, so does another Y, OR that as X increases, Y decreases.

## Covariance

For two random variables X and Y, each with n values:

$\sigma_{XY} = \frac{\Sigma^n_{i = 1}(x_i - \mu_x)(y_i - \mu_y)}{n}$

<br/>

Note that the value of the covariance is very much a function of the values of X and Y, which can make interpretation difficult. What is wanted is a standardized scale for covariance, hence: _correlation_.

## Correlation

Pearson Correlation $r = \frac{\Sigma^n_{i = 1}(x_i - \mu_x)(y_i - \mu_y)}{\sqrt{\Sigma^n_{i = 1}(x_i - \mu_x)^2\Sigma^n_{i = 1}(y_i -\mu_y)^2}}$

Note that we are simply standardizing the covariance by the standard deviations of X and Y (the _n_'s cancel!).

What happens if X = Y?

We'll always have $-1 \leq r \leq 1$. (This was the point of standardizing by the standard deviations of X and Y.)

A correlation of -1 means that X and Y are perfectly negatively correlated, and a correlation of 1 means that X and Y are perfectly positively correlated.

## Causation

_Why_ does it happen that variables correlate? It _may_ be that one is the cause of the other. A city having a high population, for example, probably does have some causal effect on the number of buses that the city has. But this _need not_ be the case, and that is why statisticians are fond of saying that 'correlation is not causation'. An alternative possibility, for example, is that high values of X and Y are _both_ caused by high values of some third factor Z. The size of children's feet, for example, is correlated with their ability to spell, but this is of course NOT because either is a cause of the other. Rather, BOTH are caused by the natural maturing and development of children. As they get older, both their feet and their spelling abilities grow!

## Statistical Learning Theory

It's important at this point to understand the distinction between dependent and independent variables.

Roughly, the independent variable is what can be directly manipulated and the dependent variable is what cannot be (but is nevertheless of great interest). What matters structurally is simply that we understand the dependent variable to be a _function_ of the independent variable(s).

This is the proper interpretation of a statistical _model_.

Simple idea: We can model correlation with a _line_. As one variable changes, so does the other.

This model has two _parameters_: _slope_ and _y-intercept_.

Q: How do we measure the quality of our linear model?

A: By a loss function! The loss function represents the _loss_ of accuracy that we get by assuming the truth of our model. We therefore want to _minimize_ that function. More on this soon.

## Simple Linear Regression

Finding the best-fit line y = mx + b. Note: The formal proof of this proceeds by setting the derivative of the loss function to zero.

slope: $m = r\frac{\sigma_y}{\sigma_x}$

y-intercept: $b = \mu_y - m\mu_x$

Assumptions:

1. The relationship between target and predictor(s) is linear.
2. The errors are mutually independent.
3. The errors are normally distributed.
4. The errors are homoskedastic.

## Coefficient of Determination

Very often a data scientist will calculate $R^2$, the _coefficient of determination_, as a measure of how well the model fits the data.

$R^2$ for a model is ultimately a _relational_ notion. It's a measure of goodness of fit _relative_ to a (bad) baseline model. This bad baseline model is simply the horizontal line $y = \mu_Y$, for dependent variable Y.

The actual calculation of $R^2$ is $\frac{\Sigma_i(y_i - \hat{y}_i)^2}{\Sigma_i(y_i - \bar{y})^2}$.

$R^2$ takes values between 0 and 1.

$R^2$ is a measure of how much variation in the dependent variable your model explains.



```python

```
