---
title: "I Was Busy Thinkin’ ‘Bout Birds"
---
## Problem Setup
This project created a bird classification model for the Kaggle competition "I Was Busy Thinkin' 'Bout Birds". The goal of the model is to classify the 555 bird species using the dataset that this competition provided.
## DataSet
The Kaggle competition provides the dataset containing 555 different bird species and 38562 images of the training dataset. In the training dataset folder, it contains 555 different sub-folders, representing 555 different bird species. Since this dataset does not provide the validation dataset to test the model and the testing dataset does not have labels, I split the labeled dataset to 85/15 for the training dataset and validation dataset.
## Techniques
A pre-trained model ResNet101 was used, and its final fully connected layer was modified to have the same amount of bird species, which is 555, in the output dimension. The data augmentation used in the project includes random 224 x 224 cropping, horizontal flip, affine transform, and normalize transform with the mean and median of ImageNet [2]. Different pre-trained models were also trained, which include ResNet50, ResNet34, and ResNet101 provided the best result among the three pre-trained models, considering the size of the dataset. 

The model was trained in 25 epochs, 0.01 as the beginning learning rate along with the schedule [0: 0.01, 5: 0.001, 10: 0.0001, 15: 0.00001, 20: 0.000001], and this can provide the best result compare to the different learning rate and schedule, which includes [0: 0.1, 5: 0.01, 10: 0.001, 15: 0.0001, 20: 0.00001],  [0: 0.025, 7: 0.0025, 14: 0.0025, 21 : 0.0025],  [0: 0.25, 7: 0.025, 14: 0.025, 21: 0.025].          

## Result
