# Traffic Signs Recognition with Convolutional Neural Networks
This project focuses on recognizing traffic signs using Convolutional Neural Networks (CNNs). The objective is to train a model capable of classifying various traffic signs commonly found on roads.

## Introduction
Traffic sign recognition is crucial for autonomous vehicles and advanced driver-assistance systems (ADAS). This project employs CNNs to classify and predict the type of traffic sign from images.

## Problem Statement
- In this case study, you have been provided with images of traffic signs and the goal is to train a Deep Network to classify them
- The dataset contains 43 different classes of images. 
- Classes are as listed below: 

    - ( 0, b'Speed limit (20km/h)') ( 1, b'Speed limit (30km/h)')
    - ( 2, b'Speed limit (50km/h)') ( 3, b'Speed limit (60km/h)')
    - ( 4, b'Speed limit (70km/h)') ( 5, b'Speed limit (80km/h)')
    - ( 6, b'End of speed limit (80km/h)') ( 7, b'Speed limit (100km/h)')
    - ( 8, b'Speed limit (120km/h)') ( 9, b'No passing')
    - (10, b'No passing for vehicles over 3.5 metric tons')
    - (11, b'Right-of-way at the next intersection') (12, b'Priority road')
    - (13, b'Yield') (14, b'Stop') (15, b'No vehicles')
    - (16, b'Vehicles over 3.5 metric tons prohibited') (17, b'No entry')
    - (18, b'General caution') (19, b'Dangerous curve to the left')
    - (20, b'Dangerous curve to the right') (21, b'Double curve')
    - (22, b'Bumpy road') (23, b'Slippery road')
    - (24, b'Road narrows on the right') (25, b'Road work')
    - (26, b'Traffic signals') (27, b'Pedestrians') (28, b'Children crossing')
    - (29, b'Bicycles crossing') (30, b'Beware of ice/snow')
    - (31, b'Wild animals crossing')
    - (32, b'End of all speed and passing limits') (33, b'Turn right ahead')
    - (34, b'Turn left ahead') (35, b'Ahead only') (36, b'Go straight or right')
    - (37, b'Go straight or left') (38, b'Keep right') (39, b'Keep left')
    - (40, b'Roundabout mandatory') (41, b'End of no passing')
    - (42, b'End of no passing by vehicles over 3.5 metric tons')

## Dataset
The dataset used for this project is the Traffic Sign Recognition Benchmark (GTSRB). Due to its large size, the dataset cannot be included directly in this repository.

## LE-NET CNN
- The network used is called Le-Net that was presented by Yann LeCun
http://yann.lecun.com/exdb/publis/pdf/lecun-01a.pdf

## Data Preparation
The dataset consists of images of traffic signs categorized into different classes. The following steps were taken to prepare the data:

- Importing Data: The data was stored in pickle files (train.p, test.p, valid.p) and loaded using Python's pickle library.
- Image Exploration: A brief exploration of the dataset was performed to visualize and verify the images and their corresponding labels.
- Data Preprocessing: Steps included shuffling the data, converting images from color to grayscale, and normalizing pixel values.

## Model Training
The model consists of the following layers: 

- STEP 1: THE FIRST CONVOLUTIONAL LAYER #1
    - Input = 32x32x1
    - Output = 28x28x6
    - Output = (Input-filter+1)/Stride* => (32-5+1)/1=28
    - Used a 5x5 Filter with input depth of 3 and output depth of 6
    - Apply a RELU Activation function to the output
    - pooling for input, Input = 28x28x6 and Output = 14x14x6


    * Stride is the amount by which the kernel is shifted when the kernel is passed over the image.

- STEP 2: THE SECOND CONVOLUTIONAL LAYER #2
    - Input = 14x14x6
    - Output = 10x10x16
    - Layer 2: Convolutional layer with Output = 10x10x16
    - Output = (Input-filter+1)/strides => 10 = 14-5+1/1
    - Apply a RELU Activation function to the output
    - Pooling with Input = 10x10x16 and Output = 5x5x16

- STEP 3: FLATTENING THE NETWORK
    - Flatten the network with Input = 5x5x16 and Output = 400

- STEP 4: FULLY CONNECTED LAYER
    - Layer 3: Fully Connected layer with Input = 400 and Output = 120
    - Apply a RELU Activation function to the output

- STEP 5: ANOTHER FULLY CONNECTED LAYER
    - Layer 4: Fully Connected Layer with Input = 120 and Output = 84
    - Apply a RELU Activation function to the output

- STEP 6: FULLY CONNECTED LAYER
    - Layer 5: Fully Connected layer with Input = 84 and Output = 43

## Model Evaluation
The trained model was evaluated on the test dataset to measure its performance:
Test Accuracy: Achieved an accuracy of approximately **85.71%** on the test set.
### Visualizing Results
The model's predictions were visualized using heatmaps for the confusion matrix and a grid of actual vs. predicted traffic sign images from the test set.

## Files
traffic_signs_classification.ipynb: Jupyter Notebook containing the entire code and implementation.

## Instructions for Usage
1. Clone the repository.
2. Download the GTSRB dataset.
3. Run the notebook traffic_signs_classification.ipynb in an environment with necessary dependencies.
