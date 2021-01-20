# Project: Operationalizing Machine Learning

## Table of content
* [Overview](#overview)
* [Architectural Diagram](#architectural-diagram)
* [Key Steps](#key-steps)
* [Screen Recording](#screen-recording)
* [Future work](#standout-suggestions)

## Overview
In this project, we will use the Bank Marketing dataset. This dataset shows information about the marketing campaign of a bank. The aim of the analysis is to predict potential customers who are willing to contribute to the bank's future loan or deposit plans. Hence, improving the overall future performance. We will use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. We will also create, publish, and consume a pipeline. 

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps

#### Step 1: Authentication
Since I worked with Udacity lab, I have skipped this step as I'm not authorized to create a security principal. 

#### Step 2: Automated ML Experiment
In this step, I have created a new experiment using Automated ML and the bank marketing registered dataset, created and configured a compute cluster, and used it to run the experiment.

###### Registerd Dataset Screenshot
![](Screenshots/registerd-ds.png)

##### Creating Automl Experiment Screenshot
![](Screenshots/creating-expt.png)

##### Automl Experiment Completed Screenshot
![](Screenshots/expt-completed-detl-w-best-model.png)

##### Best Model Screenshot
The best model was a VotingEnsemble pipeline with 0.918 accuracy rate. 
![](Screenshots/expt-models.png)

#### Step 3: Deploy the Best Model

## Screen Recording
[Click Here](https://www.loom.com/share/3727c42fa67f4288a224d28c78d495cb)

## Standout Suggestions
* I would resolve the imbalance issue in the dataset to prevent the bias that could impact the prediction. This type of issue is common in Classification problems.
* I would try enabling azure ml features such as deep learning option when training the model, this could improve the accuracy. 
* Test the model with new records and evaluate the model behavior instead of the existing records.

