# House-Price-Prediction-using-Amazon-Sagemaker-and-XGBoost

This repository contains code for predicting house prices using XGBoost, a popular machine learning algorithm. The dataset used for this project is the Boston Housing Dataset, which includes various features related to housing characteristics.

## Dataset
The dataset is loaded from a CSV file, and you can find the data [here](https://www.kaggle.com/code/prasadperera/the-boston-housing-dataset/input). The features include variables such as crime rate (CRIM), room count (RM), and others. The target variable is the median value of owner-occupied homes in $1000s (MEDV).

## Data Exploration
Data exploration is performed to understand the dataset and identify patterns. Key steps include:

- Displaying the first few rows of the dataset.
- Calculating summary statistics of numerical columns.
- Creating a correlation matrix heatmap to visualize relationships between variables.
- Checking for outliers using boxplots and identifying columns with potential outliers.
- Analyzing the distribution of the target variable 'medv'.
## Uploading data to s3
![Alt text](./1%20pushing%20dataset%20to%20s3.png)

## Model Training
The XGBoost model is trained using Amazon SageMaker. Key steps include:

- Preparing the dataset by splitting it into training and validation sets.
- Uploading the dataset to Amazon S3 for training.
- Configuring the XGBoost estimator with hyperparameters.
- Training the XGBoost model with the provided dataset.
- Deploying the trained model to an Amazon SageMaker endpoint for making predictions.
![Alt text](./2%20model%20training.png)

## Making Predictions
After deploying the model, predictions are made using a test sample. The code includes:

- Setting up the SageMaker endpoint for testing the deployed model.
- Generating a test sample without the target column.
- Serializing and deserializing data for prediction.
- Making predictions using the deployed endpoint and checking the results.

## Cleanup
To free up resources, the SageMaker endpoint is deleted after testing the deployed model.
