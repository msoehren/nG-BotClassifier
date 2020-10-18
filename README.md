# nodeGame-BotClassifier

# Description 

This repository was created for the Seminar "Design and Implementation of Online Behavioral Experiments". 
The goal of this project is to build a bot classifier that outputs probabilistic scores wheter a participant of a nodeGame survey is a bot or not. 

# Current Status 

## Feature selection

Descriptive analysis showed strong differences in variables related to meta information of the user. Besides choosing these variables as features other variables were choosen (for now) out of theoretical intutiotn as well. The variable "feedback" was used to create further features. Using the Bag-of-words approach, the 300 most common words in these feedback answers were created as unique numeric. A word count variable which counts the amount of words written in the feedback variable was created as well since descriptive analysis showed that bots only write half as much words as non-bots.  

## Class Imbalance 

A large challenge in this project is the high class imbalance in the target variable. Only 6 % of the instances in this data are labeled as bots and therefore training and testing the model is difficult. Class Imbalance was handled by creating synthetic data in the training set with SMOTE (Chawla, N. V. and Bowyer, K. W. and Hall, L. O. and Kegelmeyer, W. P., "{SMOTE}: synthetic minority over-sampling technique" , Journal of Artificial Intelligence Research, 2002, pp. 321--357). 

## Models

At the moment, models were trained (and tuned) with the following algorithms : KNN, Adaboost, XGB, ExtraTrees, C5.0. 

XGB (<i> parameters: nrounds = 50, max_depth = 3, eta = 0.4 gamma = 0, colsample_bytree = 0.8, min_child_weight = 1, subsample = 1 </i>) currently performs the best out of all these models with <b> Accuracy of 96% </b> Sensitivity is 0.82 & Specificity is 0.97 which means that the model accurately could identify 97% of non-bots, 82% of bots and therefore surpassed the no information rate which was pretty high (0.941) because of class imbalance. One has to keep in mind that the model did not have many cases of bots so Sensitivity could increase with more data. 


