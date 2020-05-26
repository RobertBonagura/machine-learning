# Linear Regression with One Variable
Can also be referred to as Univariate linear regression
## Model Representation
Take for example a plot of data points for Housing Prices in Portland, OR given by two values:
* Price
* Size

You can fit a model to this data using a straight line to predict what you can sell a house for based on its size.
* This is an example of **supervised learning** because we are given the "right answer" for example in the data.
* We can use this to predict new pairs
* This is a **Regression Problem**, where we can predict a real-valued output

Formally, in supervised learning this data set is known as a **training set**. 

### Some Notation:
* **m** = Number of training examples
* **x**'s = "input" variable / features
* **y**'s = "output" variable / "target" variable
* (x,y) = a single training example
* (x<sup>i</sup>, y<sup>i</sup>) = The i<sup>th</sup> training example

With our **Training Set**, we will use a **Learning Algorithm** to output a function **h**, also known as out *hypothesis*, whose job is to take as input **x** to output an estimated value of **y**.

**h** maps from **x** to **y**.

### So how should we represent h?
h<sub>Theta</sub>(x) = Theta<sub>0</sub> + Theta<sub>1</sub>x<br>
also shown as h(x) = Theta<sub>0</sub> + Theta<sub>1</sub>x<br>

## Cost Function
We can measure the accuracy of our hypothesis function by using a **cost function**.
* This will let us figure out to fit the best possible straight line to our data.

Hypothesis: h<sub>Theta</sub>(x) = Theta<sub>0</sub> + Theta<sub>1</sub>x
* Theta<sub>i</sub>'s are the Paramaters.

### How do we choose Theta<sub>i</sub>'s?
In the case of linear regression, we want these values to correspond to straight line that some how fits the data well.

We want to solve a minimization problem  over Theta<sub>0</sub> Theta<sub>1</sub>
* We want the difference between h(x) and y to be small:
* (1 / 2m) * SIGMA i:m ( h( x<sup>i</sup> ) - y<sup>i</sup> )<sup>2</sup>

In other words, what this equations does is:
* Find the values of Theta<sub>0</sub>, Theta<sub>1</sub> such that the average of the sum of square errors between the predictions on the data set minus the actual on the data set is minimized.
* This is our **cost function**, which is known as a **squared error function**.
* There are other cost functions, but this is one of the most commonly used ones for linear regression problems.

J(Theta<sub>0</sub>, Theta<sub>1</sub>) = (1 / 2m) * SIGMA i:m ( h( x<sup>i</sup> ) - y<sup>i</sup> )<sup>2</sup>

Mimize over Theta<sub>0</sub>, Theta<sub>1</sub> our Cost Function, J(Theta<sub>0</sub>, Theta<sub>1</sub>) 

## Cost Function Intuition I
To better visualize Cost Function J, we are going to use a simplified cost function:
* h(x) = Theta<sub>1</sub>x
  * Theta<sub>0</sub> is set to zero
* One parameter Theta<sub>1</sub>, so our objective is to minimize this parameter.
  * If Theta<sub>0</sub> is set to zero, that means that our hypthesis function will pass through the origin (0,0)

When there is a fixed value for Theta<sub>1</sub>
* The hypothesis function is a function of x.
  * h<sub>Theta</sub>(x)
* The cost function is a function of the parameter Theta<sub>1</sub>.
  * J(Theta<sub>1</sub>)

For each value of Theta<sub>1</sub>, it corresponds to a different straight line fit. By plotting multiple Theta<sub>1</sub> values using our cost function, we will find that a parabola is formed where Theta<sub>1</sub> is our global maximum.

## Cost Function Intuition II
3D Modeling is needed to visualize the cost function of a two variable function.

A contour plot can be used to plot a two variable function, where a given contour line has a constant value at all points on the same line.

## Gradient Descent
Can be used to minimize the cost function J
* Is not used only for linear regressions.
* It is often applied to many other cost functions
* We can use it to minimize *n* paramters on J

Suppose we have some function J(Theta<sub>0</sub>, Theta<sub>1</sub>) that we want to minimize.
* Start with some Theta<sub>0</sub>, Theta<sub>1</sub> values
  * Say Theta<sub>0</sub> = 0,  Theta<sub>1</sub> = 0 for example
* Keep changing Theta<sub>0</sub>, Theta<sub>1</sub> to reduce J(Theta<sub>0</sub>, Theta<sub>1</sub>) until we hopefully end up at a minimum

