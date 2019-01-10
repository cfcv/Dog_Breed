# Dog_Breed
## Requirements
The basic requirements to run this project is to have installed:
Python 3, jupyter notebook, Keras and Numpy.
 
## Description
This project was divided in 6 main steps:
* 1: Loading the datasets
* 2: Human detection
* 3: Dog detection
* 4: Classify dog breeds
* 5: Writing the Application algorithm
* 6: Testing the application

#### Loading the datasets
In this part we load two datasets, the dataset of humans(13233 photos) and the datasets of dogs(8351 photos). Both can be found here:

#### Human detection
In the first moment i'm using the Haarcascade face detector of opencv that detects only **frontal faces**. Later i will improve this part by using the Deep learning based face detector of opencv.

#### Dog detection
For the dog detection i'm using the Restnet50 trained in the ImageNet dataset.

#### Classifying breeds
First i built a little CNN from scratch with the following architecture:
2x Convolutional layers with 32 and 64 filters with kernel size of 3 and relu activations
1x MaxPooling layer with pool size of 2
1x Fully connected hidden layer with 128 neurons and relu activation
1x output layer with size 133 and softmax activation
After training for 5 epochs it achieved an accuracy of 4.7%

Later i used transfer learning to build the classifier. I used the bottleneck_features of
ResNet50 to train a NN to predict achieving 84.6% accuracy. It was in average 50 photos per breed in the testing set, 6 for the validation and 6 for testing.

#### Writing the algorithm
Here i checked if there is a dog in the input image to predict its breed, otherwise, i checked if there is a human in the input image to predict the breed of the dog who is most similar to him/her.

#### Testing
Here are the results :)

![alt text](https://github.com/cfcv/Dog_Breed/blob/master/images_test_final_app/dog_breed_result.png)

