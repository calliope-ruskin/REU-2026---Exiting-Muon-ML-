This repository contains the code from my 2026 REU at the University of Rochester studying how machine learning can be used to reconstruct exiting muon momentum in the ICARUS neutrino detector. 
I worked with Dr. Chris Marshall and Kiyoung Jung on this project. 
Versions 1-5 used a Deep Neural Net that was ineffective at any attempt of reconstruction. 
These versions are not represented in this repository. 

For testing with inputs and polar deviation see Kiyoung Jung's work. 

**Version 6 (GRU):** Deviation ordering and loss function testing
- V6 has cartesian deviations and non-inverse ordering of data. 
- V6.1 has cartesian deviations and inverse ordering of data.
- V6.2 introduces and MSE loss to the superior inverse ordered data. 
- V6.3 uses MAE loss. 
- V6.4 implements Huber Loss with delta = 1 or SmoothL1Loss.
- V6.5 and V6.6 have Huber Loss with delta = 1.35 and 500 respectively. 
- V6.7 uses Log Cosh Loss. 
- V6.8 introduces a bidirectional ordering with the inverse data first, to the previous best model V6.5 . 

We see that V6.8 is the most successful. 

**Version 7:** Activation function testing
- V7 uses Huber Loss function with delta = 1, bi-directionality, and training on 50% of data with a GeLU activation function. 
- V7.1 tests with the ReLU activation function. 
- V7.2 used a combination of Tanh and Sigmoid which resulted in failure. 
- V7.3, V7.4 has the SeLU and Leaky ReLU activation functions.

We found the best model of this batch to be V7.1.

**Version 8:** Dropout rate testing
- V8 uses the previous most successful mode, V7.1, with a dropout rate of 0.1
- V8.1, V8.2, V8.3, and V8.4 have dropout rates of .2, .15, .05, and .3 respectively.

We found that V8 was the most perferable model. 

**Version 9:** Optimizing number of hidden layers and dimensions
- V9 uses previous best model, V8, with 4 hidden layers.
- V9.1 and V9.2 has 5 and 3 hidden layers respectively.
- V9.3 has 100 nodes in each layer with the previous best performance of 4 layers.
- V9.4 has 64 nodes per layer with 4 layers.
- V9.5 used 40 nodes per layer and significantly underperformed.

We observe that model V9.4 performed the best. 

**Version 10:** Final tunings with 100% of data
- V10 used V9.4 with a training sample of 100% of the data and found an underperformance compared to the previous model trained with 100% of data.
- V10.1 implemented a 80 hidden nodes with 4 layers and was found to be the most sucessful model throughout all versions. 
