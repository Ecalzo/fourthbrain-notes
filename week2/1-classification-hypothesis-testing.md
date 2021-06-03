# 1.1 Classification, Logistic Regression
Classification problems where the variable, y, that we want to predict is made up of discrete values.

## Examples of classification problems
* email - spam or not spam?
* online transactions - fraudulent?
* medical - malignant or benign tumor?

in all of these scenarios, y takes on the value of 0 (**negative class**) or 1 (**positive class**). There is the intuition that the negative class is conveying the absence of something, and positive is conveying the presence of something.

Linear regression cannot be applied well to classification problems, because it can be predict values much greater than 1 or much smaller than 0.

# 1.2 Hypothesis testing, Logistic Regression
We would like our classifier to output values between 0 and 1 for (binary) classification

## Logistic Regression Model
In linear regression:
* h<sub>&theta;</sub>(x) = &theta;<sup>T</sup>x

We will apply a function to this linear regression alogirthm, `g(z)`, which will signify the **sigmoid** (logistic) function
* h<sub>&theta;</sub>(x) = g(&theta;<sup>T</sup>x)
* g(z) = 1 / 1 + e<sup>-z</sup>

Therefore:

* h<sub>&theta;</sub>(x) = 1 / 1 + e <sup>-&theta;<sup>T</sup>x

The Sigmoid function has an asymptote as g(z) approaches -inf and +inf at 0 and 1, respectively.
![logistic_regression](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F8%2F88%2FLogistic-curve.svg%2F1200px-Logistic-curve.svg.png&f=1&nofb=1)

## Interpretation of Hypothesis Output
h<sub>&theta;</sub>(x) = estimated probability that `y=1` on input `x`

Ex: h<sub>&theta;</sub>(x) = 0.7, therefore **there is a 70% chance that the tumor is malignant**. (as opposed to a 70% chance that it is NOT malignant)

We can define this as:
* h<sub>&theta;</sub>(x) = P(y=1|x;&theta;)
* probability that `y=1` given `x`, parameterized by &theta;

But since this is a classification task, we know that y must be `0` or `1`.
* We know that the probability that `y=1` and probablity that `y=0` must be equal to 1
* In our example, the probablity that `y=0` is 30% (since `y=1` is 70%)

## Decision Boundary Logistic Regression
Suppose we predict:
* `y=1` if h<sub>&theta;</sub>(x) >= 0.5
    * occurs when &theta;<sup>T</sup>x >= 0
* `y=0` if h<sub>&theta;</sub>(x) < 0.5
    * occurs when &theta;<sup>T</sup>x < 0

The decision boundary is a property of the hypothesis.

The training set is not used to set the decision boundary. The training set is used to learn the parameters, theta, which define the decision boundary.

Higher order polynomial functions can produce very complex decision boundaries.
