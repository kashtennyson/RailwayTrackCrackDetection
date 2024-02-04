# Railway Track Crack Detection
This repository implements computer vision methodology to automate the inspection of railway tracks.

## General
This project involves training a deep learning algorithm for multi-class classification problem.

## Problem Description
Maintaining railway tracks in healthy conditions is critical to ensuring the safe operation of railroad transportation. In an effort to prevent such accidents, railway companies regularly inspect tracks to detect and fix defects of track systems.

Conventionally, these inspections are done manually: Track inspectors visually inspects the rails using specialized equipment to measure and check track conditions. However, the current inspection practices have a few critical limitations — heavy involvement of human operations, costly and time consuming processes, and error-prone results. 

## Proposed Solution
This repository proposes and implements an innovative method for conducting railroad track inspection to enhance the maintenance operation. 

It utilizes computer vision methodologies to achieve high-level automation and accuracy of defect detection through the analysis of digital images. It aims to help railway companies perform predictive maintenance more effectively and, thereby, reducing the risk of train accidents and increasing the resiliency of their assets.

## Basic Overview of the Code
After setting up the colab environment and importing necessary modules, we load the dataset into our colab environment. Then, we split the data into train, validation, and test sets and apply necessary preprocessing steps before feeding it to the network. We also apply various data augmentations to help our model generalise well to the previously unseen examples. It also helps us in battling overfitting and makes our model more robust.

Now, we import the pre-trained inception v3 model and remove its top layer. Then we construct and train our custom made top layers on our small dataset containing 858 images distributed in 7 classes. The topmost layer contains 7 activation units corresponding to 7 different classes. In other words, we are making use of transfer learning for our classification problem.

Finally, we plot the loss and accuracy of our model against the number of epochs. We also evaluate our model on a held out test set and render the confusion matrix for true labels given by the test set and predicted labels given by the model.

Last step in saving the model weights in google drive in '.h5' format.

## Basic Overview of the project based on Edge AI
The project integrates advanced computer vision and gyroscope sensor information to identify defects and determine the rail alignment.

The railway track video is captured by a camera module and saved in a compressed format and decoded into frames. Among the frames, only the keyframes storing the complete image information in the data stream were used for track defect classification and analysis to reduce the processing time.

The track alignment is measured by a gyroscope sensor.

An OV7670 camera module is selected for video recording and a MEMS GPU6050 sensor is used for collecting acceleration and gyroscope information. In addition, an STM32 evaluation board is used to collect and process digital image data, which is then combined with the gyroscope data to create a multi-source inspection system running on edge AI.