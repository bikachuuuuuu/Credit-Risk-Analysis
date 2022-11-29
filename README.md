# Credit-Risk-Analysis

## Overview

The objective of this project was to use machine learning models to analyze credit risk to provide a quicker and more reliable loan experience. Using these models, I was able to accurately identify good candidates for loans which could help a financial institution decrease their default rate on their loans. I was able to build and evaluate several machine learning algorithms to predict credit risk.

## Results

To conduct this analysis, we utilized six machine learning models:

- Random Oversampling
- SMOTE Oversampling
- Cluster Centroids Undersampling
- SMOTEENN Combination Sampling
- Balanced Random Forest Classifier
- Easy Ensemble AdaBoost Classifier

To determine how efficient these models were, we pulled the balanced accuracy score, as well as the precision and recall.

The balanced accuracy score tells us how good the classifier is for the dataset. The closer the number is to 1 the better.
Precision is a measure of how reliable a positive classification is.
Recall, or sensitivity, is the ability of the classifier to find all of the positive samples.
In assessing the results, our majority class is the low_risk, whereas our minority class is the high_risk.

### Random Oversampling
We used the RandomOverSampler from the imblearn library on the dataset. In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

1_balanced_accuracy

The balanced accuracy score is 0.65.
1_classification_report

Precision for the minority class is very low (0.01), and very high for the majority class (1.00).
Recall for the minority class is high (0.71), and a little lower for the majority class (0.58).
SMOTE Oversampling
We used SMOTE (Synthetic Minority Oversampling Technique) for our second algorithm. In using SMOTE, the size of the minority class is increased. However, the new instances are interpolated. For an instance from the minority class, a number of its closest neighbors is chosen. Based on the values of these neighbors, the new values are created. The results were as follows:

2_balanced_accuracy

The balanced accuracy score is 0.66.
2_classification_report

Precision for the minority class is very low (0.01), and very high for the majority class (1.00).
Recall for the minority class is high (0.63), and a little higher for the majority class (0.68).
Cluster Centroids Undersampling
We then turned to an undersampling model, Cluster Centroids, and assessed how well the model worked with this dataset. This algorithm identifies clusters of the majority class, then generates synthetic data points (centroids) that are representative of the clusters. Then the majority class is undersampled down to the size of the minority class.

3_balanced_accuracy

The balanced accuracy score is 0.54.
3_classification_report

Precision for the minority class is very low (0.01), and very high for the majority class (1.00).
Recall for the minority class is high (0.69), and lower for the majority class (0.40).
SMOTEENN Combination Sampling
We also used the SMOTEENN model (Synthetic Minority Oversampling Technique and Edited Nearest Neighbors) and assessed its proficiency with the dataset. SMOTEENN oversamples the minority class using SMOTE, then cleans the resulting data with an undersampling strategy. If the two nearest neighbors of a data point belong to two different classes, then that data point is dropped.

4_balanced_accuracy

The balanced accuracy score is 0.67.
4_classification_report

Precision for the minority class is very low (0.01), and very high for the majority class (1.00).
Recall for the minority class is high (0.73), and lower for the majority class (0.60).
Balanced Random Forest Classifier
The Balanced Random Forest Classifier randomly under-samples each bootstrap sample to balance it. Just as with the previous models, we assessed how well this model works with the dataset.

5_balanced_accuracy

The balanced accuracy score is 0.79.
5_classification_report

Precision for the minority class is very low (0.03), and very high for the majority class (1.00).
Recall for the minority class is high (0.70), and a little higher for the majority class (0.87).
Easy Ensemble AdaBoost Classifier
The last model we utilized was the Easy Ensemble AdaBoost Classifier. The classifier is an ensemble of AdaBoost learners that trained on different balanced bootstrap samples. The balancing is achieved by random under-sampling.

6_balanced_accuracy

The balanced accuracy score is 0.93.
6_classification_report

Precision for the minority class is low (0.09), and very high for the majority class (1.00).
Recall for the minority class is high (0.92), and also high for the majority class (0.94).

## Summary

In conclusion, credit-risk is a difficult thing to predict, even for advanced machine learning algorithms with 93 columns of data to process. While the Easy Ensemble AdaBoost Classifier model had the highest overall accuracy, this was largely due to the fact that the dataset was so radically unbalanced. Even when it's balanced accuracy and average F-score were above 90%, it's F-score for high-risk prediction was no better than 0.16. In the end, I would advise against using any of these algorithms, as it would put creditors as too great of risk being unable to accurately predict who the high-risk clients/debtors would be.
