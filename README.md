# Bank Marketing Analysis

## Project Overview

The Bank-Marketing Dataset contains data related to a direct marketing campaign by a Portuguese banking institution. The campaign involved phone calls to potential clients to persuade them to subscribe to a term deposit. The dataset includes demographic information, contact details, and campaign-related attributes.

## Dataset Source
UCI Machine Learning Repository

[Bank-Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)

## Data Description

The dataset consists of 41188 records with 20 input attributes and 1 target variable.

## Features

Client Attributes:

age (numeric)

job (categorical) – Type of job

marital (categorical) – Marital status

education (categorical) – Education level

default (categorical) – Credit default status

housing (categorical) – Housing loan status

loan (categorical) – Personal loan status

Contact & Campaign-Related Attributes:

contact (categorical) – Contact communication type (e.g., cellular, telephone)

month (categorical) – Last contact month of the year

day_of_week (categorical) – Last contact day of the week

duration (numeric) – Last contact duration (in seconds)

Previous Campaign Interaction:

campaign (numeric) – Number of contacts during this campaign

pdays (numeric) – Number of days since last contact (-1 means no previous contact)

previous (numeric) – Number of contacts performed before this campaign

poutcome (categorical) – Outcome of the previous campaign

Social & Economic Context:

emp.var.rate (numeric) – Employment variation rate

cons.price.idx (numeric) – Consumer price index

cons.conf.idx (numeric) – Consumer confidence index

euribor3m (numeric) – Euribor 3-month rate

nr.employed (numeric) – Number of employees

## Target Variable

y (binary) – Whether the client subscribed to a term deposit (yes or no)

## Project Workflow

### Data Preprocessing:
Removing duplicated values
Encoding categorical variables using One-Hot Encoding and Label Encoding
Handling class imbalance

### Exploratory Data Analysis (EDA):

#### Distribution of key variables

Relationships between features and the target variable
![image](https://github.com/user-attachments/assets/9f8689d8-f730-4d31-a8f3-2f9cb2da3515)

![image](https://github.com/user-attachments/assets/7777a134-c865-49ef-83ad-37473d03b71b)

## Model Training & Evaluation:

Decision Tree classifier was used
Performance was evaluated using Accuracy, Precision, Recall, F1-Score, and AUC-ROC 
![image](https://github.com/user-attachments/assets/2df155ca-a202-43d1-8114-feda90fb6214)

and confusion matrix
![image](https://github.com/user-attachments/assets/34db96ac-6813-42db-ba85-4fae87473122)

### Results for final model
(a) Precision
Class 0 (No): 0.94 
Out of all predictions labeled as "No", 94% were actually "No."
Class 1 (Yes): 0.64 
Out of all predictions labeled as "Yes", only 64% were actually "Yes."

Thereby, the model is better at avoiding false positives for No but struggles with those for Yes.

(b) Recall
Class 0 (No): 0.96 
Out of all actual "No" cases, 96% were correctly classified.
Class 1 (Yes): 0.54
Out of all actual "Yes" cases, only 54% were correctly classified.

The low recall for Class 1 suggests that the model is missing many "Yes" cases (high false negatives).

(c) F1-Score
The F1-score is the harmonic mean of precision and recall.
Class 0 (No): 0.95 (Very strong performance)
Class 1 (Yes): 0.58 (Weak performance)

Since Class 1 has low recall, the F1-score is also lower.

(d) Macro & Weighted Averages
Macro Avg: Averages precision, recall, and F1-score across both classes equally (0.79, 0.75, 0.77) respecively.

Weighted Avg: Takes into account the number of instances per class, meaning Class 0 (which has more data points) influences the overall metrics more.


**In conclusion:**
The model performs very well for predicting "No" (clients not subscribing) and the overall accuracy is high. However, the model struggles with predicting "Yes" (clients subscribing).

Low recall for Class 1 means many actual "Yes" cases are misclassified as "No."

Class 1 has significantly fewer samples hence the model is significantly biased towards Class 0.

Recommendations for Improvement:
Decision Trees can be prone to overfitting. Thereby, it is important to try other models such as Random Forest, XGBoost, or Logistic Regression for better performance.



