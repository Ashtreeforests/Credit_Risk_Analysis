# Credit_Risk_Analysis

## Overview
Application of machine learning to solve an issue associated with credit card risk.

As relatively safe loans substantiantally outnumber risky loans, credit risk is considered to be an inherently unbalanced classification problem. For this reason, this analysis required us to employ different techniques to train and evaluate models with unbalanced classes. We used an imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Credit card dataset was derived from LendingClub, which is a a peer-to-peer lending services company. 

The following methods were used as part of this analysis were used to predict credit risk: 

* oversample the data using the RandomOverSampler and SMOTE algorithms
* undersample the data using the ClusterCentroids algorithm
* combinatorial approach of over- and undersampling using the SMOTEENN algorithm
* comparison of the two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk 

## Results

### RandomOverSampler Model

* balanced accuracy score is 65%
* high risk precision is about 1% with 62% sensitivity

Due to the high number of the low risk population, its' precision is almost 100% with a sensitivity of 68%.

![image](https://user-images.githubusercontent.com/96931376/173711039-a26cef03-85c1-4db2-834a-a849bbbc35e9.png)
![image](https://user-images.githubusercontent.com/96931376/173711052-67f738b7-46f0-4c7e-a69d-286856f09493.png)
![image](https://user-images.githubusercontent.com/96931376/173711061-b36a7c04-1af5-4e7a-9881-00a184008ecf.png)

### SMOTE Model

* balanced accuracy score is 64%
* high risk precision is about 1% with 63% sensitivity

Due to the high number of low risk population, its' precision is almost 100% with a sensitivity of 66%. 

![image](https://user-images.githubusercontent.com/96931376/173711293-1cfb31c1-5866-42b9-991b-dbebe35833b1.png)
![image](https://user-images.githubusercontent.com/96931376/173711308-94447473-1526-410f-a945-d6ae6073cdc7.png)
![image](https://user-images.githubusercontent.com/96931376/173711317-b07b00bb-eeb6-4d92-b918-f56a82daf5f7.png)

RandomOverSampler and SMOTE models exhibited significantly similar results. 

### ClusterCentroids Model

* balanced accuracy score is about 52%
* high risk precision is about 1% with 63% sensitivity 

Due to the high number of false positives, the low risk sensitivity is only 40%.

![image](https://user-images.githubusercontent.com/96931376/173711615-5d143512-66f1-4093-99aa-ba9c4906537a.png)
![image](https://user-images.githubusercontent.com/96931376/173711630-0c4c4e14-fffb-4a77-a7d3-03fd187c0078.png)
![image](https://user-images.githubusercontent.com/96931376/173711639-1aa901fb-6139-4317-80b8-87a1c38bc03d.png)

### SMOTEENN Model

* balanced accuracy score is about 62%
* high risk precision is about 1% with 68% sensivity 

Due to the high number of false positives, the low risk sensitivity is 57%. 

![image](https://user-images.githubusercontent.com/96931376/173711692-365af5d2-d1e2-4334-9e2c-634a47f42e91.png)
![image](https://user-images.githubusercontent.com/96931376/173711699-92a1e4c3-5e9b-4484-9365-f79a81d305b8.png)
![image](https://user-images.githubusercontent.com/96931376/173711713-5616e0ae-3181-4f3e-afc5-905bee3bfb8e.png)

### BalancedRandomForestClassifier Model

* balanced accuracy score is about 79%
* high risk precision is about 4% with 67% sensitivity

Due to a lower number of false positives, the low risk sensitivity is 91% with 100% precision. 

![image](https://user-images.githubusercontent.com/96931376/173711890-b24ef0cf-ea17-457b-a015-366dc9dc9fbd.png)
![image](https://user-images.githubusercontent.com/96931376/173711900-b17d4808-8b61-4f45-bb82-86368c0a0cff.png)
![image](https://user-images.githubusercontent.com/96931376/173711911-21edfb23-e879-4cb2-b5a8-74be52fc7773.png)

### EasyEnsembleClassifier Model

* balanced accuracy score is about 93%
* high risk precision is about 7% with 91% sensitivity

Due to a lower number of false positives, the low risk sensitivity is 94% with 100% precision. 

![image](https://user-images.githubusercontent.com/96931376/173712066-3f0970f8-ba6d-46de-b3b6-72d6d732f7c8.png)
![image](https://user-images.githubusercontent.com/96931376/173712081-956b3355-8aa2-47de-ac78-161681357543.png)
![image](https://user-images.githubusercontent.com/96931376/173712091-9f39f8dc-4b21-47a2-99b6-59ece464a4f1.png)

## Summary

All the models used to perform the credit risk analysis exhibitied weak precision in determining if a credit risk is too high. The Ensemble models resulted in significant improvement on the sensitivity of the high risk credits. The EasyEnsembleClassifier model resulted in a recall of 92%, which indicates it detected almost all of the high risk credit. In contrast, the majority of the low risk credits are falsely reported as high risk. This would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities. With the current results, it is not recommended that the bank utilize these models to predict credit risk.
