# Linear-Regression-and-Linear-SVM

## What to test on
You’ll be analyzing the performance of these methods on a somewhat-recently devised classification
problem, known as Fashion-MNIST.
For instructions on how to load the dataset, use this README:
https://github.com/zalandoresearch/fashion-mnist/blob/master/README.md
As mentioned above, Fashion-MNIST corresponds to a multi-class problem with ten classes;
however, this assignment is about binary classification. Therefore, once you load the dataset, use
only the data points (from both the training and test sets) from classes 0 and 6 (corresponding
to “T-shirt/top” and “Shirt” respectively). You can let class 0 from Fashion-MNIST be class 0 of
your binary classification problem (and class 6 from Fashion-MNIST can be class 1 of your binary
classification problem).
To make training easier, I recommend normalizing each example in one of the following ways:

• rescaling the inputs by dividing them by 255, so they lie in the range [0, 1];

• normalizing each feature vector so that it has unit (Euclidean) norm.

You (optionally) can also try other preprocessing techniques. You can feel free to ask classmates
about preprocessing techniques that work well or don’t work well.

## How to do the analysis
Now that you have implementations and the data prepared, it’s time for the main part of the
assignment: the experiment analysis. Your analysis will go into a file called report.pdf and
consists of the following parts, which should be presented in separate sections in this order:
### First. 
For logistic regression, plot how the training and test error change as the regularization
parameter C varies. For training, use the whole training set (all 12,000 examples), and for testing,
use the whole test set (all 2,000 examples). You should try at least ten values of the regularization
parameter. I suggest using a logarithmically spaced grid for initial value C0 > 0 and base α > 1,
so you try C0, αC0, α
2C0, etc. The values you try ideally should capture both the regime of
underfitting (too much regularization) and overfitting (too little regularization). Discuss the results.
### Second. 
For linear SVM (SVM with the linear kernel), plot how the training and test error
change as you vary the regularization parameter C. I suggest proceeding as you did for logistic
regression, but note that the range of values you try for the regularization parameter likely will
need to be different. Again, discuss your results.
### Third. 
Now that you have some understanding of the regularization parameter of each algorithm,
it’s time to do some hyperparameter tuning. The goal is to do a fair, head-to-head comparison of
an optimally regularized logistic regression classifier and an optimally regularized linear SVM. For
this, using only the training data, use k-fold cross-validation (for k being some integer between 5
and 10) to select the optimal value of the logistic regression regularization parameter. Likewise,
use k-fold cross-validation to select the optimal value of the SVM regularization parameter. Now
that you have optimal regularization parameters for each, train each optimally-tuned method on
the entire training set and report the method’s test error. Discuss the results. Are the test errors
significantly different? Think about confidence intervals (which depend on the test set size) to
assess significance.
### Fourth. 
The final part of the assignment is to go beyond linear classifiers. For this, you’ll use
kernelized SVMs with the Gaussian kernel. This kernel has a scale parameter (sometimes called
a “bandwidth” parameter). For each value γ in a good range of values of the scale parameter
(I suggest using a logarithmic spacing as you did with the regularization parameter), use k-fold
cross-validation on the training set to select the optimal regularization parameter Cγ. Now, for
each (γ, Cγ) pair, you have a tuned SVM that can be trained. For each tuned SVM, train on the
full training set and compute both the training error and the test error. Finally, plot the results.
The x-axis will be γ, and the y-axis will be the training error (or test error) based on an SVM with
parameters tuned to (γ, Cγ).
How do these test errors compare to the test error of linear SVM (with regularization parameter
tuned via cross-validation on the training set, which you already did)?