### Gradient Descent Algorithm
Repeat until convergence:<br>
  Theta<sub>j</sub> := Theta<sub>j</sub> - alpha(d/dTheta<sub>j</sub>)J(Theta<sub>0</sub>, Theta<sub>1</sub>)  (for j = 0 and j = 1)<br>

We update Theta<sub>0</sub> and Theta<sub>1</sub> simultaneously, not using new Theta<sub>0</sub> to find Theta<sub>1</sub>.

* alpha is the **learning rate**, and controls how big a step you make down hill.
* The derivative of our cost function is what tells us which direction to go in.

## Gradient Descent Intuition
The derivative term is:
* (d / dTheta<sub>j</sub>) J(Theta<sub>0</sub>, Theta<sub>1</sub>))

Lets look at a simpler example to see how the alpha and the derivative term effect our descension:

Minimize Theta<sub>1</sub> on J(Theta<sub>1</sub>):
* Regardless of the slope's sign for (d / dTheta<sub>1</sub>) J(Theta<sub>1</sub>), Theta<sub>1</sub> eventually converges to its minimum value.

* Alpha should be adjusted accordingly to ensure taht the graident descent converges in a reasonable time, without overshooting the minimum or failing to converge.

## Gradient Descent for Linear Regression
Previously, we have worked out the following equations:
1. Gradient Descent algorithm
  * Repeat until convergence:
    * Theta<sub>j</sub> := Theta<sub>j</sub> - alpha * (d/dTheta<sub>j</sub>) * J(Theta<sub>0</sub>, Theta<sub>1</sub>)
    * for j = 0 and j = 1
2. Linear Regression Model
    * h<sub>Theta</sub>(x) = Theta<sub>0</sub> + Theta<sub>1</sub>x
    * J(Theta<sub>0</sub>, Theta<sub>1</sub>) = (1 / 2m) * SIGMA i:m ( h( x<sup>i</sup> ) - y<sup>i</sup> )<sup>2</sup>

We are going to apply Gradient Descent to minimize our squared error Cost Function:
* Minimize over Theta<sub>0</sub>, Theta<sub>1</sub> on J(Theta<sub>0</sub>, Theta<sub>1</sub>)

In order to use the Gradient Descent algorithm to minimize our cost function, the key term we need to figure out is the partial derivative term:

(d/dTheta<sub>j</sub>) * J(Theta<sub>0</sub>, Theta<sub>1</sub>)
<br>= (d/dTheta<sub>j</sub>) * (1 / 2m) * SIGMA i:m ( h( x<sup>i</sup> ) - y<sup>i</sup> )<sup>2</sup>
<br>= (d/dTheta<sub>j</sub>) * (1 / 2m) * SIGMA i:m ( Theta<sub>0</sub> + Theta<sub>1</sub>x - y<sup>i</sup> )<sup>2</sup>

We want to find this partial derivative for both Theta<sub>0</sub> and Theta<sub>1</sub>:
* The following values are derived from Multi-variable Calculus' partial derivatives (I'm gonna take Andrew Ng's word for it that these calculations are right)

(d/dTheta<sub>0</sub>) * J(Theta<sub>0</sub>, Theta<sub>1</sub>) = (1/m) SIGMA 1:m ( h( x<sup>i</sup> ) - y<sup>i</sup> )
f
(d/dTheta<sub>1</sub>) * J(Theta<sub>0</sub>, Theta<sub>1</sub>) = (1/m) SIGMA 1:m ( h( x<sup>i</sup> ) - y<sup>i</sup> ) * x<sup>i</sup>

The above calculations are simply the slopes of the cost function J with respect to each Theta parameter

#### Gradient Descent algorithm:
* Repeat until convergence:
  * Theta<sub>0</sub> := Theta<sub>0</sub> - alpha * (1/m) * SIGMA 1:m ( h( x<sup>i</sup> ) - y<sup>i</sup> )
  * Theta<sub>1</sub> := Theta<sub>1</sub> - alpha * (1/m) * SIGMA 1:m ( h( x<sup>i</sup> ) - y<sup>i</sup> ) * x<sup>i</sup>

 * note: All Theta parameters are updated simultaneously

The cost function for a linear regression is always going to be a "Convex function", with no optima other than the global optima.

#### "Batch" Gradient Descent
This term is used for when in every step of gradient descent, we use all of the training examples.
