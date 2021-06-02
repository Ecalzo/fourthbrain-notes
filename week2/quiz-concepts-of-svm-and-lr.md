# Quiz - Concepts of SVM and LR

1. What is the minimum number of training samples that are necessary to construct a 2D linear SVM model for a binary classification problem? [Helpful link](http://web.mit.edu/6.034/wwwbob/svm-notes-long-08.pdf)
    * 3 samples, 2 samples of one class and atleast 1 sample of another class
    * 2 samples, one of each class
    * atleast 10 samples per class
    * 1 samples from either class


2. You have a dataset with 50 samples belonging to 2 classes {1, -1} and each sample has 21 features each. Which of the following models will you prefer for classification?
    * SVM with Gaussian Kernel
    * LInear kernel SVM/Linear SVM
    * Logistic regression always
    * Create more features first, then use logistic regression or SVM

3. Which of the following SVM parameters will ensure lower bias and higher variance?
    * Large C, small σ<sup>2</sup>
    * Small C, large σ<sup>2</sup>
    * Small C, small σ<sup>2</sup>
    * Large C, large σ<sup>2</sup>

4. It IS possible to train a logistic regression and SVM classifier for a data set with 1000 samples from 5 different classes using One vs-all method.
    * True
    * False
