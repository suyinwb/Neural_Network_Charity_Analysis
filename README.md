# Neural Network Charity Analysis

## Background

Help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Overview of Project

### Purpose

From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

* EIN and NAME—Identification columns
* APPLICATION_TYPE—Alphabet Soup application type
* AFFILIATION—Affiliated sector of industry
* CLASSIFICATION—Government organization classification
* USE_CASE—Use case for funding
* ORGANIZATION—Organization type
* STATUS—Active status
* INCOME_AMT—Income classification
* SPECIAL_CONSIDERATIONS—Special consideration for application
* ASK_AMT—Funding amount requested
* IS_SUCCESSFUL—Was the money used effectively

## Analysis And Challenges

## Methodology: Analytics Paradigm

#### 1. Decomposing the Ask
* Deliverable 1: Preprocessing Data for a Neural Network Model
* Deliverable 2: Compile, Train, and Evaluate the Model
* Deliverable 3: Optimize the Model
* Deliverable 4: A Written Report on the Neural Network Model

#### 2. Identify the Datasource
* charity_data.csv

### 3. Define Strategy & Metrics
**Resource:** Python, numpy, pandas, path, hvplot.pandas, sklearn, plotly.express, StandardScaler, MinMaxScaler, PCA, KMeans

#### 4. Data Retrieval Plan
NA

#### 5. Assemble & Clean the Data
The processing is done in [Data Preprocessing](#data-preprocessing)

#### 6. Analyse for Trends

The analysis is indicated below in [Analysis](#analysis)

#### 7. Acknowledging Limitations
Need more knowledge on statistics.

#### 8. Making the Call:
The "Proper" Conclusion is indicated below in [Summary](#summary)

## Analysis

The first model yields the results below:
268/268 - 1s - loss: 0.5555 - accuracy: 0.7273
Loss: 0.5555166602134705, Accuracy: 0.7273469567298889

This shows that it is only 72.73% accurate.

### Data Preprocessing
1. What variable(s) are considered the target(s) for your model?

IS_SUCCESSFUL is the target for the model because this indicate that the applicant is successful.

2. What variable(s) are considered to be the features for your model?

NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE	STATUS, INCOME_AMT, ASK_AMT.
In this case, Name is the most important feature in this model as there are companies like PARENT BOOSTER USA INC that had applied 1260 times.

3. What variable(s) are neither targets nor features, and should be removed from the input data?

EIN

### Compiling, Training, and Evaluating the Model

1. How many neurons, layers, and activation functions did you select for your neural network model, and why?

I've kept the original model as recommended. See below.
* Activation function: RELU
* Epochs: 100
2 hidden layers and their corresponding nodes:
* hidden_nodes_layer1 = 80
* hidden_nodes_layer2 = 30

The reason is changing these parameters did not yield better accuracy results. See explanation below in [Optimize your model in order to achieve a target predictive accuracy higher than 75%](#optimize-your-model-in-order-to-achieve-a-target-predictive-accuracy-higher-than-75)

2. Were you able to achieve the target model performance?

Yes.

3. What steps did you take to try and increase model performance?

By adding "NAME" feature.

### Optimize your model in order to achieve a target predictive accuracy higher than 75%

The biggest factor in achieving the target of more than 75% accuracy is by adding feature "NAME". By Adding this feature, the model was able to increase the accuracy to 79.15%. See results below.

268/268 - 1s - loss: 0.4557 - accuracy: 0.7915
Loss: 0.4556748569011688, Accuracy: 0.7914868593215942

Subsequently changing the activation function and adding another hidden layer did not improve the model by much. at most 0.1%. See results below.

Activation function Sigmoid:

268/268 - 1s - loss: 0.4415 - accuracy: 0.7923
Loss: 0.4415421187877655, Accuracy: 0.792303204536438

Adding hidden layer 3:

268/268 - 1s - loss: 0.4552 - accuracy: 0.7918
Loss: 0.4551962912082672, Accuracy: 0.7918367385864258

## Summary

This new optimised model can predict the success of each applicant with 79.15% accuracy if funded by Alphabet Soup.
With the same dataset, another more suitable model such as Support vector machines (SVMs) would be less resource intensive and also produces good classification results.  

## Appendix

Adjusting the input data to ensure that there are no variables or outliers that are causing confusion in the model, such as:
* Dropping more or fewer columns.
* Creating more bins for rare occurrences in columns.
* Increasing or decreasing the number of values for each bin.
* Adding more neurons to a hidden layer.
* Adding more hidden layers.
* Using different activation functions for the hidden layers.
* Adding or reducing the number of epochs to the training regimen.


### References
