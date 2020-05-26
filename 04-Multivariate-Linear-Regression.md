# Multivariate Linear Regression
## Multiple Features
Previously, we had used a single variable *x* to predict *y*.

Now we can look at a vector of variables representing various features to predict the price.

Some notation:
* n = number of features
* x<sup>i</sup> = input (features) of i<sup>th</sup> training example
* x<sub>j</sub><sup>i</sup> = value of feature j in i<sup>th</sup> training example

Hypothesis:
* Previously:
    * h(x) = Theta<sub>0</sub> + Theta