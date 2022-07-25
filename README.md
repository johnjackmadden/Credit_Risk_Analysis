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
![image1](/Resources/oversample.png)
### The RandomOverSampler model randomly takes data from the minority category and adds it to the training set until they are both equivilent, resulting in 51,366 high risk loan groups and 51,366 low risk loan groups. This provided a balanced accuracy score of 66% for this test.
![image2](/Resources/oversampleresults.png)
### - The high risk precision rate was 1% with the ceall at 72%
### - The low risk precision rate was 100% with a recall at 60
## SMOTE
![image3](/Resources/smote.png)
### Using the Synthetic Minoirty Oversampling Technique model (or SMOTE), also increasees the size of the minority class by creating new values based on the values of the current minority data set, instead of by random seletion. This provided a balanced accurracy of 65% for this test.
![image4](/Resources/smoteresults.png)
### - The high risk precision rate was 1% with the ceall at 61%
### - The low risk precision rate was 100% with a recall at 70%
## Undersampling
![image5](/Resources/undersample.png)
### Using ClusterCentroids Model, we clustered together alike data inm het majority class to represent all clusters. This set a total of 246 high and low risk test groups. This provided a balanced accuracy score of 54% for this alogrithym. 
![image6](/Resources/undersampleresults.png)
### -The high risk precision rate was 1% with the ceall at 69%
### -The low risk precision rate was 100% with a recall at 40%
## Combination Sampling
![image7](/Resources/smoteenn.png)
### Using the Synthetic Minority Oversamplignm Technique + Edited NearestNeighbors Model (or SMOTEENN), we strike a balance of over and undersampling by boosting both data sets to a higher amount. This had a balanced accuracy score of 64%
![image8](/Resources/smoteenn.png)
### -The high risk precision rate was 1% with a recall of 72%
### -The low risk precision was at 100% with a recall at 57%
## Additional Machine learning
![image9](/Resources/forest.png)
### The BalancedRandomForestClassifier Model takes two trees of a similar size to the minoirty class that are used to represent both the majority and minority class. This algorythm had a balanced accuracy score of 78%.
### - The high risk precision rate was 4% with the ceall at 67%
### - The low risk precision was at 100% with a recall at 91%
![image10](/Resources/forestresults.png)
### Lastly, the EasyEnsembleClassifier Model is a set of classifiers where individual decisions are combined into new examples. The balanced accuracy score of this method was 93%
![image11](/Resources/easy.png)
### - The high risk precision rate was 7% with the ceall at 91%
### - The low risk precision was at 100% with a recall at 94%
![image12](/Resources/easyresults.png)
# Summary
### In summary, there were six different models of machine learning used to test this data set with varying results for accuracy and precision. The Easy Ensemble Classifier preformed the best with an accuracy rate of 93% and a 7% precision rate predicting high risk canidates. The sensitivity of these calculations (recall) was also the highest at 91% compared to the other methods. The preformance for low risk canidates was also stellar with a precision rate of 100% and a sensitvitry of 94%. Therefore I would reccomend this model above all others. However I would like to note that machine learning algorithyms do have shortcomings in the context of the probelms they are applied to, where in a business sense it may be better to deny a loan to a qualified canidate than to let a high risk canidate through the process, so the margin of risk that someone takes on while using this method may not be tolerable depending on the setting.
