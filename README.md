# MNIST-Data-Set
## MNIST Digit Data Set Classification using Backpropagation
##### Author & Date: Sameer Kumar, 24/10/2018
This file trains Neural Network for Digit Classifications of MNIST Using BackPropagation
Neural Architecture:
- Three Layers - 1: Input Layer 2: Hidden Layer 3: Output Layer
Input Layer - 784 Inputs
Hidden Layer - 40 Neurons Activation Function tanh
Output Layer - 10 Neurons Activation Function softmax
- Weight: w(i, j) indicates weight fed to ith neuron from jth input
Weights in Layer 2 (Hidden Layer) W_Layer_2 [ w(1,0).....w(1,784)
                                              ...................
                                              w(40,0).....w(40,784)] 40x785
Weights in Layer 3 (Output Layer) W_Layer_3 [ w(1,0).....w(1,40)
                                              ...................
                                              w(10,0).....w(10,40)] 10x41
- Energy or Loss function: Cross Entropy 
- Weights have bias
- Note: This network is designed to have only have two layers but can have user defined neurons in each layer.
- Weights in Layer 2: n x (785), 784 input neurons, +1 to that to incorporate bias
- Weights in Layer3: 10 x (n+1), 10 output neurons works well with Softmax, +1 to incorporate bias.

This code was designed to use following Heuristics to make it efficient:
1 - Scaled/Normalized the Training Set to have mean 0 and variance 1. The parameters used to normalize the Training Set
was used to normalize Test Set.
Note: To report accuracy on different Test Set that data must be normalized in the same way as above
2 - Momentum Method was incorporated in update step.
Note: This code has regularization has incorporated in it. But Hyperparameter search is highly necessary. So set it to zero.
3 - In last layer Softmax activation function coupled with Cross Entropy loss function was used.
4 - Before every epoch of training Shuffling of Training Set Elements was done.
5 - Weights were initialized by taking inspiration from Xavier initialisation. I didn't follow it as it is, but modified to get:
    Layer 1 weights: Gaussian Random Variable N(0, sqrt(2/784))
    Layer 2 weights: Gaussian Random Variable N(0, sqrt(2/10))
    Imp: Even if you change the number of neurons in the hidden layer don't change the weight how weights are initialised.
 6 - To Push accuracy or to decrease the error of the Neural Net increase number of neurons present in hidden layer. 
 7 - Due to the Cross Entropy function the traning set accuracy will jump to more than 99%. 
Note: Code requires optimization to decrease execution time. 
Note: Set alpha = 0, beta = 0.9, eta = 5
Note: I have also uploaded results for reference. 
