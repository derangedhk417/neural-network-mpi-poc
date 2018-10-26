# Neural Network Training Proof of Concept

The  goal of this project is to demonstrate a means of optimizing neural networks against quantum mechanical simulation data. The dataset that the neural networks are optimized against is extremely large, and requires that the job processed in a distributed manner. This repository contains code for optimizing a neural network using optimization functions provided by the scipy library. The set of neural network weights generated by each step of the optimization function is distributed to multiple MPI nodes. Each MPI node will compute part of the root mean squared error for that particular set of weights. Each MPI node has a part of the training dataset stored in memory on it. This repo also contains an implementation that uses CUDA capable devices, rather than generic MPI nodes. 

For the sake of simplicity, this repo demonstrates the concept by optimizing the neural network against a dataset that is generated using a simple 60 dimensional function. The actual function is composed of several simple Gaussian terms. In practice, this code will be applied to a much more complex dataset that is generated using quantum mechanical simulations.
