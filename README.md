# Credit Risk Analysis: Unsupervised Machine Learning 
## Overview
### The objective of this exercise was to use an unsupervised machine learning module to sort out a large unbalanced data set of loans to predict which ones would be considered "good", where they would be paid back and "high risk", which would mean they would be likely defaulted. Bother oversampling and under sampling algorithms were conducted for this data set.
## Results
### First the null values were dropped out of the data set so that the algorithms would work correctly. A " High Risk" loan status was assigned to any loan with a status in the following:
- Late (31-120 days)
- Late (16-30 days)
- Default
- In Grace Period
### If a loan did not meet this criteria, it was considered a "good" low risk loan.
## Summary
### After the data was cleaned there was a total of 68,470 low risk applicants, and 347 high risk applicants. Utilizing the python libraries scikit-learn and imbalanced-learn, we split the data into a 75/25% split data set for training vs testing for various analysis using various methods
# Oversampling
![image1](/Resources/oversample.png)
### The RandomOverSampler model randomly takes data from the minority category and adds it to the training set until they are both equivalent, resulting in 51,366 high risk loan groups and 51,366 low risk loan groups. This provided a balanced accuracy score of 66% for this test.
![image2](/Resources/oversampleresults.png)
### - The high risk precision rate was 1% with the recall at 72%
### - The low risk precision rate was 100% with a recall at 60
## SMOTE
![image3](/Resources/smote.png)
### Using the Synthetic Minority Oversampling Technique model (or SMOTE), also increases the size of the minority class by creating new values based on the values of the current minority data set, instead of by random selection. This provided a balanced accuracy of 65% for this test.
![image4](/Resources/smoteresults.png)
### - The high risk precision rate was 1% with the recall at 61%
### - The low risk precision rate was 100% with a recall at 70%
## Under sampling
![image5](/Resources/undersample.png)
### Using ClusterCentroids Model, we clustered together alike data in the majority class to represent all clusters. This set a total of 246 high and low risk test groups. This provided a balanced accuracy score of 54% for this algorithm. 
![image6](/Resources/undersampleresults.png)
### -The high risk precision rate was 1% with the recall at 69%
### -The low risk precision rate was 100% with a recall at 40%
## Combination Sampling
![image7](/Resources/smoteenn.png)
### Using the Synthetic Minority Oversampling Technique + Edited NearestNeighbors Model (or SMOTEENN), we strike a balance of over and under sampling by boosting both data sets to a higher amount. This had a balanced accuracy score of 64%
![image8](/Resources/smoteennresults.png)
### -The high risk precision rate was 1% with a recall of 72%
### -The low risk precision was at 100% with a recall at 57%
## Additional Machine learning
![image9](/Resources/forest.png)
### The BalancedRandomForestClassifier Model takes two trees of a similar size to the minority class that are used to represent both the majority and minority class. This algorithm had a balanced accuracy score of 78%.
### - The high risk precision rate was 4% with the recall at 67%
### - The low risk precision was at 100% with a recall at 91%
![image10](/Resources/forestresults.png)
### Lastly, the EasyEnsembleClassifier Model is a set of classifiers where individual decisions are combined into new examples. The balanced accuracy score of this method was 93%
![image11](/Resources/easy.png)
### - The high risk precision rate was 7% with the recall at 91%
### - The low risk precision was at 100% with a recall at 94%
![image12](/Resources/easyresults.png)
# Summary
### In summary, there were six different models of machine learning used to test this data set with varying results for accuracy and precision. The Easy Ensemble Classifier preformed the best with an accuracy rate of 93% and a 7% precision rate predicting high risk candidates. The sensitivity of these calculations (recall) was also the highest at 91% compared to the other methods. The performance for low risk candidates was also stellar with a precision rate of 100% and a sensitivity of 94%. Therefore I would recommend this model above all others. However I would like to note that machine learning algorithms do have shortcomings in the context of the problems they are applied to, where in a business sense it may be better to deny a loan to a qualified candidate than to let a high risk candidate through the process, so the margin of risk that someone takes on while using this method may not be tolerable depending on the setting.
