# Credit_Risk_Analysis



## 1. Analysis Overview

The purpose of this analysis was twofold: (1) To explore the effectiveness of a series of data re-sampling techniques to format a credit risk dataset in order to fit logistic regression models to classify loan risk. (2) To explore the application of ensemble learning techniques, namely balanced random forest and easy ensemble AdaBoost classifiers, as an alternative method to predict loan risk from the credit risk dataset. 



## 2. Results

Results of this analysis, including the balanced accuracy score and precision and recall scores for each machine learning model/technique, are given below:

* **Naive random over-sampling & logistic regression**

  ![Naive_oversampling_cm](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\Naive_oversampling_cm.PNG)

  ![Naive_oversampling_classification_report](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\Naive_oversampling_classification_report.PNG)

  Re-sampling the data using Naive random over-sampling and fitting a logistic regression model to predict loan risk (0: high risk, 1: low risk) resulted in the above classification scores. Utilizing this method, a balanced accuracy score of 0.64 was achieved, with a precision of 0.01 and recall of 0.62 for the high-risk class (encoded as 0), and a precision of 1.00 and recall of 0.67 for the low-risk class (encoded as 1). These results indicate that after over-sampling, the logistic regression model exhibits low precision in predicting high loan risk, generating a large number of false positive classifications (predicted 0, actual 1). However, the model was able to achieve a higher recall of 0.62, indicating the model is able to predict the (slight) majority of high risk loans. In this instance, it is likely better to optimize recall, as identifying high risk loans is of a higher priority than avoiding falsely classifying low-risk loans as high-risk loans.

  

* **SMOTE over-sampling & logistic regression**

  ![SMOTE_oversampling_cm](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\SMOTE_oversampling_cm.PNG)

  ![SMOTE_oversampling_classification_report](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\SMOTE_oversampling_classification_report.PNG)

  Re-sampling the data using SMOTE over-sampling and fitting a logistic regression model to predict loan risk (0: high risk, 1: low risk) resulted in the above classification scores. Utilizing this method, a balanced accuracy score of 0.65 was achieved, with a precision of 0.01 and recall of 0.66 for the high-risk class (encoded as 0), and a precision of 1.00 and recall of 0.64 for the low-risk class (encoded as 1). These results indicate that after SMOTE over-sampling, the logistic regression model exhibits comparable characteristics and predictive performance as the logistic regression model fit to the randomly oversampled dataset. However, the average performance has been reduced by a small amount relative to the randomly oversampled data set as indicated by the lowered average f1 score of 0.78, down from 0.80.

  

* **Under-sampling (cluster centroids) & logistic regression**

  ![Undersampling_cm](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\Undersampling_cm.PNG)

  ![Undersampling_classification_report](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\Undersampling_classification_report.PNG)

  After under-sampling the credit risk dataset and fitting a logistic regression model to predict loan risk (0: high risk, 1: low risk), the above classification scores were obtained. Utilizing this method, a balanced accuracy score of 0.52 was achieved, with a precision of 0.01 and recall of 0.60 for the high-risk class (encoded as 0), and a precision of 1.00 and recall of 0.43 for the low-risk class (encoded as 1). These results indicate that after SMOTE over-sampling, the logistic regression model exhibits comparable characteristics as when the data were re-sampled using the over-sampling techniques. However, the overall model performance has been considerably reduced, particularly with respect to the recall for low-risk loans. This is expected behavior, as the under-sampling technique greatly reduced the number of low-risk training data which are over-represented in the raw dataset. As a result, there are less low-risk loan data for the model to train on.

  

* **SMOTEENN re-sampling & logistic regression**

  ![SMOTEENN_cm](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\SMOTEENN_cm.PNG)

  ![SMOTEENN_classification_report](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\SMOTEENN_classification_report.PNG)

  After re-sampling the credit risk dataset utilizing the SMOTEENN technique and fitting a logistic regression model to predict loan risk (0: high risk, 1: low risk), the above classification scores were obtained. Utilizing this method, a balanced accuracy score of 0.64 was achieved, with a precision of 0.01 and recall of 0.69 for the high-risk class (encoded as 0), and a precision of 1.00 and recall of 0.58 for the low-risk class (encoded as 1). These results demonstrate that the SMOTEENN re-sampling process results in logistic regression model characteristics and performance comparable to the two oversampling techniques explored above. There are, however, some small differences in the recall performance, where the SMOTEENN re-sampling has resulted in a relatively higher recall for high-risk loans, and a lower recall for low-risk loans. Given the objective/priority of this analysis of identifying high-risk loans, this technique is preferable to the previously explored re-sampling techniques.

  

* **Balanced random forest classifier**

  ![BalancedRandomForest_cm](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\BalancedRandomForest_cm.PNG)

  ![BalancedRandomForest_classification_report](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\BalancedRandomForest_classification_report.PNG)

  Fitting a balanced random forest classifier model to predict loan risk (0: high risk, 1: low risk), the above classification scores were obtained. Utilizing this method, a balanced accuracy score of 0.79 was achieved, with a precision of 0.04 and recall of 0.67 for the high-risk class (encoded as 0), and a precision of 1.00 and recall of 0.91 for the low-risk class (encoded as 1). These results indicate that the balanced random forest classifier ensemble model dramatically outperforms the logistic regression model applied after data re-sampling. The balanced random forest classifier model maintains a comparable high-risk loan recall to the logistic regression models fit after data re-sampling, but exhibits much improved high-risk loan precision (though still low overall) and low-risk loan recall. Therefore, this technique would be preferable to the logistic regression models fit after performing data re-sampling.

  

* **Easy ensemble AdaBoost classifier**

  ![EasyEnsembleAdaBoost_cm](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\EasyEnsembleAdaBoost_cm.PNG)

  ![EasyEnsembleAdaBoost_classification_report](C:\Users\james\Desktop\Bootcamp\ML Pathway\Credit_Risk_Analysis\images\EasyEnsembleAdaBoost_classification_report.PNG)

  Fitting the final machine learning model explored in this analysis, an easy ensemble AdaBoost classifier, to predict loan risk (0: high risk, 1: low risk) yielded the above classification scores. Utilizing this method, a balanced accuracy score of 0.92 was achieved, with a precision of 0.07 and recall of 0.91 for the high-risk class (encoded as 0), and a precision of 1.00 and recall of 0.94 for the low-risk class (encoded as 1). These results indicate yet another marked improvement, outperforming the balanced random forest classifier ensemble model, particularly with respect to high-risk loan recall. The easy ensemble AdaBoost classifier returned by far the best overall performance of all machine learning algorithms explored, and would therefore be the recommended model for this application.

  

  ## 3. Summary

  In general, due to the imbalanced nature of the credit risk dataset, containing far more instances of low-risk loans than high risk loans, all machine learning models explored exhibited relatively low precision in predicting high-risk loans. However, the majority of the models were able to predict high-risk loans with recall scores exceeding 0.6. Given the nature of this problem, this model behavior is preferable to an improved high-risk loan precision at the expense of recall. This is because it is of more importance to identify high-risk loans, than to avoid falsely labeling low-risk loans as high-risk. Overall, the easy ensemble AdaBoost classifier model performed by far the best, and is the recommended model for use in this application.

