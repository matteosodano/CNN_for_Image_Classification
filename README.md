# Convolutional Neural Networks for Image Classification
Developed by: M. Sodano (2019).

Supervisor: prof. L. Iocchi.

Achievement: Machine Learning exam.\
<br>


Convolutional Neural Networks are used since they are able to deal with multi-dimensional data by means of a kernel that moves along the image and perform some operations on it, so as to obtain some new representation of that image.

Two different approaches are followed in this work: first, a Convolutional Neural Network is created, trained and tested. It is named *MatNet*. Then, transfer learning is applied: in this way, a pre-trained model is used and compared with MatNet.

## Data-set
A weather data-set is used. It is stored in Google Drive, and it is divided into different folders. Four classes are considered: haze, sunny, snowy, rainy. The data-set is balanced, therefore the accuracy is chosen as main metric for the evaluation.

Also a blind test-set is used at the end of the project.

## Mat-Net
Three convolutional layers, each one followed by a max pooling operation, are used. After them, four dense layers (with dropout) and an output layer are present. The hidden layers are characterized by a ReLU activation function, while the output layer has a softmax. Heavy fluctuation of the results are obtained, probably due to under-fitting. 

<p align="center"> <img width="400" src="https://user-images.githubusercontent.com/62264708/83524394-d9649300-a4e3-11ea-8f37-d83289b12902.PNG"> </p>

## Transfer Learning
Two different convolutional model are used for transfer learning. Both are pre-trained on ImageNet. Several models have been tested, but these two have been reported because of their differences, even if both pre-trained on ImageNet.

**Case 1**: *InceptionResNetV2*. It is used with average pooling. It achieves good performances. As it can be seen from the confusion matrix below, the rainy pictures are often confused with snowy ones.

<p align="center"> <img width="400" src="https://user-images.githubusercontent.com/62264708/83524404-da95c000-a4e3-11ea-8d2b-246989ce3465.PNG"> </p>

**Case 2**: *VGG16*. It is used with max pooling. Performances are poor.

<p align="center"> <img width="400" src="https://user-images.githubusercontent.com/62264708/83524406-da95c000-a4e3-11ea-8908-c1a7253adfd4.PNG"> </p>
