# Module_12_Challenge

## Credit Risk Analysis Report

## Overview of the Analysis

This analysis assesses the creditworthiness of borrowers for a peer-to-peer lending services company. 

The analysis is based on the following historical information from borrowers:

* Loan size
* Interest rate
* Borrower income
* Debt to Income Ratio
* Number of Accounts
* Derogotary Marks
* Total Debt
* Loan Status (Healthy 0 or High-Risk 1)

Using the information provided, the model was trained to try to predict the Loan Status as healthy or high-risk.

The Loan Status was split out from the rest of the data and then both were split into training and testing datasets using train_test_split from [sklearn](https://scikit-learn.org/stable/). 

Using sklearn, a Logistic Regression was run on the split data. 

The data was then resampled to take account of the low number of high-risk loans compared to healthy loans. 

A logistic regression analysis was then completed on the resampled data.

## Results

* Machine Learning Model 1: Logistic Regression
    * Acccuracy: 95%
    * Precision: 99%
        100% (almost) for healthy loans
        84% for high-risk loans
    * Recall: 99% 
        99% for healthy loands
        92% for high-risk loans

    * 18676 true positives
    * 104 false negatives
    * 554 true negatives
    * 50 false positives

* Machine Learning Model 2: Resampled Logistic Regression
    * Acccuracy: 99%
    * Precision: 99%
        100% (almost) for healthy loans
        83% for high-risk loans
    * Recall: 99% 
        99% for healthy loans
        99% for high-risk loans
    * 18661 true positives
    * 119 false negatives
    * 600 true negatives
    * 4 false positives

## Summary

The purpose of this model is to correctly predict the high-risk loans amongst the peer-to-peer lenders. 

The number that needs to be minimised is the false negative (predicted as Healthy but should be High-Risk).

The recall value illustrates the percentage of predicted high-risk as a portion of all real high-risk cases. The higher the recall value, the lower the false negatives.

Both models have an overall recall of 99% but the dataset is skewed by the number of healthy loans compared to high-risk. Looking at the recall value for the high-risk loans, Model 1 predicts 83% and Model 2 predicts 99% correctly. 

The overall accuracy increased from 95% in Model 1 to 99% in Model 2. 

This translates to 50 high-risk loans being categorised as healthy in Model 1 and only 4 in Model 2.

I recommend using Model 2 for this dataset.


