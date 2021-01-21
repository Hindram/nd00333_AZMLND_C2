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

The diagram below shows the steps followed in implementing the project:
![](Screenshots/Architectural-Diagram.png)

- Authentication: Create a Security Principal to associate with the Azure Workspace.
- Automated ML Experiment: Create experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment.
- Cleaning & Training the model: Automl will validate and clean the data then train it with several algorithms. 
- Deploy the best model: Deploy the model with the highest accuracy rate and move it to production.
- Enable insights & logging: To monitor model behavior and get detailed information about the running processes. 
- Swagger Documentation : Consume the deployed model using Swagger.
- Interact with model & benchmark: consume the endpoint using test records by running enpoint.py script, load and test the model using benchmark.sh script.
- Create & publish pipeline: Create & publishing a pipeline using Python SDK. 

## Key Steps

#### Step 1: Authentication
Since I worked with Udacity lab, I have skipped this step as I'm not authorized to create a security principal. 

#### Step 2: Automated ML Experiment
In this step, I have created a new experiment using Automated ML and the bank marketing registered dataset, created and configured a compute cluster, and used it to run the experiment. I have selected 'y' column as the target column.

###### Screenshot 1: Registerd Dataset
![](Screenshots/registerd-ds.png)

After selecting the registered bank marketing dataset, I have created the automl model using Standard_DS12_v2 compute cluster type for the VM with 1 minimum number of nodes. I have selected classification as the type of experiment & enabled explain best model options to get the best model with the highest accuracy out of all runs with the best algorithm for the task. The experiment has been completed after training the dataset with many models.

##### Screenshot 2: Creating Automl Experiment 
![](Screenshots/creating-expt.png)

##### Screenshot 3: Automl Experiment Completed 
![](Screenshots/expt-completed-detl-w-best-model.png)

##### Screenshot 4: Best Model
The best model was a VotingEnsemble pipeline with 0.918 accuracy rate. 
![](Screenshots/expt-models.png)

#### Step 3: Deploy the Best Model
In this step, I deployed the best model while enabling authentication and Azure Container Instance (ACI). Later, the deployed model showed in the endpoints section.

##### Screenshot 5: Deploy Best Model 
![](Screenshots/deploy-best-model.png)

##### Screenshot 6: Deployed Model Endpoint
![](Screenshots/deployment-endpoint.png)

#### Step 4: Enable Application Insights
From the deployed best model, I have enabled application insights and retrieve logs. This step will help in detecting failures, anomalies...etc in the model. The executed code in logs.py enables Application Insights. Application Insights were disabled before running logs.py script.

##### Screenshot 7: Before Enabling Application Insights 
![](Screenshots/before-enabling-insghts.png)

##### Screenshot 8: After Enabling Application Insights
![](Screenshots/after-enabling-insights.png)

##### Screenshot 9: Enable Logs by running logs.py script
![](Screenshots/py-logs.png)
![](Screenshots/logs-cont.png)

#### Step 5: Swagger Documentation
A swagger is a tool used to document and consume RESTful web services with APIs in GET & POST HTTP requests. To enable swagger I have run serve.py script in port 8000 and swagger.sh in port 9000. Then, interact with the swagger instance and retrieve its response from localhost. 

##### Screenshot 10: Running swagger.sh 
![](Screenshots/bash-swagger.png)


##### Screenshot 11, 12, 13: API Interaction 
Best model documentation showed by swagger 

![](Screenshots/API-interaction.png)
![](Screenshots/API-result.png)
![](Screenshots/API-result-cont.png)

#### Step 6: Consume Model Endpoints
In this step, I have interacted with the trained model using endpoint.py script updating the score url & Key. After running the code, it produced a JSON output response. Also, to load & test my model, I executed the benchmark bash script. 

##### Screenshot 14: Consume Endpoint 
![](Screenshots/endpoint-response.png)

##### Screenshot 15, 16: Benchmark 
![](Screenshots/benchmark-run.png)
![](Screenshots/benchmark-run-2.png)

#### Step 7: Create, Publish and Consume a Pipeline
I have updated the Jupyter Notebook with the dataset, cluster, keys, and model names and created the pipline.Then, published the pipeline using python SDK.

##### Screenshot 17, 18: Creating Pipeline 
![](Screenshots/create-pip.png)
![](Screenshots/creating-pipline-running.png)

##### Screenshot 19, 20: RunDetails Widget of the Pipeline
![](Screenshots/pythonsdk-pip-widget.png)
![](Screenshots/pysdk-pip-widget-dtls.png)

##### Screenshot 21: Completed Pipelines 
![](Screenshots/pip-completed.png)

##### Screenshot 22: Rest Pipeline from pyhon SDK
![](Screenshots/pips-runs-completed.png)

##### Screenshot 23, 24 Published Pipeline showing a REST endpoint
The REST endpoint shows a status as Active.

![](Screenshots/pysdk-publish-pip.png)
![](Screenshots/pip-endpoint-detl.png)

## Screen Recording
[Click Here](https://www.loom.com/share/71e5770326d34e2da6be697d85df232f)

## Standout Suggestions
* I would resolve the imbalance issue in the dataset to prevent the bias that could impact the prediction. This type of issue is common in Classification problems.
* I would try enabling azure ml features such as deep learning option when training the model, this could improve the accuracy. 
* Test the model with new records and evaluate the model behavior instead of the existing records.

