# Credit Risk Report

## Overview of the Analysis
This analysis took loan data where data on each loan was provided, and categoized each loan as either 'healthy loan' or 'high-risk loan'. This data was used to build a predictive model about if loans were healthy or high-risk.

Data that was considered for each loan:
- Size of loan (loan_size)
- Interest rate of loan (interest_rate)
- Income of the borrower (borrower_income)
- Debt to income ration of borrower (debt_to_income)
- Number of accounts borrower has open with the bank (num_of_accounts)
- Derogatory marks (derogatory_marks)
- Total debt (total_debt)
- 'Healthy' or 'High-risk' (loan_status)

Data was split into training data and test data using the train_test_split module. Then the LogisticRegression module was used to create and fit the model using the training data. Using this classifier, a prediction set was created with the test data. The prediction set was then compared to the output test data by measuring the balanced_accuracy_score, a confusion_matrix, and classification_report.

A similar process was used after creating a RandomOverSampler set. There were about 30 times more healthy loans than high-risk loans. The RandomOverSampler creates a dataset that has the same number of healthy and hihg-risk loans to evenly weight the outputs we're measuring for.

## Results
* Machine Learning Model 1:
                precision    recall  f1-score   support
  healthy loan       1.00      0.99      1.00     18765
high-risk loan       0.85      0.91      0.88       619
      accuracy                           0.99     19384



* Machine Learning Model 2 (RandomOverSampler):
                precision    recall  f1-score   support
  healthy loan       1.00      0.99      1.00     18765
high-risk loan       0.84      0.99      0.91       619
      accuracy                           0.99

## Summary
The first model is pretty good, but whether or not it should be used depends on the level of risk the client is willing to take on. A majority of loans are good loans. If the model just predicted all loans were good, it would have a ~96% accuracy, so the value in this model is predicting bad loans. The model predicted 91% of bad loans, and 85% of the loans that were predicted to be bad were bad.

The second model (RandomOverSampler) is a much better model. This model found 99% of the high-risk loans. The model performed slightly worse in false-negatives. In the context of loans, this is a much more risk-adverse model. Of the false negatives, a person can work to process appeals.