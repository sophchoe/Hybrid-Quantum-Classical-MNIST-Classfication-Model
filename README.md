# Hybrid-Quantum-Classical-MNIST-Classfication-Model

This is a Keras-Pennylane implementation of MNIST classification using classical and quantum layers, inspired by "Continuous-variable quantum neural networks" Physics Review 1 033063 (2019). The model in the paper is for binary classification, hence there is a slight modification to the proposed model. 

The modification takes advantage of the measurement flexibility not present in the qubit model. A quantum state in photonic quantum computing is an infitie sum of density matrices of number basis as shown in this expression.

<img width="300" alt="photonic_quantum_state" src="https://user-images.githubusercontent.com/22792633/134836345-83ddf514-51c0-4ef2-9ef0-c4e2878cc2c7.png">


A visual representation of the architecture of the network (based on binary classication) is 


The notion of cutoff dimension allows for the flexibility of approximating the true quantum state with a desired number of basis. When using 2 qumodes, the probability measurement of the computational basis (density matrix) returns a vector of length (cutoff dimension)^2. By setting cutoff dimension to 4, we get vectors of length 4^2 = 16. Viewing each element of the vector as the probability of finding 0 - 9 with 6 irrelevant entries allows us to use it as label prediction. We one-hot encode the labels and pad 6 zeros for each label to match the output vector of our hybrid network.
