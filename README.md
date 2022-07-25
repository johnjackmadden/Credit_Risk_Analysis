# Credit Risk Analysis: Unsupervised Machine Learning 
## Overview
### The objective of this exercise was to use an unsupervised machine learning module to sort out a large unbalanced data set of loans to predict which ones would be considered "good", where they would be paid back and "high risk", which would mean they would be likely defaulted. Bother oversampling and undersampling algorithms were conducted for this data set.
## Results
### First the null values were dropped out of the data set so that the algorims would work correctly. A " High Risk" loan status was assigned to any loan with a status in the following:
- Late (31-120 days)
- Late (16-30 days)
- Default
- In Grace Period
### If a loan did not meet this critera, it was considered a "good" low risk loan.
## Summary
### After the data was cleaned there was a total of 68,470 low risk applicants, and 347 high risk applicants. Utalizing the python libraries scikit-learn and imbalanced-learn, we split the data into a 75/25% split data set for training vs testing for various analysis using various methods
# Oversampling
### image1
### The RandomOverSampler model randomly takes data from the minority category and adds it to the training set until they are both equivilent, resulting in 51,366 high risk loan groups and 51,366 low risk loan groups. This provided a balanced accuracy score of 66% for this test.
### image 2
### - The high risk precision rate was 1% with the ceall at 72%
### - The low risk precision rate was 100% with a recall at 60
## SMOTE
### image 3
### Using the Synthetic Minoirty Oversampling Technique model (or SMOTE), also increasees the size of the minority class by creating new values based on the values of the current minority data set, instead of by random seletion. This provided a balanced accurracy of 65% for this test.
### image 4
### - The high risk precision rate was 1% with the ceall at 61%
### - The low risk precision rate was 100% with a recall at 70%
