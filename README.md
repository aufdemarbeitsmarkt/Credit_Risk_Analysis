# Credit_Risk_Analysis

## Overview

In this exercise, we used `sci-kit` and `imbalanced-learn` to employ several resampling techniques to train and evaluate unsupervised machine learning models on a credit card credit dataset from LendingClub. 

We employed the following techniques to predict credit risk: 
* Naive random oversampling
* SMOTE oversampling algorithm
* Cluster Centroids undersampling algorithm
* SMOTEENN over and undersampling algorithm
* Random Forest 
* Easy Ensemble

Once we completed training our models, we evaluated their performance, making a determination whether they should be used to predict credit risk. 


## Results

The table below describes the results of our assessment of each model, generated by the code found in [credit_risk_resampling.ipynb](credit_risk_resampling.ipynb) and [credit_risk_ensemble.ipynb](credit_risk_ensemble.ipynb). 

| Model Name                      | Accuracy | Precision   |  Recall  | Confusion Matrix                  |
|---------------------------------|----------|-------------|----------|-----------------------------------|
| Naive Random Oversampling       | 0.66     |    0.01     |   0.70   | [[   71,  30],  [ 6718, 10386]]   |
| SMOTE Oversampling              | 0.66     |    0.01     |   0.63   | [[   64,  37],  [ 5283, 11821]]   |
| Cluster Centroids Undersampling | 0.54     |    0.01     |   0.77   | [[   70,  31],  [10340,  6764]]   |
| SMOTEENN Over & Undersampling   | 0.67     |    0.01     |   0.76   | [[   77,  24],  [ 7199,  9905]]   |
| Random Forest                   | 0.68     |    0.88     |   0.37   | [[   37,  64],  [    5, 17099]]   |
| Easy Ensemble                   | 0.93     |    0.09     |   0.92   | [[   93,   8],  [  983, 16121]]   |




## Summary

All of the resampling techniques lead to average results overall, but especially poor precision. By contrast our ensemble methods generally had better accuracy with higher values in both precision and recall. However, as we see in the table above, Random Forest and Easy Ensemble have somewhat "opposite" scores -- Random Forest performed better in precision and Easy Ensemble performed better in recall. Of these two ensemble methods, Easy Ensemble had the highest accuracy score. 

With that said, it might be tempting to choose the Easy Ensemble method for predicting credit risk, but let's take a closer look at the Random Forest method's results. 

Random Forest had the highest precision of any model. With that, it also had the lowest number of false positives (5), meaning its impact on the financial well-being of potenial lendees is greatly minimized. In other words, an individual  seeking out a loan, will be less likely to be deemed as a risk when they are in fact not a risk. As well, it has the highest number of true negatives, which means this model correctly identified the highest number of low risk potential lendees. For this reason, we recommend using Random Forest methods for predicting credit risk. 