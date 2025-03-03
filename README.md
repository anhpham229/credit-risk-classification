# credit-risk-analysis-report

## Overview of the Analysis

The goal of this analysis is to build a model that predicts the creditworthiness of borrowers for a peer-to-peer lending service. The company aims to minimize the risk of lending to unhealthy borrowers.

* Dataset Overview
  - Size: The dataset contains 77,531 entries, including features such as loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, total debt, and loan status.
  - Loan Status: The target column, loan_status, has two values:
        0: healthy loan
        1: high-risk loan (default)

* Methodology
  - Model: Logistic Regression was used to predict the loan status.
  - Process:
     + Read the lending_data.csv file into a Pandas DataFrame.
     + Split the data into features (X) and labels (y), with loan_status as the label.
     + Split the data into training and testing sets using train_test_split.
     + Train a logistic regression model using the training set.
     + Evaluate the model's performance using the test set.
     + Generate a confusion matrix and classification report to assess the model's accuracy.

## Results

* Precision
  - Healthy Loan (0): 1.00
    The model correctly classifies all healthy loans as healthy with no false positives.
  - High-Risk Loan (1): 0.84
    The model predicts high-risk loans with 84% precision. However, 16% of the time, it mistakenly classifies healthy loans as high-risk (false positives).

* Recall
  - Healthy Loan (0): 0.99
    The model correctly identifies 99% of healthy loans.
  - High-Risk Loan (1): 0.94
    The model correctly identifies 94% of high-risk loans, missing 6% (false negatives).

* F1 score
  - Healthy Loan (0): 1.00
    The model has perfect precision and recall for healthy loans, yielding an F1-score of 1.00.
  - High-Risk Loan (1): 0.89
    The F1-score for high-risk loans reflects a good balance between precision and recall, though it is slightly lower than the F1-score for healthy loans due to the lower precision.

* Accuracy
  - Overall Accuracy: 0.99
    The model achieves a 99% accuracy rate, indicating excellent overall performance in predicting loan status.

* Average
  - Macro Average
      + Macro Average (Precision): 0.92
        This is the average precision across both classes, ignoring class imbalance. It shows the model's overall performance when both classes are treated equally.
      + Macro Average (Recall): 0.97
        The average recall across both classes, showing that the model is generally good at identifying both healthy and high-risk loans.
      + Macro Average (F1-Score): 0.94
        The average F1-score across both classes, providing an overall measure of the model's performance in balancing precision and recall.

  - Weighted Average:
      + Weighted Average (Precision): 0.99
        This is the average precision weighted by the support (the number of instances) in each class. Since there are more healthy loans than high-risk loans, the precision is weighted towards healthy loans.
      + Weighted Average (Recall): 0.99
        This is the weighted recall, which is very high, meaning the model does an excellent job in predicting both classes, considering the class distribution.
      + Weighted Average (f1-score): 0.99
        The weighted f1-score is very high, reflecting the model's good balance between precision and recall for both classes.

## Summary

* For Healthy Loans (0): The model performs exceptionally well, with perfect precision (1.00) and high recall (0.99), meaning it correctly identifies nearly all healthy loans.

* For High-Risk Loans (1): The model performs well with a 94% recall, meaning it correctly identifies most high-risk loans. However, it has a lower precision of 0.84, meaning that it sometimes mistakenly classifies healthy loans as high-risk (false positives).

* Overall Performance: The model has an overall accuracy of 99%, which indicates that it is very good at predicting the loan status. The macro and weighted averages of precision, recall, and f1-score suggest a strong overall performance, with only slight room for improvement in terms of precision for high-risk loans.

## Conclusion

While the logistic regression model performs very well for both healthy loans and high-risk loans, there is room for improvement in the precision for high-risk loans. The model occasionally misclassifies healthy loans as high-risk loans (false positives). To address this, consider experimenting with the following:

- Adjust the Decision Threshold: Increase the threshold to make the model more conservative when predicting high-risk loans, which may reduce false positives.
- Use Resampling: Balance the dataset through oversampling the high-risk loans or undersampling the healthy loans.
- Feature Engineering: Investigate new features or transformations of existing ones to improve model accuracy.
- Consider Other Models: If precision for high-risk loans remains unsatisfactory, exploring other machine learning models like Random Forest or Gradient Boosting could yield better results.
