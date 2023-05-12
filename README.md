# dl_final_project
DL Final Project (Medical Image Segmentation)

# Project Description
## Project Title
Medical Image Detecting in Different Models
## Team Members
Daniel Drafta and Dania Elsheikh
## Goal/Objective
Medical diagnosis using machines has gained significant attention in recent years due to the potential benefits it can offer. Machine learning algorithms can be trained on large datasets of medical information, such as patient symptoms, medical history, and test results, to make predictions and provide diagnoses. This technology has the potential to improve accuracy, efficiency, and speed up the diagnostic process. One of the major advantages of using machines in medical diagnosis is the ability to identify diseases and disorders much earlier than traditional diagnostic methods. This early detection can help save lives by allowing doctors to provide the necessary treatment in a timely manner.

The goal of this project is to run different image segmentation models on pancreas medical images to detect tumors and compare accuracies of each model, focusing mainly on false negative rates, as those will be most important when detecting medical issues such as tumors or cancer. Having a high false negative rate will lead to unnecessary death that could have been avoided. We want to see which model is best for this task, as well as she how optimizing the parameters will change the 
## Challenges
The largest problem of this project was the preprocessing of the data.
Loading the file from the kaggle and unzipping them into google drive took a while. Once unzipped the file had to be split up equally and we had to match the ground truth values to the normal scans. There were more scans than ground truth values so we had to take time to filter through every single image and only kept those that had a matching ground truth image.

Unzip pickle files twice since they were also tar files. The pickle files were  turned into something called eval segmentation arrays. We wanted to turn them into numpy arrays but it worked by calling the full index slices [:,:,:]. There was no library or documentation for this type so we had to just try different ideas and methods to convert it. This took a really long time as we were unsure how exactly eval segmentation worked and how to manipulate it

Each patient scan had a different depth, as shown in the graph of the previous slide. In order to adjust we initially considered concatenating the depths of every single image and inputting each layer one by one. This turned out to be computationally too expensive so we had to reconsider a different method. We then changed the scans into JPEGS to input into the data loader. Then these jpegs were input into the model one by one after they were split into test and train. There was another error where one image was put into the train of the ground truth and the training set of the regular scan. We had to debug and run code to find out which file it was a solve the issue.

 
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
Daniel's code contains both of the evaluations.
The code table of contents were split into two main parta: 
1. Data loading, extraction, and preprocessing section
2. Image dataset creating and loading, as well as model training and evaluation

&emsp; One of the imported github python files contained a deprecated module that had to be commented out for successful running

# How to run 
All the code was run through colab. It would not possible directly from this repo without downloading the necessary zips from the referenced github repos and adjusting the paths in the notebook. However, results from the cells that we ran can be viewed with running any code by opening the ipynb file. 

## Example from top few lines of ipynb file
![image](https://github.com/draftd01/dl_final_project/assets/60448623/e8a75dba-45eb-4037-9e1e-5b7f38f86be1)

# Results
Our final model metric results can be viewed in the last few cells of the daniel_project_code.ipynb, which include average accuracy, false negative rate, recall, and precision across the defined test set.

![image](https://github.com/draftd01/dl_final_project/assets/60448623/bc488500-b95a-4a57-9c89-2603fba05f29)

![image](https://github.com/draftd01/dl_final_project/assets/60448623/3ea1c83c-5d09-454f-a689-d2861d01edac)

