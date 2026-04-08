# Fraud Detection Using Machine Learning

## Overview
This project focuses on detecting fraudulent financial transactions using machine learning models. The goal is to identify patterns in trandsaction data that can help distinguish 
between legtimate and fraudulent activity.

## Dataset
The dataset contains approximately 5 million financial transactions with features such as transaction type, merchant category, location, device used, and behavioral scoring metrics.

Due to the large size of the dataset, a sample of 100,000 records was used for model building and evaluation.

## Methods 
Several preprocessing steps were applied before modeling:
  - Removed high-cardinality identifier columns (transaction ID, account numbers, IP address) to avoid memory issues and ineffective encoding
  - Handled missing values
  - Numerical columns were filled using the median
  - Categorical columns were filled with "Unknown"
  - Converted categorical variables into numerical format using one-hot encoding
  - Split the dataset into training and testing sets using an 80/20 split with stratification

## Models Used
### Logistic Regression (with class balancing)
  - Used as the baseline classification model
  - Applied class weighting to address class imbalance
  - Successfully detected fraudulent transactions, but produced a high number of false positives

### Random Forest Classifier
  - Used a comparison model
  - Acheived high overall accuracy, but failed to detect fraudulent transactions
  - Demonstrated that accuracy alone is not reliable for imbalanced datasets

## Model Evaluation 
Models were evaluated using:
  - Precision
  - Recall
  - F1-score
  - Accuracy
Recall was particularly important for this project because identifying fraudulent transactions is critical.

## Threshold Tuning
Threshold tuning was applied to the Logistic Regression model to explore the tradeoff between fraud detection and false positives.
  - Lowering the threshold increased fraud detection (recall)
  - However, it also signigicantly increased false positives, reducing precision
  - At lower thresholds, the model classified nearly all transactions as fraud

This demonstates the challenge of balancing sensitivity and accuracy in fraud detection systems.

## Key Findings
- Logistic Regression was more effective than Random Forest for detecting fraud in this dataset
- Random Forest achieved high accuracy but failed to detect fraudulent transactions
- Threshold tuning improved fraud detection but increased false positives

## Tools Used
- Python
- Pandas
- Scikit-learn

## Author
Deborah (Deb) St. Cyr
