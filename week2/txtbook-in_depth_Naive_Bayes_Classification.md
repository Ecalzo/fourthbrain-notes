# In Depth: Naive Bayes Classification

Link to [textbook chapter](https://jakevdp.github.io/PythonDataScienceHandbook/05.05-naive-bayes.html) in Python Data Science Handbook

Naive Bayes Classification is one of several algorithms for supervised and unsupervised learning.

Naive Bayes models are a group of extremely fast and simple classification algorithms.
* Suitable for very high-dimension data
* Useful for quick & dirty baseline d/t speed

## Bayesian Classification
Built on Bayesian classification methods, which relay on Bayes's therorem.
* This is an equation describing the relationship of conditional probabilities of statistical quantities.
* Bayesian classigivation is interested in finding the probability of a label given some observed features.
*  [Link to Wikipedia entry](https://en.wikipedia.org/wiki/Bayes%27_theorem) for Bayes' theorem

Deciding between two (or more) labels can be accomplished by computing the ration of the [posterior probabilities](https://en.wikipedia.org/wiki/Posterior_probability) for each label.
    * "Posterior" means after taking into accoun the relevant evidence related to the particular case being examined.

**Generative Model** - is a type of model that specifies the hypothetical random process that generates the data.
* Specifying this generative model for each label is the mai npiece of training of such a Bayesian classifier.
* This general step is very difficult, but we can make some assumptions about the form of this model to simplify things, this is what makes the model "naive".

> If we make very naive assumptions about the generative model for each label, we can find a rough approximation of the generative model for each class, and then proceed with the Byesian classification. Different types of naive Bayes classifiers rest on different naive assumptions about the data...

## Gaussian Naive Bayes
In this classifier, the assumption is:
* The data from each label is drawn from a simple Gaussian (normal) distribution.

assumes that the data is described by a Gaussian distribution with no covariance between dimensions.
* FYI: [covariance](https://en.wikipedia.org/wiki/Covariance) is the measure of the joint variability b/t two variables.
* Means that greater values of one variable correspond with greater values of the other variable. Same for smaller variables.

The procedure for a Gaussian Naive Bayes is implemented in `sklearn.naive_bayes.GaussianNB`
* In general, the boundary of a Gaussiance naive Bayes is **quadratic**
* A nice piece of Bayesian formalism is that it "naturally" allows for more probabilistic classification, which we can compute using the `predict_proba` method, `model.predict_proba(Xnew)`
    * This gives the posterior probabilities of the first and second label, respectively.
    * If you are looking for estimates of uncertainty in your classification, Bayesian approaches like this can be useful.

## Multinomal Naive Bayes
* Features are assumed to be generated from a simple [multinomial distribution](https://en.wikipedia.org/wiki/Multinomial_distribution)
    * **multinomial** distribution is a generalization of the binomial distribution.
    * It models the probability of counts for each side of a k-sided die rolled n times.
    * > When k is 2 and n is 1, the multinomial distribution is the Bernoulli distribution. When k is 2 and n is bigger than 1, it is the binomial distribution. When k is bigger than 2 and n is 1, it is the categorical distribution.
* This describes the probabilitiy of observing counts among a number of categories.
* **Multinomial Bayes is most appropriate for features that respresent counts or count rates**

## When to use Naive Bayes
Because these models make strict assumptions about data, they will generally not perform as well as a more complicated model. But there are still advantages:
* Extremely fast for training/prediction
* Staightforward probabilistic prediction
* Easily interpretable
* Very few tunable parameters

The NB classifiers tend to perfor well in the following situations:
* When the naive assumptions actually match the data (rare)
* For very well-separated categories, when model complexity is less important
* For very high-dimensional data, when model complexity it less important