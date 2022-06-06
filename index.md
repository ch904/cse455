---
title: "I Was Busy Thinkin’ ‘Bout Birds"
---
Link to video: [CSE455 Final Project](https://youtu.be/GCLo-X8UCGg) <br><br>
Link to source code: [cse455_final_project.ipynb](https://github.com/ch904/cse455/blob/gh-pages/cse455_final_project.ipynb)
## Problem Setup
This project created a bird classification model for the Kaggle competition "I Was Busy Thinkin' 'Bout Birds". The goal of the model is to classify the 555 bird species using the dataset that this competition provided.
## DataSet
The Kaggle competition provides the dataset containing 555 different bird species and 38562 images of the training dataset. In the training dataset folder, it contains 555 different sub-folders, representing 555 different bird species. Since this dataset does not provide the validation dataset to test the model and the testing dataset does not have labels, I split the labeled dataset to 85/15 for the training dataset and validation dataset.
## Techniques
A pre-trained model ResNet101 [1] was used, and its final fully connected layer was modified to have the same amount of bird species, which is 555, in the output dimension. The data augmentation used in the project includes random 224 x 224 cropping, horizontal flip, affine transform, and normalize transform with the mean and median of ImageNet [2]. Different pre-trained models were also trained, which include ResNet50, ResNet34, and ResNet101 provided the best result among the three pre-trained models, considering the size of the dataset. 

The model was trained in 25 epochs, 0.01 as the beginning learning rate along with the schedule [0: 0.01, 5: 0.001, 10: 0.0001, 15: 0.00001, 20: 0.000001], and this can provide the best result compare to the different learning rate and schedule, which includes [0: 0.1, 5: 0.01, 10: 0.001, 15: 0.0001, 20: 0.00001],  [0: 0.025, 7: 0.0025, 14: 0.0025, 21 : 0.0025],  [0: 0.25, 7: 0.025, 14: 0.025, 21: 0.025].          

## Result
![image](https://user-images.githubusercontent.com/97132692/172105010-7a0b7424-9c98-4e6d-b85e-16c5121c0f60.png)
![image](https://user-images.githubusercontent.com/97132692/172109812-67792018-38e6-4c38-982d-354dc30d1158.png)

#### Final Training Accuracy (epoch 25): 0.785
#### Final Testing Accuracy (epoch 25): 0.676
#### Score on Kaggle: 0.824

## Previous work
The pre-trained model ResNet101 were used as the model. The majority code used in this project was adopted from the PyTorch tutorial ImageNet and Transfer Learning, and Transfer Learning To Birds that given by Professor Redmon. I modified the data augmentation part to perform different transformation to the images, splitted the dataset to test out the model, re-write the training function to include validation losses, as well as designed training schedules for model. 

## References
1: https://arxiv.org/pdf/1512.03385.pdf <br> <br>
2: https://pytorch.org/vision/stable/models.html
