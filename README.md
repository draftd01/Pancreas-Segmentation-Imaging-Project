# dl_final_project
DL Final Project (Medical Image Segmentation)

# Project Description
## Project Title
Medical Image Detecting in Different Models
## Team Members
Daniel Drafta and Dania Elsheikh
## Goal/Objective
The goal of this project is to run different image segmentation models on pancreas medical images to detect tumors and compare accuracies of each model, focusing mainly on false negative rates, as those will be most important when detecting medical issues such as tumors or cancer. Having a high false negative rate will lead to unnecessary death that could have been avoided. We want to see which model is best for this task, as well as she how optimizing the parameters will change the 
## Challenges
One challenge includes working with a large data set and having to build the model from scratch. Because we will be working with three large models, changing parameters multiple times, this might take a while and have a high computational cost. 
 
## Approach/Technique
Different models will be used. The first model will be a not pretrained model. The second will be a pretrained version of the model
Compare model metrics of a pre-trained and not pre-trained Mask R-CNN model with a ResNet-50-FPN backbone
## Implementation Details
We will be using google colab’s GPU to train the models as this would be faster than training them the our devices’ CPUs
## References
https://github.com/JunMa11/SegLoss
https://github.com/pytorch/vision/tree/main/references/detection

# Code decription
The repo contains 2 ipynb: Daniel's project code that contains the code to train the not pretrained model while Dania's project code contains the code to train the pretrained model on our dataset. 
Daniel's code contains both of the evaluations

# How to run 
All the code was run through colab. 
