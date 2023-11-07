# Notes 7-9-23

## Week 3 of Course 1

* **Neural Networks** essentially repeat the calculations done in logistic regression multiple times.

* **NN**s are made up of layers, where the first layer is called the **input** layer, the final layer that generates the output is called **output** layer.

* Any other layers in between are called hidden layers and these are responsible for computing the **activation function** for each layer and passing it to the next layer.

* Each hidden layer has parameters _w_ and _b_ associated with it in the form of matrix and vector. The shape and size of _w_ and _b_ depends on the **number of nodes** in the layer, and the **number of inputs** from the previous layer. 

* It is possible to vectorise all the inputs and weights and biases to optimise our calculations.

* It is further possible to vectorise our input across all training examples, eliminating the need of a `for` loop to loop through all the training examples.

* **Activation** functions are used to process the final output of the layer and there are various types of them:
  1. **sigmoid** (Between 0 and 1)
  2. **tanh** (Between -1 and 1)
  3. **ReLU** (0 to infinity)

* In most cases, (except binary classification) the _tanh_ is superior to the _sigmoid_ because the output data of _tanh_ is already somewhat centered on zero, making training for the next layer easier.

* Generally however, we use different activation functions for different layers.

* But, one common problem with the tanh and sigmoid, is for larger input values, the gradient becomes very small, causing difficulties in backpropagation

* This is solved by the **ReLU** which is short for _Rectified Linear Unit_ which produces a constant gradient for positive input and zero gradient for negative input.

* **ReLU** is the default activation function for most use cases.

* There is also the **Leaky ReLU** function which has a slight positive gradient for negative values, but it is not used much in practice.

* **Non-Linear Activation Functions** allow the **NN** to learn more complex functions to predict the output.

* **Linear Activation Functions** are almost never used in the hidden layers, but in some cases, they may be used in the output layer.

* The derivatives of the activation functions are as:

    |   tanh   | sigmoid | ReLU |
    |:--------:|:---------:|:---------:| 
    |1 - tanh(z)^2 | sig(z)(1-sig(z)) | 0 if z<0 else 1


* The equations for backprop of two hidden layers is also given.

* We prefer to intialise weights randomly rather than to zero, as this leads to each node of the layer computing the exact same function, even after gradient descent, which is not intended

* Hence, we initialise the weights to random, very small values

* Biases do not have this problem, and can be initialised to zero.

* We initialise the weights to small values, to prevent the activation function from reaching saturation, where the gradient is near zero, thereby slowing down training.

* Including more nodes in hidden layers leads to better results, but after a certain point, causes **overfitting**, which is what happens when the model sticks to the learned data too much and struggles to make new predictions