# Crypto_Currency_prediction
- This notebook displays a recurrent neural network to predict against a time-series dataset, which is going to be cryptocurrency prices. Which further predicts whether we should buy/sell.

## Technical Requirements:
- Tensorflow
- Keras
- Python

## Overview:
- The data I will be using is Open, High, Low, Close, Volume data for Bitcoin, Ethereum, Litecoin and Bitcoin Cash.
- Our main focus here is on **Close and Volume columns.**
  - The **Close column** measures the final price at the end of each interval. In this case, these are 1 minute intervals. So, at the end of each minute, what was the price of the asset
  - The **Volume column** is how much of the asset was traded per each interval, in this case, per 1 minute.
  
## Input Parameters:
- First, we need to combine price and volume for each coin into a single featureset, then we want to take these featuresets and combine them into sequences of 60 of these featuresets. This will be our input.

## Output Parameter:
-  we're trying to predict if price will rise or fall. So, we need to take the **prices** of the item we're trying to predict. Let's stick with saying we're trying to predict the price of Litecoin. So we need to grab the future price of Litecoin, then determine if it's higher or lower to the current price. We need to do this at every step.

## Preparing the dataset:
- Balance the dataset between buys and sells
- Scale/normalize the data
- Create reasonable out of sample data that works with the problem
- Divided the dataset into 40k train data and 41K validation_data

## Machine Learning Alogorithm:
- We use LSTM model to predict the prices.
- Used Sequential from keras to build the model.
- Created a 5 layer model
- Added Dropout and BatchNormalisation on every layer.
- Used **ADAM** optimizer and loss was calculated using **sparse_categorical_crossentropy**.
- The model gave us an accuracy on 54.5%

