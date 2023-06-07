# **Credit Risk Analysis**
Under construction. Not finished.
## **1 - Introduction**
This is a data science portfolio project focused on credit risk analysis. The objective is to emphasize the critical importance of credit risk analysis in the financial industry and showcase my skills in data analysis and machine learning by developing a model that predicts credit risk for financial institutions.

Credit risk analysis is of paramount importance for financial institutions as it allows them to assess the probability of borrowers defaulting on their loan obligations. By accurately predicting credit risk, these institutions can make informed decisions regarding lending, determine appropriate interest rates, and maintain a balanced loan portfolio. Effective credit risk analysis not only minimizes financial losses but also contributes to the stability of the financial system as a whole.

## **2 - Solution Strategy**
A data science project was developed to build, evaluate and launch a machine learning model capable of predicting loans default probabilities. The project consists of the following steps:

**2.1 - Data Analysis and Preparation**

In this step the data was analyzed in terms of structure, features information, datatypes, missing data and statistics summary. Furthermore, features were selected and the data prepared to be used in the modeling.

**2.2 - Machine Learning Modeling**

For this project, seven ML models for classification: Logistic Regression (LR), Random Forest (RF), Light Gradient Boosting Machine (LGBM), XGBoost (XGB) Multilayer perceptron (MLP); were evaluted considering four metrics: Balanced Accuracy, Precision, Recall, F1, Kappa and AUC; in a 5-fold cross validation strategy. Scalled and not scalled data were tested and hyperparameter tunning was done for the best model.
  
**2.3 - Company Expansion Strategy**

With the best model selected, a one time modeling was done and the results used to calculate the prospects of the company strategy using the model. Then, the questions of "The Challenge" were answered.
  
**2.4 - Model Deploy**

The one time model was saved and deployed. A small dataset was used to test the API and the model.
  
**2.5 - Report Writing**

A report with all relevant information obtained during the project was written. And the notebook with all the code was made [available](https://github.com/felipebita/fraud_detection/blob/main/notebook/fraud_project.ipynb).
  
## **3 - Data Analysis Report**

**Table 1.** Descriptive statistics of the continuous variables.
| |person_age	| person_income	| person_emp_length	| loan_amnt	| loan_int_rate	| loan_percent_income	| cb_person_cred_hist_length |
|:---------:|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|:--------------:|:--------------:|
|mean |	27.7 |	66426.5 |	4.8 |	9655.3 |	11 |	0.17 |	5.8 |
|std |	6.18 |	51547.5 |	4 |	6327.8 |	3.2 |	0.11	| 4 |
|min |	20 |	4000 |	0 |	500 |	5.4 |	0	 | 2 | 
|max |	84 |	2039784 |	41 |	35000	| 23.2	| 0.83	| 30 |

## **4 - Machine Learning Modeling Results**

**Table 2.** Results regarding the evaluation metrics for all the classification models.

| Model | Balanced Accuracy	| Precision	| Recall	| F1	| Kappa	| AUC |
|:---------:|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|:--------------:|
|LR |	0.576 +/- 0.002 |	0.743 +/- 0.014 |	0.168 +/- 0.005 |	0.274 +/- 0.006	| 0.211 +/- 0.005 |	0.758 +/- 0.004 |
|MLP | 0.63 +/- 0.08 | 0.724 +/- 0.188	| 0.328 +/- 0.229	| 0.365 +/- 0.174	| 0.282 +/- 0.13	| 0.774 +/- 0.019 |
|LR scaled	| 0.726 +/- 0.006	| 0.74 +/- 0.023	| 0.5 +/- 0.008	| 0.597 +/- 0.013	| 0.511 +/- 0.016	| 0.865 +/- 0.006 |
|MLP scaled	| 0.841 +/- 0.004	| 0.93 +/- 0.012	| 0.697 +/- 0.009	| 0.797 +/- 0.007	| 0.751 +/- 0.009	| 0.919 +/- 0.004 |
|RF	| 0.856 +/- 0.004	| 0.973 +/- 0.006	| 0.718 +/- 0.008	| 0.826 +/- 0.005	| 0.787 +/- 0.006	| 0.932 +/- 0.002 |
|RF scaled |	0.856 +/- 0.004 |	0.972 +/- 0.006	| 0.719 +/- 0.008	| 0.826 +/- 0.005	| 0.787 +/- 0.006	| 0.933 +/- 0.001 |
|LGBM	| 0.86 +/- 0.009	| 0.977 +/- 0.006	| 0.725 +/- 0.018	| 0.832 +/- 0.012	| 0.794 +/- 0.014	| 0.947 +/- 0.003 |
|LGBM scaled	| 0.86 +/- 0.009	| 0.978 +/- 0.006	| 0.724 +/- 0.018	| 0.832 +/- 0.012 | 0.794 +/- 0.014	| 0.947 +/- 0.003 |
|XGB scaled |	0.865 +/- 0.004	| 0.956 +/- 0.008	| 0.738 +/- 0.01	| 0.833 +/- 0.005	| 0.794 +/- 0.006	| 0.951 +/- 0.003 |
|**XGB** |**0.865 +/- 0.004** | **0.956 +/- 0.008**	| **0.738 +/- 0.01**	| **0.833 +/- 0.005**	| **0.794 +/- 0.006**	| **0.951 +/- 0.003** |

## **5 - Company Credit Strategy**

## **6 - Report Results**

## **7 - Conclusions and Prospects**
