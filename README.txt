This project was a first attempt at building a simple neural network from scratch using NumPy trained to recognise handwritten digits (0-9) from the MNIST dataset.

The dataset originally contained 28x28 pixel images of handwritten digits which were flattened into 784 values and scaled the value of pixels 0-1

The hidden layer of the network contains 128 neurons that are all connected to each other. The activation function used in this project was ReLu because it allows to account for non-linear correlations within the data. During backpropagation, it uses SoftMax to generate probabilities for how likely each value is. 

The train and test set labels were rewritten in the form of a list containing 10 zeroes with a 1 in the index of the label of the number. 


