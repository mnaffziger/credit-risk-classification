# credit-risk-classification
Module 20 Challenge: Supervised Learning
---


## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

The purpose of thsi analysis was to utilize supervised learning methods to categorize if a loan was 'Healthy' or 'High-Risk'.  Parameters utilized in training the model were
* loan_size	interest_rate	
* borrower_income	
* debt_to_income	
* num_of_accounts	
* derogatory_marks	
* total_debt

Using the provided data above, a Logistical Regression was utilized to determine if a loan was 'Healthy' or 'High-Risk'.  The original dataset consisted of 77535 financial records: 77% of the data was randomized and used to train/fit the model.  The remaining 23% of the original dataset was used to test the model. From the initial model performance analysis, it was determined that the original dataset was overrepresented by the number of 'Healthy' loans.  A oversampleing method was then utilized to retrain the model to better model instances of 'High-Risk Loans'.  After over-sampling, the models provided improved predictions for 'High-Risk Loans' precision and recall.


## Results

Description of the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1 (original dataset trained model):
   * Balanced Accuracy Score: 0.944
   * Classification Report:
     * Health Loan:
         * Precision: 1.00
         * Recall: 1.00
         * f1-score: 1.00
         * Support: 18759 records
     * High Risk Loan:
         * Precision" 0.87
         * Recall" 0.89
         * f1-score: 0.88
         * Support: 625 records



* Machine Learning Model 2:
   * Balanced Accuracy Score: 0.996
     * Classification Report:
       * Health Loan:
           * Precision: 1.00
           * Recall: 1.00
           * f1-score: 1.00
           * Support: 18759 records
       * High Risk Loan:
           * Precision" 0.87
           * Recall" 1.00
           * f1-score: 0.93
           * Support: 625 records

## Summary

At first glance, I am skeptical of the results.  Credit ratings, and loan approval requirements require a lot of information that is based on parameters that are not discrete.  That is, an applicant can have a vast amount of savings, but horrible debt/income ratio. Do these factors result into a 'Healthy Loan' ?  From the previous value_counts of the original, test, and train outcome values, there was an imbalance of 'Healthy Loan' (value '0') records in the dataset.  Since there are 30 times more datapoints with this value, I am not surprised that the precision, recall, and f1-score are 1.00.  The lower scores (0.87 - 0.89) for the 'High-Risk Loan' (value 1) are justified due to the underrepresentation, 3%, of these outcomes from the original dataset

Since the classificaiton report contains many values that are 0.87 and greater, suggests to me that the model was trained on a dataset that may not be representative of the population it is trying to predict.  From the confusion matrix, the data does not seam balanced between true negative and true positive results.  It might be possible that the dataset is inadvertently being skewed/overrepresented towards one particular outcome.

When the model was fitted with oversampled data, there was an improvement in the 'High-Risk Loan' true positive predictions.  These results also signaled a lower instance of false negative and false positive outcomes.

Based on these performance analysises, the oversampled data performed better at predicting which loans were healthy or high-risk.  This was due to an equal number of records that aligned with a healthy loan as those classified as a high-risk loan.

To accuratly predict which is a healthy/high-risk loan it is important to consider who is asking the question.  If the question is being asked from a bank's point of view, then the ability for an applicant to repay the loan, i.e. Healthy, (especially if the loan is called early) is more important than predicting a high-risk loan.  However, it the question is being asked from a societal/poverty prediction then it is more important to classify the 'High Risk' loans to perhaps correlate to socio-economic issues within a community or region.

In either case, it is important to train/test the model on a dataset that is representative and balanced towards the question at hand.  If the majority of the data lies within a single cluster, then utilizing a machine learning model to analyze any predictive model becomes moot. 

