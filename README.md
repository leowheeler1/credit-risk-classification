# Supervised Learning Report

## Overview of the Analysis

- This analysis was conducted to judge if credit loans were healthy or high risk
- The data contained the following columns:
  - loan_size = size of loand
  - interest_rate = interest rate on the loan
  - borrower_income = annual income of loan holder
  - debt_to_income = loan_size/borrower_income
  - num_of_accounts = how many accounts the loan holder has
  - derogatory_marks = risk factor, how many times have they missed a payment
  - total_debt = total debt accrued
  - loan_status = healthy or credit risk
- After separating the data so that `y` contained the loan_status, and `X` contained everthing else, it was time to build the model
- A Logistic Regression linear model was used to train and predict this data
- The model was fitted and tested on the data, and then scored afterwards

## Results

### Note

#### `0` = Healthy Loan, `1` = High-Risk Loan

- Logistic Regression
  - Confusion Matrix:
    - [[`18686`,    `99`],
      [   `32`,   `567`]]
    - [[`TP`,       `FP`],
      [  `FN`,      `TN`]]
  - Accuracy - `99%`
    - (True Positives) / (Total Predictions)
    - How many labels did we get correct?
  - Precision - {
    `0` : `100%`
    `1` : `85%`
  }
    - True Positive / (True Positive + False Positive)
    - How many that we identified as positives were actually positives?
  - Recall - {
    `0` : `99%`
    `1` : `95%`
  }
    - True Positive / (True Positive + False Negative)
    - How many points from this group were correctly identified?

## Summary

- With a high accruacy score (`99%`) and high recall scores (`>= 90%`), this model was pretty successful, but there is room for improvement
- The precision score for high-risk loans (`85%`) was the lowest statistic measured. This means about `15%` of the time, the model incorrectly identifies a healthy loan as a high-risk loan.
- In this circumstance, I would say that this model is worth using. It is better to have some loans be flagged as high-risk when they're healthy than it is for high-risk loans to be marked as healthy.
