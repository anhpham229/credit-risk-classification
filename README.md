# credit-risk-analysis-report

## Overview of the Analysis

In this analysis, we evaluated five different machine learning models for predicting loan status (healthy loan or high-risk loan) based on the dataset. Below is a summary of the results from each model, along with an analysis of which model performs best, and how the performance might depend on the problem at hand.

* Dataset Overview
  - Size: The dataset contains 77,531 entries, including features such as loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, total debt, and loan status.
  - Loan Status: The target column, loan_status, has two values:
        0: healthy loan
        1: high-risk loan (default)

* Methodology
  - Machine Learning Models: In this analysis, five different machine learning models were used to predict the loan status (whether a loan is healthy or high-risk). These models are:
      + Logistic Regression Model
      + Support Vector Machines (SVM) Model
      + Decision Tree Model
      + K-Nearest Neighbors (KNN) Model
      + Random Forest Model
  - Process:
     + Read the lending_data.csv file into a Pandas DataFrame.
     + Split the data into features (X) and labels (y), with loan_status as the label.
     + Split the data into training and testing sets using train_test_split.
     + Scale the test and training features
     + Train the model using the training set or scaled training set.
     + Evaluate the model's performance using the test set/scaled test set.
     + Generate a confusion matrix and classification report to assess the model's accuracy.

## Results

1. Logistic Regression Model
* Accuracy Score: 0.9925
* Confusion Matrix:
  - True Positives (Healthy Loan): 18655
  - False Positives (Healthy Loan classified as High-Risk): 110
  - False Negatives (High-Risk Loan classified as Healthy): 36
  - True Positives (High-Risk Loan): 583
* Precision for High-Risk Loan: 0.84
* Recall for High-Risk Loan: 0.94
* F1-Score for High-Risk Loan: 0.89
* Precision for Healthy Loan: 1.00
* Recall for Healthy Loan: 0.99
* F1-Score for Healthy Loan: 1.00

2. Support Vector Machines (SVM) Model
* Accuracy Score: 0.9935
* Confusion Matrix:
  - True Positives (Healthy Loan): 18654
  - False Positives (Healthy Loan classified as High-Risk): 111
  - False Negatives (High-Risk Loan classified as Healthy): 15
  - True Positives (High-Risk Loan): 604
* Precision for High-Risk Loan: 0.84
* Recall for High-Risk Loan: 0.98
* F1-Score for High-Risk Loan: 0.91
* Precision for Healthy Loan: 1.00
* Recall for Healthy Loan: 0.99
* F1-Score for Healthy Loan: 1.00

3. Decision Tree Model
* Accuracy Score: 0.9903
* Confusion Matrix:
  - True Positives (Healthy Loan): 18667
  - False Positives (Healthy Loan classified as High-Risk): 98
  - False Negatives (High-Risk Loan classified as Healthy): 91
  - True Positives (High-Risk Loan): 528
* Precision for High-Risk Loan: 0.84
* Recall for High-Risk Loan: 0.85
* F1-Score for High-Risk Loan: 0.85
* Precision for Healthy Loan: 1.00
* Recall for Healthy Loan: 0.99
* F1-Score for Healthy Loan: 0.99

4. K-Nearest Neighbors (KNN) Model
* Accuracy Score: 0.9922
* Confusion Matrix:
  - True Positives (Healthy Loan): 18657
  - False Positives (Healthy Loan classified as High-Risk): 108
  - False Negatives (High-Risk Loan classified as Healthy): 44
  - True Positives (High-Risk Loan): 575
* Precision for High-Risk Loan: 0.84
* Recall for High-Risk Loan: 0.93
* F1-Score for High-Risk Loan: 0.88
* Precision for Healthy Loan: 1.00
* Recall for Healthy Loan: 0.99
* F1-Score for Healthy Loan: 1.00

5. Random Forest Model
* Accuracy Score: 0.9917
* Confusion Matrix:
  - True Positives (Healthy Loan): 18657
  - False Positives (Healthy Loan classified as High-Risk): 108
  - False Negatives (High-Risk Loan classified as Healthy): 44
  - True Positives (High-Risk Loan): 575
* Precision for High-Risk Loan: 0.85
* Recall for High-Risk Loan: 0.90
* F1-Score for High-Risk Loan: 0.87
* Precision for Healthy Loan: 1.00
* Recall for Healthy Loan: 0.99
* F1-Score for Healthy Loan: 1.00

## Summary

* Best Performing Model:
  - SVM Model seems to perform the best overall, with the highest accuracy score (0.9935) and a good balance between precision and recall for both classes (healthy loan and high-risk loan).
  - The model has a recall of 0.98 for high-risk loans, which is the best among all models, meaning it correctly identifies most high-risk loans. Additionally, the F1-Score for high-risk loans is 0.91, which is the highest among the models.
  - Logistic Regression follows closely with an accuracy of 0.9925 but has slightly lower recall for high-risk loans (0.94) compared to SVM.

* Precision and Recall Trade-offs:
  - Healthy Loans (0) are always predicted with high precision (1.00) and recall (0.99) across all models, which means that the models are extremely effective at identifying healthy loans correctly.
  - High-Risk Loans (1) show some variation between models, with SVM and Random Forest performing better in correctly identifying high-risk loans (higher recall), but with slightly lower precision compared to the healthy loans.
  - For high-risk loan identification, it may be acceptable to have slightly lower precision (around 0.84) if the model improves recall, which helps in identifying more high-risk loans. SVM achieves a good balance in this case.

* Model Selection Based on Problem Needs:
  - If the primary goal is to minimize false positives (incorrectly classifying healthy loans as high-risk), Logistic Regression or Random Forest might be more suitable since they tend to have slightly fewer false positives than the other models.
  - If the focus is to minimize false negatives (missing high-risk loans), SVM might be the best choice, given its high recall for high-risk loans (0.98).

* Other Considerations:
  - SVM and Logistic Regression provide the best overall accuracy scores and balance between precision and recall for both classes.
  - Decision Tree and KNN are still effective, but they tend to have slightly lower recall for high-risk loans (especially the Decision Tree).

## Conclusion

* SVM is recommended as the best model for predicting loan risk in this case, especially if the goal is to improve recall for high-risk loans without sacrificing too much precision.
* Logistic Regression could also be used as a solid alternative, particularly if minimizing false positives is a higher priority.
* If computational complexity or interpretability is a concern, Logistic Regression might be more desirable because it is simpler to understand and implement, while still providing good performance.
