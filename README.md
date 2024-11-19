# deep-learning-challenge
Module_21_Challenge_Neural_Networks_Deep_Learning

## Overview
In this challenge, we analyze a dataset provided by the nonprofit organization Alphabet Soup.
The goal is to develop a machine learning model capable of predicting which applicants are most likely to succeed if funded by Alphabet Soup.

## Results
In the original machine learning model, the target predictive accuracy was lower than 75%.
It resulted in an accuracy of 0.7287 and a loss of 0.5641.

I then made three attempts to optimize the machine learning model to achieve a target predictive accuracy higher than 75%.

In my first attempt, I achieved an accuracy of 0.7313 and a loss of 0.5988.
In my second attempt, I achieved an accuracy of 0.7285 and a loss of 0.6160.
In my third attempt, I achieved an accuracy of 0.7610 and a loss of 0.5345.

## Data Preprocessing
In the original machine learning model, I dropped the 'EIN' and 'NAME' columns. The target variable is the 'IS_SUCCESSFUL' column,
and the 'APPLICATION_TYPE' and 'CLASSIFICATION' columns were binned to help clean up the data.

In the first attempt, the only change I made was adjusting the cutoff value from 500 to 1000 in the 'APPLICATION_TYPE'.

In the second attempt, I also dropped the 'STATUS' column, adjusted the cutoff value for 'APPLICATION_TYPE' to 200,
and adjusted the cutoff value for 'CLASSIFICATION' to 200.

In the third attempt, I only dropped the 'EIN' column. I then binned the 'NAME' column with a cutoff value of 40.
I did not make any adjustments to the cutoff values of the 'APPLICATION_TYPE' and 'CLASSIFICATION' columns.

For all three attempts, I kept the 'IS_SUCCESSFUL' column as the target variable.

## Compiling, Training, and Evaluating the Module
In the original machine learning model, the Perceptron only contained two hidden layers and an output layer.
The first layer had 80 nodes and the second layer had 30 nodes. We used a 'ReLU' activation function with 100 epochs.

In the first attempt of optimization, I added a third hidden layer and increased the number of units for optimization.
The first layer had 120 nodes, the second layer had 80 nodes, and the third layer had 40 nodes.

In the second attempt, I had a total of 5 hidden layers to attempt to optimize the model.
The hidden layers had 200, 150, 100, 50, and 25 nodes. With this model, I used 200 epochs.

In the third attempt, I scaled back to just 3 hidden layers. I increased the number of nodes to 160, 80, and 40.
I also scaled back the number of epochs to 100.

For all three attempts, I used the 'ReLU' activation function.

## Summary
In summary, I was able to achieve a predictive accuracy of 76.10%, surpassing the target of 75%. This required quite a bit of experimenting with the features, bin
cutoff values, and the architecture of the neural network, including adjustments to the layers, nodes, and epochs.

Initially, I thought a slight adjustment would be needed since the original model already had a decent accuracy of 72.87%. In my first attempt, I adjusted the bin
cutoff for 'APPLICATION_TYPE', which brought the accuracy up slightly to 73.13%, but it wasn’t enough to meet the target.

For the second attempt, I tried a more complex approach, dropping the 'STATUS' column, refining the bin cutoffs further, and significantly increasing the number of
layers, nodes, and epochs. However, this was unsuccessful, as the accuracy dropped to 72.85% and the loss increased.

In the third and final attempt, I decided to simplify the approach. I reintroduced the 'NAME' column with binning, kept the original cutoffs for 'APPLICATION_TYPE' and
'CLASSIFICATION', and scaled back the architecture to three hidden layers with 100 epochs. This strategy worked the best, achieving 76.10% accuracy and a loss of 0.5345
while keeping the model balanced and efficient.

This model worked by making predictions based on the input features, but using Random Forest could improve performance. Random Forest would combine multiple decision
trees, making predictions more accurate and reducing the risk of overfitting.