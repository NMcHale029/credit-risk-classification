# credit-risk-classification
Imports include:
- numpy
- pandas
- Path
- balanced_accuracy_score
- confusion_matrix
- classification_report
- train_test_split
- LogisticRegression
- accuracy_score
- RandomOverSampler

## Overview
Provided loan data categoized each loan as either 'healthy loan' or 'high-risk loan'. The data was used to build a predictive model about if loans were healthy or high-risk.

Data was split into training data and test data using the train_test_split module. Then the LogisticRegression module was used to create and fit the model using the training data. Using this classifier, a prediction set was created with the test data. The prediction set was then compared to the output test data by measuring the balanced_accuracy_score, a confusion_matrix, and classification_report.

A similar process was used after creating a RandomOverSampler set. There were about 30 times more healthy loans than high-risk loans. The RandomOverSampler creates a dataset that has the same number of healthy and hihg-risk loans to evenly weight the outputs we're measuring for.

## Findings
The RandomOverSampler model was found to be a better model by recalling a greater percentage (99%) of high-risk loans, while having an acceptable (84%) precision. This model presents less risk than the first model tested.