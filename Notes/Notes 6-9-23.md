# Notes 6-9-23

## Week 1 of Course 1
* **Neural Networks** are made up of neurons each having its own weight and bias.

* **Supervised Learning** deals with structured data and relies on labelled datasets to make predictions about the output.
* This is in contrast to **Unsupervised learning** which learns patterns in unlabelled datasets to solve problems.


* Examples of **Supervised Learning** include,
1. Neural Networks
2. Logistic Regression
3. Linear Regression

    and many more...

* NNs can be of various types such as RNNs, LSTMs, CNNs, GRUs, etc

***

## Week 2 of Course 1
* **Binary Classification** is the classification of data into one of two categories.

* **Binary Classification** is commonly implemented through **Logistic Regression** which is a supervised learning algorithm relying on an activation function to compute the probability of an event occuring.

* **Logistic Regression** uses a **Loss Function** to calculate the error between our predicted output, and the actual correct output.
  
* The **Mean Square Loss** is by far the simplest way to calculate loss, however it suffers from certain optimisation problems, particularly with multiple local optima.

* Rather we prefer the **Log Loss** function

* There is also the **Cost Function** which describes the total error over all the training examples and is expressed as the mean of **Loss Functions** for each training example.

* The **Cost Function** has a convex shape, which is very useful for gradient descent, as it has only one global optimum.

* **Gradient Descent** is used for training the weights and biases by subtracting the product of learning rate _a_ with the derivative of _loss function wrt the weight w_.

* A **Forward Pass** involves passing in inputs and generating an output.

* A **Backward Pass** involves computing the derivatives of the **Loss Function**, wrt each weight and bias of the network using the chain rule of derivatives.

* For a **Logistic Regression** model derivatives can be easily computed as

1. da = -y/a + (1-y)/(1-a)
2. dz = a-y
3. dw = X*dz
4. db = dz

* But these are for one sample, for multiple examples, we make use of vectors, which we will see later...

* Another important variable in the training procedure is the **learning rate**
1. w = w -_a_*dw
2. b = b -_a_*db

* These are the general formulas for updating the weights and biases for training.
  
* Generally, the learning is very small (think 0.000001).

* The learning rate should be chosen carefully, so that learning takes place at a steady pace
  * If it is too small, it will take too much time to converge on the optimum (in rare cases it could even diverge!).
  * If it is too large, it may skip over the optimum.
  
* Generally, all the variables involved in the model are stored as vectors or matrices.

    This is done to improve the efficiency as  `for`  loops are observed to be slower in comparison.

* All the above formulas can be extended to their vector forms as well.

* This is made possible thanks to broadcasting, whereby a (3,1) matrix can be extended to a (3,3) matrix if it is to be added to another (3,3) matrix by simply taking the first column and making copies of it for the other two columns.
