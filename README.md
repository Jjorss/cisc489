# cisc489

Research proposal
https://docs.google.com/document/d/1InT-A8FoZubg3esio2vVZCb5J0ZSNX5nXT1fN7oPtKA/edit

# Asteroid Classification by Features and Profitability
### By Emily McNeil, Eric Kurtz, Jackson Jorrs

## Abstract
Our goal is to determine an asteroid’s profitability based on the current data collected. The dataset we’ve obtained was pulled from the Asterank database, which was initally assembled via the NASA JPL Small Body database. As of now, Asterank estimates profitability based on the various attributes of an asteroid and its ease of accessibility. This undoubtedly is useful, but it is unclear how accurate this prediction is. Our research hopes to improve accuracy in the prediction of profitability. Space exploration is currently on the verge of a paradigm shift, and we believe the results produced by our research will help make asteroid mining transform from fiction to reality.

## Introduction
* Space exploration could be only a few decades away. If there was a clearly defined financial incentive for companies and private entities to launch space missions, space travel and colonization of space could be more feasible.

* Classifying asteroids is something that is quite frequently done by scientists around the world. However, classifying based specifically on profitability is not. 
![picture](https://github.com/Jjorss/cisc489/blob/master/images/ryugu.png)
The asteroid Ryugu, with a estimated profitability of 30.4 Billion (Asterank)

## Purpose and Research Question
* The purpose of this research project was initially to classify asteroids based on potential profitability. 

* Using an data from an open-source project called AsterRank, we aimed to predict whether an asteroid would be profitable for a mining mission using based on features such as mass and closeness, using logistic regression and clustering.

## Subject, Method, and Analysis

* We obtained our data set from the Asterank database. This database pull asteroid data from the Nasa/JPL small body database and various published asteroid mass data. We choose this data due to the ease of use and access of their API.

* Asterank has its own algorithm for predicting cost efficiency. Our aim was to calculate this in a more accurate way. Our first step was to run a clustering algorithm on our data set. This was to determine which attributes had the most impact on the profit of an asteroid. The attributes we found that had the most impact on profit were closeness and mass. Once obtained, we then trained our machine learning model with the attributes.

* We created a column in our dataset that marked if an asteroid was high profit or not base on if its profit was in the 75th percentile.

* We used a linear regression model to determine which asteroids were most profitable. Our data set contained 1000 asteroids. We used 800 to train the model and the 200 remaining for verfication.

* overall we were able to correctly determine if an asteroid is profitable or not with 88% accuracy. Our AUC was 68%. Our model we have trained did not preform to expectations and we plan to improve upom it in further research.

## Results (edit needs explainations)
![picture](https://github.com/Jjorss/cisc489/blob/master/images/LogLoss.png)
* Our model improved over periods as displayed here by logloss.
* However, the same improvement was not seen on the validation set. A potential cause of this is overfitting.
![picture](https://github.com/Jjorss/cisc489/blob/master/images/ROC_curve.png)
* AUC (Area under ROC curve) 
* Graph indicates that our model is better than guessing (AUC of .5)
* Our logistic regression model predicted whether an asteroids profitability was above the 3rd quantitle with an 88% accuracy on the validation set.
![picture](https://github.com/Jjorss/cisc489/blob/master/images/parameters_learning%20model.png)
* Trained a logistic regression model as a classifier using batched gradient descent. 
* Instances are divided into batches of 10, and model error is calculated. 
* Error is then used to update weights of the logistic regression model. 
* Testing found that these parameters produced the best model.

## Conclusions
* As of now, no conclusions can realistically be made from our research. 
* Classifying asteroids by this metric with machine learning suffers from the simple fact that there is no validation data yet. * No one has attempted to mine an asteroid, or even anything tangentially related. 
* As a result, there is absolutely no validation data. We don't know if our model is correct because there's no validation set available.
* Cleaner data with respect to the spectral type of the asteroid would result in a more conclusive classification model. 

## Direction for Future Research
* The tensorflow functions that we used were not distributed tensorflow - this project would benefit from being parallelized to try clustering with randomized attributes. 
* Would also benefit from re-coding the attributes based on quartile above the median profit.
* Also, examining the estimated composition of different minerals and seeing how that correlates with profitability. Currently the model is created with proximity and asteroid size as heavily weighted factors. This is reasonable - the current cost of leaving the Earth’s atmosphere means that we should seek to get the most bang for our buck.
* Furthermore, examining whether we can find proximally tight clusters with high probability would be a great way to achieve the above bullet point.

# Link to Google Notebook
https://drive.google.com/open?id=1IfEuc6LIbYaWwKtO111fPA79yEYovQ-e
## How to Reproduce Results
1. Download full dataset
2. Go to Google Notebook
3. Run Each cell, First cell will prompt you to upload the full dataset.
