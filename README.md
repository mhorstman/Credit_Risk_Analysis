# Credit Risk Analysis

## Overview
The purpose of this analysis is to use various machine learning techniques on a credit card dataset from LedningClub, a peer-to-peer lending service company, to predict credit risk. The analysis compares results from oversampling algorithms (RandomOverSampler and SMOTE), an undersampling algorithm (ClusterCentroids), and a combination over/undersampling algorithm (SMOTEENN). The analysis then compares two machine learning models that reduce bias (BalancedRandomForestClassifier and EasyEnsembleClassifier).

### Resources
**Input**: credit_risk_resampling_starter_code.ipynb, credit_risk_ensemble_starter_code.ipynb, LoanStats_2019Q1.csv <br/>
**Software/Tools**: Python 3.7, Jupyter Notebook <br/>
**Output**: credit_risk_resampling.ipynb, credit_risk_ensemble.ipynb, GitHub ReadMe <br/>

## Results
The following section shows the results of the 6 machine learning models that were run against the credit card dataset. From these results we see that none of the models are great at predicting credit risk for high-risk people. Of all the models the EasyEnsembleClassifier was clearly the best with the highest accuracy, very good prediction of low-risk, and marginal prediction of high-risk. The detailed results section below contains additional detail on the results of each of the models.

### Summary Table
![SummaryTable](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/SummaryTable.png)

### Detailed Resuilts
The following shows the detailed results for the 6 models run. The key metrics from these results are accuracy score, precision (pre), recall (rec) and f1.

![RandomOverSample](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/RandomOverSample.png)

![SMOTE](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/SMOTE.png)

![CluseredCentroids](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/CluseredCentroids.png)

![SMOTEENN](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/SMOTEENN.png)

![BalancedRandomForest](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/BalancedRandomForest.png)

![EasyEnsembleClassifier](https://github.com/mhorstman/Credit_Risk_Analysis/blob/main/Output/EasyEnsembleClassifier.png)

## Summary
As seen in the results above, the EasyEnsembleClassifier is the best model for predicting credit risk of all the models tested.  
- For low-risk the precision was 1.00 which indicates that the model was nearly perfect at identifying low-risk people with nearly zero high-risk people misclassified in this dataset. The recall was 0.94 which indicates that a relatively small number of low-risk people were mis-classified as high-risk.
- For high-risk the precision was 0.09 which indicates that there were more low-risk people mis-classified than actual high-risk caught by the model. This is due to the overall low number of high-risk people in the dataset. The recall was 0.92 which indicates a low number of high-risk people were mis-classified. 

Since the bank is mostly concerned with ensuring credit is provided to low-risk people only, this model does a very good job and it is my recommendation to implement this model going forward. The relatively small number of low-risk people mis-classified should be handled by manual appeal or additional models investigated to further reduce that number. 