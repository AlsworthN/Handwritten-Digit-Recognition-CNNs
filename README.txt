OBJECTIVE:
The objective of this repository was to build a model that can accurately recognise handwritten digits (0-9) from the MNIST dataset

WORKFLOW:
-Load and read MNIST data.
-Scale pixels values of images to be between 0 and 1.
-Flatten 'x_train' and 'x_test' 28x28 pixel images to be a one dimensional 784 values numpy array
-Reorganise y values (labels) to be stored as a list of 10 zeroes except for the index corresponding to the true label, which is stored as a one. e.g if label was 3, the list would look like [0,0,0,1,0,0,0,0,0,0]
-Initialise weights and biases to a value using He-Initialisation to narrow the range of possible initial values.
-Define activation function (ReLu) and its derivative.
-Define softmax function to return probabilities of each possible output rather than the absolute value. 
-Define move forward function which returns output of first and second layer along with the activations of the first layer and softmaxed probability of the second layer. (z1,z2,a1,a2 respectively)
-Define Cross-Entropy Loss function which returns the loss of the final output.
-Define update paramters function which updates the weights and biases of the network based on the learning rate and change in loss with respect to change in variable.
-Define arbitrary learning rate, number of epochs and batch size.
-Define backpropagation function which works out the error at the output layer and gradients for the second hidden layer before sending the error backwards. The gradient for the first layer is also calculated.
-Loop through for number of epochs defined, and at each iteration:
  -an index is randomly chosen from the length of the flattened x train values.
  -x and y shuffle variables are defined as the array of the values of x and y at the index calculated previously. 
  -variable for epochs_loss is also defined.
  -a secondary loop is defined between 0 and the length of flattened x train, in steps of batch size defined. At each iteration:
    -x_batch is defined as x_shuffle between the number of iteration and number of iteration + batch size.
    -y_batch is defined as y_shuffle between the number of iteration and number of iteration + batch size.
    -move forward function is called to find output of first and second layer along with the activations for the first layer and the final softmaxed output. 
    -cross-entropy loss for each prediction is calculated by calling the cross entropy loss function
    -backpropagation function is called to find the change in weights and biases
    -update parameters is called to update weights and biases while using the changes in weights and biases returned from the backpropagation function. 
-Predictions function is defined for the model returning the final softmaxed probability using the move forward function.
-Each prediction is stored in a list named predicted_label.

TECHNICAL REQUIREMENTS:
Python 3.13.7was used as the backend language.
NumPy as a data science library


