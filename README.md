# Triplet Network

This project is a coarse replication of the paper [Deep Metric Learning Using Triplet Network (Hoffer et al.)](https://arxiv.org/pdf/1412.6622.pdf).

## Usage

Run the ```main_triplet.py``` file to train the model. Loss, accuracy, and encoded graphs are auto-generated using ```matplotlib``` under root. By default, the dataset (CIFAR10 Images) will be encoded into 128D vectors by the trained model.  
Run the ```main_classifier.py``` file to train another independent, one-layer neural network, with inputs being the encoded images (128D vectors) and outputs being a softmax classifying vector (10D vector).  
To customize loss function or model architecture, use the ```lib``` folder and modify the classes.
To apply the sampling method in the paper [Sampling Matters in Deep Embedding Learning (Wu et al.)](https://arxiv.org/pdf/1706.07567.pdf), run the ```triplet_sampling.py``` file.

## Results
Using the following hyperparameters:
```
learning_rate=0.01, loss_margin=1, batch_size=100, num_train_instance=50000, num_test_instance=10000
```
The model achieves KNN-accuracy of 65% on testing dataset after around 50 epochs.

<img src="https://github.com/Jichao-Yang/triplet_network/blob/master/doc/loss.png" width="400"> <img src="https://github.com/Jichao-Yang/triplet_network/blob/master/doc/acc.png" width="400">

The encoded images shows clusters after applying PCA for dimension reduction.

<img src="https://github.com/Jichao-Yang/triplet_network/blob/master/doc/Encoded_train_set.png" width="400"> <img src="https://github.com/Jichao-Yang/triplet_network/blob/master/doc/Encoded_test_set.png" width="400">

## Notes

This program uses a different architecture than the one mentioned in the paper. Additionally, data augmentation techniques are different from the one used in the original paper.
