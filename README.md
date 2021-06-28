# Credit Risk Analysis

## Overview

Machine learning is going to be applied towards a real-world challenge: credit card risk. Credit risk is an unbalanced classification problem, as good loans easily outnumber risky loans. Different techniques are eployed to train and evaluate models with unbalanced classes. Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, the data will be sampled by the following algorithms:

* Oversampling: RandomOverSampler and SMOTE algorithms
* Undersampling: ClusterCentroids algorithm
* Combinatorial Approach: SMOTEEN algorithm

Afterwards, two machine learning models, both which reduce bias, will be compared (BalancedRandomForestClassifier and EasyEnsembleClassifier) to predit credit risk.

## Results

#### RandomOverSampler Model

![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/oversampling/ros/balanced_accuracy_score.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/oversampling/ros/confusion_matrix.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/oversampling/ros/imbalanced_classification_report.PNG?raw=true)

* The balanced accuracy score is 64%
* The high risk precision is about 1% with a 62% sensitivity, which makes a F1 of 2%
* Due to the high number of the low risk population, its precision is almost 100% with a sensitivity of 67%

#### SMOTE Model

![alt_text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/oversampling/smote/balanced_accuracy_score.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/oversampling/smote/confusion_matrix.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/oversampling/smote/imbalanced_classification_report.PNG?raw=true)

* The balanced accuracy score is about 65%
* The high risk precision is about 1% with a 66% sensitivity, which makes a F1 of 2%
* Due to the high number of the low risk population, its precision is almost 100% with a sensitivity of 64%
* This model's results is similar to the ROS Model

#### ClusterCentroids Model

![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/undersampling/cc/balanced_accuracy_score.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/undersampling/cc/confusion_matrix.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/undersampling/cc/imbalanced_classification_report.PNG)

* The balanced accuracy score is about 51%
* The high risk precision is about 1% with a 59% sensitivity, which makes a F1 of 1%
* Due to the high number of false positives, the low risk sensitivity is only 40%.

#### SMOTEENN Model

![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/combination/smoteenn/balanced_accuracy_score.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/combination/smoteenn/confusion_matrix.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/combination/smoteenn/imbalanced_classification_report.PNG?raw=true)

* The balanced accuracy score is about 62%
* The high risk precision is about 1% with a 70% sensitivity, which makes a F1 of 2%
* Due to the high number of false positives, the low risk sensitivity is 55%.

#### BalancedRandomForestClassifier Model

![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/ensemble/brfc/balanced_accuracy_score.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/ensemble/brfc/confusion_matrix.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/ensemble/brfc/imbalanced_classification_report.PNG?raw=true)

* The balanced accuracy score improved to about 79%
* The high risk precision is still low at 4% with a 67% sensitivity, which makes a F1 of only 7%.
* Due to a lower number of false positives, the low risk sensitivity is now 91% with an almost 100% presicion.

#### EasyEnsembleClassifier Model

![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/ensemble/eec/balanced_accuracy_score.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/ensemble/eec/confusion_matrix.PNG?raw=true)
![alt text](https://github.com/viernesr/Credit_Risk_Analysis/blob/main/images/ensemble/eec/imbalanced_classification_report.PNG?raw=true)

* Note that the balanced accuracy score is improved to about 93%
* The high risk precision is still low at 7% with a 91% sensitivity, which makes a F1 of only 14%
* Due to a lower number of false positives, the low risk sensitivity is now 94% with an almost 100% presicion

## Summary

All models used to perform the credit risk analysis showed weak precision to determine if a credit risk is high. The ensemble models showed much better results, specifically on the sensitivity of the high risk credits. In particular, the Easy Ensemble Classifier Model showed a recall rate of 92%, thus identifying almost all high risk credit. This model would be the best suggested model for this analysis. However, since the precision rate is very low for all models, a lot of low risk credits are falsely detected as high risk, penalizing the bank's credit strategy. Since that is the case for all models used in this analysis, none of these models should be recommeneded to predit credit risk.
