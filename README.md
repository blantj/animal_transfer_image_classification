# Cat/Dog Transfer Learning Image Classification
## Introduction
In order to test the efficacy of transfer learning, I decided to classify a Kaggle dataset with 10,000 rgb images across dog and cat classes. I first built a baseline stratified dummy classifier model, which had a test accuracy of .5. I next built a transfer learning neural network with MobileNet as the non-trained portion and a trained pooling layer, dense layer, dropout layer and output layer. The transfer learning model produced a testing accuracy of .789, which outperformed the baseline stratified dummy classifier.

## Obtain Data
I downloaded 10,000 png images from Kaggle.  Included in the images were cat class images, which included cats in them, and dog class images, which included dogs.

## Scrub Data

<a href="url"><img src="https://github.com/blantj/animal_transfer_image_classification/blob/main/Images/sample_images.png" align="middle" height="250" width="500" ></a>

In order to model the raw images, I used the Keras ImageDataGenerator to extract rgb pixel value and label data from the training and test set images. I then defined image and label variables from the generator for use in training the neural network. While generating the image data, I set the image size to 224x224 pixels in order to ensure that the images would be the same size as the input layer of the pre-trained neural network I planned to use.

## Explore Data

<a href="url"><img src="https://github.com/blantj/animal_transfer_image_classification/blob/main/Images/class_distribution.png" align="middle" height="200" width="250" ></a>

The cat-dog image dataset had 8,000 training images and 2,000 testing images, representing an 80/20 train test split. Each image had a 224x224x3 shape representing a 224x224 image size across the rgb values. The training and test datasets were both 50/50 balanced across the cat and dog classes.

## Model Data

<a href="url"><img src="https://github.com/blantj/animal_transfer_image_classification/blob/main/Images/neural_network_train_layers.png" align="middle" height="200" width="600" ></a>

In order to model the cat-dog dataset, I first built a stratified dummy classifier to compare to my subsequent transfer learning neural network. This baseline model had a test accuracy of .5. I used a MobileNet neural network with the output layer removed as the non-trained portion of my transfer learning neural network. I also added to the MobileNet a pooling layer, a dense layer, a dropout layer and an output layer that would need to be trained. This model produced a testing accuracy of .789, which outperformed the baseline stratified dummy classifier.

# Github Files
[Modeling.ipynb](https://github.com/blantj/animal_transfer_image_classification/blob/main/Modeling.ipynb) :  Cat/Dog Transfer Learning Image Classification Modeling

# Sources
Kaggle: https://www.kaggle.com/chetankv/dogs-cats-images
