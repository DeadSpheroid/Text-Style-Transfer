# Mini-Projects

## About the projects
This folder contains a list of mini-projects implemented by us during the course of the entire project.
***
### Deep-Neural-Network-From-Scratch
***
Binary_Classifier.ipynb contains the code for a binary classifier that we created using a deep neural network.

We trained the network on a dataset consisting of genuine and forged bank notes using four features of the image of the note.
Full information about the dataset used is available [here](https://www.openml.org/search?type=data&sort=runs&id=1462&status=active)

The implmentation was done in [numpy](https://numpy.org/) alone, and allows you to manually choose how many layers, units/layer, activations/layer, etc.
***
### IMDB-LSTM
***
IMDB-LSTM.ipynb contains a tensorflow implementation for a binary classifier.

The dataset used is the popular [IMDB movie review dataset](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews) consisting of reviews labelled as positive or negative.

The model used is a bi-directional LSTM model with dropout layers to discourage overfitting.

We use a bi-directional LSTM so that the model can capture the sentiment of a word using the full context of its neighbours and not just its predecessors.

***
### MNISTDigit
***
MNISTDigit.ipynb contains a simplistic tensorflow implementation of a multi-class classifier.

The dataset used is the [MNISTDigit dataset](https://www.tensorflow.org/datasets/catalog/mnist), consisting of a labelled photos of digits from 0 to 9.

The model used is a dense neural network of 3 layers with varying number of units/layer.

## Conclusion
These mini-projects were crucial to our understanding of neural networks and helped us get comfortable with the tensorflow framework.

