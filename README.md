# credit-risk-default-prediction
Credit risk modelling project predicting borrower default probability and Expected Credit Loss (ECL) using Python and machine learning.

# Credit Risk Analytics: Default Prediction & Expected Credit Loss (ECL)

# Overview
This project performs credit risk analysis on a credit card loan portfolio to identify high-risk borrowers and estimate potential financial losses.
The analysis simulates the work performed by credit risk analysts in financial institutions, including:

`Portfolio risk analysis.

`Identification of high-risk borrower behaviour.

`Prediction of Probability of Default (PD) using machine learning.

`Estimation of Expected Credit Loss (ECL) using the standard risk framework.

The project combines data analysis, feature engineering, predictive modelling, and financial risk metrics to understand the drivers of credit default.

# Dataset
The dataset contains information on 30,000 credit card borrowers, including demographic details, repayment history, billing amounts, and payment behaviour over the previous six months.

# Key Variables

# Customer Information
`LIMIT_BAL – Credit limit assigned to the borrower 

`SEX – Gender of the borrower

`EDUCATION – Education level

`MARRIAGE – Marital status

`AGE – Age of borrower

# Repayment History
PAY_0 – PAY_6 – Monthly repayment status

# Billing Information
BILL_AMT1 – BILL_AMT6 – Monthly bill amounts

# Payment Behaviour
PAY_AMT1 – PAY_AMT6 – Amount paid each month

# Target Variable
default.payment.next.month – Whether the borrower defaulted next month

# Project Workflow / Data Flow

# The project follows a structured credit risk analytics pipeline:
Raw Dataset

    
    
Data Cleaning
(Remove duplicates, rename variables)

     
     
Exploratory Data Analysis
(Portfolio statistics and borrower behaviour)

     
     
Feature Engineering
(Create behavioural risk indicators)

     
     
Risk Segmentation Analysis
(Identify high-risk borrower groups)

     
     
Machine Learning Model
(Logistic Regression to predict PD)

     
     
Probability of Default (PD)
(Model predictions)

     
     
Expected Credit Loss Calculation
(ECL = PD × LGD × EAD)

     
     
Portfolio Risk Insights & Visualisations


# 1. Data Cleaning

Initial preprocessing included:
` Removing the ID column

` Renaming the target variable to default

` Checking and removing duplicate rows

` Verifying missing values

# Final dataset size
29,965 borrowers

24 variables

# 2. Feature Engineering

Several behavioural credit risk indicators were created to capture borrower risk patterns.
# Repayment Behaviour Features
  Average repayment delay
  
  Maximum repayment delay
  
These features measure borrower delinquency behaviour across multiple months.

# Credit Utilisation Features
  Latest utilisation ratio
  
  Average utilisation ratio
  
These features measure how much of the credit limit a borrower is using.

Higher utilisation is typically associated with higher default risk.

# Payment Behaviour Features
  Latest payment ratio
  
  Average payment ratio
  
These measure how much of the bill amount the borrower repays.

Lower payment ratios indicate financial stress or repayment difficulty.

# Risk Flags
Binary indicators were created to identify high-risk behaviour:

 ` High utilisation
  
 ` High repayment delay
  
 ` Recent missed payment
  
 ` Low payment ratio
  
These features help segment borrowers into risk categories.

# 3. Portfolio Risk Analysis

Portfolio-level metrics were calculated to understand overall credit exposure.

Portfolio Statistics

  Total borrowers: 29,965
  
  Total credit exposure: 5.0 billion
  
  Portfolio default rate: 22.1%
  
  Average credit limit: 167,442
  
  Average credit utilisation: 37%

# 4. Risk Segmentation Insights

Behavioural analysis shows strong relationships between borrower behaviour and default risk.
# Recent Missed Payment
  No missed payment → 13.8% default rate
  
  Missed payment → 50.3% default rate
  
This is the strongest predictor of default risk.
# High Repayment Delay
  Normal repayment → 18% default rate
  
  High delay → 64% default rate
  
Borrowers with consistent repayment delays are significantly more likely to default.
# High Credit Utilisation
  Normal utilisation → 20% default rate
  
  High utilisation → 34% default rate
  
Heavy use of available credit increases default probability.

# 5. Probability of Default (PD) Model

A Logistic Regression model was trained to estimate the probability that a borrower will default.
# Features Used
  Credit limit
  
  Age
  
  Repayment delay indicators
  
  Credit utilisation
  
  Payment ratios
  
  Behavioural risk flags
  
# Model Performance
  Accuracy: 80.8%
  
  Precision: 0.66
  
  Recall: 0.27
  
  F1 Score: 0.39
  
  ROC-AUC: 0.74

The model demonstrates good predictive power in identifying high-risk borrowers.

# 6. Expected Credit Loss (ECL) Modelling

The project also estimates financial losses using the standard credit risk framework used by banks.
ECL Formula

# ECL = PD × LGD × EAD

Where:

PD – Probability of Default (model output)

LGD – Loss Given Default

EAD – Exposure at Default (credit limit)

# Portfolio Results
Total Expected Credit Loss: 343 million

Average Expected Loss per Borrower: 11,455

Borrowers with both high credit limits and high default probability contribute the most to portfolio risk.

# Visualisations

The analysis includes several visualisations to support risk insights:

  #  Distribution of Expected Credit Loss
<img width="859" height="545" alt="download" src="https://github.com/user-attachments/assets/a506c097-1b09-4fa0-b770-aae2f103f139" />

  #  Distribution of Predicted Default Prob
<img width="859" height="545" alt="download" src="https://github.com/user-attachments/assets/2118cfbc-a899-4628-914d-59188a6449fe" />
ability

  #  Default rates by behavioural risk indicators
<img width="1204" height="590" alt="download" src="https://github.com/user-attachments/assets/3c274f9b-5b8c-4b0c-af8a-6bb8881fe0f4" />

#    Top borrowers contributing to portfolio loss
<img width="1032" height="572" alt="download" src="https://github.com/user-attachments/assets/f9f724d9-5cd0-473d-a8e6-42c9aa2fcb16" />

#    Risk heatmap (repayment delay vs utilisation)
<img width="776" height="545" alt="download" src="https://github.com/user-attachments/assets/c434c933-67c4-4808-a863-5f7791384ecc" />

These visualisations help identify high-risk segments in the portfolio.

# Tools & Technologies

  Python
  
  Pandas
  
  NumPy
  
  Scikit-learn
  
  Matplotlib
  
  Seaborn
  
  Jupyter Notebook

# Key Skills Demonstrated
  Credit Risk Analytics
  
  Probability of Default Modelling
  
  Expected Credit Loss Modelling
  
  Feature Engineering
  
  Portfolio Risk Analysis
  
  Data Visualisation
  
  Machine Learning in Finance
