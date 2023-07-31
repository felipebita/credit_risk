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

For this project, five ML models for classification: Logistic Regression (LR), Random Forest (RF), Light Gradient Boosting Machine (LGBM) and XGBoost (XGB); were evaluted considering four metrics: Balanced Accuracy, Precision, Recall, F1, Kappa and AUC; in a 5-fold cross validation strategy. Scalled and not scalled data were tested and calibration was done for the best model.
  
**2.3 - Company Business Strategy**

After selecting the best model, a business strategy was developed considering different acceptance rates of credit, where portfolio value was estimated and expected loss minimized.
  
**2.4 - Model Deploy**

The best model was saved and deployed. A small dataset was used to test the API and the model.
  
**2.5 - Report Writing**

A report with all relevant information obtained during the project was written. And the notebook with all the code and complamentary analysis was made [available](https://github.com/felipebita/credit_risk/blob/main/notebook/credit_risk_modeling.ipynb).
  
## **3 - Data Analysis Report**
The dataset used in this project was composed of 32580 lending records, with seven features about the borrower. After removing records with NAs and outlier values, 28632 records were left. As summarized in Table 1, the mean age of the borrowers was 28 years, and the mean loan was 9650$ with a mean interest rate of 11%. In this dataset, 21.7% of the borrowers defaulted their loans. 

**Table 1.** Descriptive statistics of the continuous variables.
| |person_age	| person_income	| person_emp_length	| loan_amnt	| loan_int_rate	| loan_percent_income	| cb_person_cred_hist_length |
|:---------:|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|:--------------:|:--------------:|
|mean |	27.7 |	66426.5 |	4.8 |	9655.3 |	11 |	0.17 |	5.8 |
|std |	6.18 |	51547.5 |	4 |	6327.8 |	3.2 |	0.11	| 4 |
|min |	20 |	4000 |	0 |	500 |	5.4 |	0	 | 2 | 
|max |	84 |	2039784 |	41 |	35000	| 23.2	| 0.83	| 30 |

![image](https://github.com/felipebita/credit_risk/assets/44379044/f7357621-eea1-40ac-b102-1499c513e758)

**Figure 1. Distribution plots of the continuous variables.**

![image](https://github.com/felipebita/credit_risk/assets/44379044/21515b7b-dc9d-4c58-8547-0ac064c7a629)

**Figure 2. Correlation matrix of the continuous variables.**

![image](https://github.com/felipebita/credit_risk/assets/44379044/c4ae3fb2-7862-4331-8332-4024e4a09fa3)

![image](https://github.com/felipebita/credit_risk/assets/44379044/c5763134-4f80-4f77-97e1-169815258ecf)

![image](https://github.com/felipebita/credit_risk/assets/44379044/792705c5-8cd9-4c80-8891-518c12830bd3)

![image](https://github.com/felipebita/credit_risk/assets/44379044/f5befc6c-3576-4599-b01d-baa5d69b987c)


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

![image](https://github.com/felipebita/credit_risk/assets/44379044/06aa523a-a760-4f75-bef3-cee0334c7968)

**Table 3.** Results regarding the evaluation metrics for the calibrated XGB models.
| Model | Balanced Accuracy	| Precision	| Recall	| F1	| Kappa | AUC |
|:---------:	| :---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
| XGB	|0.866407	|0.958290	|0.741727	|0.836215	|0.798099	|0.952598|
|XGB + sigmoid	|0.870581	|0.981441	|0.751412	|0.840253	|0.802595	|0.955023|
|XGB + isotonic	|0.860899	|0.981441	|0.725585	|0.834339	|0.797004	|0.955003|

## **5 - Company Credit Strategy**
|Acceptance Rate	| Threshold	|Bad Rate	|Loans Accepted	|Average Loan Amount	|Portifolio Value |
|:---------: |:---------:	|:---------:	|:---------:	|:---------:	|:---------: |
|	1.00	|1.00 |	0.21634	| 5727 |	9704 |	31528296|
|	0.95	|0.99736 |	0.17500 |	5440	| 9704	| 34313344|
|	0.90	|0.99012 |  0.12922	| 5154	| 9704	| 37088688|
|	0.85	|0.86606 |	0.07868	| 4868	| 9704	| 39805808|
|	0.80	|0.30247 |	0.05479	| 4581	| 9704	| 39582616|
|	0.75	|0.18514 |	0.04284	| 4295	| 9704	| 38107608|
|	0.70	|0.13062 |	0.03642	| 4009	| 9704	| 36069768|
|	0.65	|0.09661 |	0.02875	| 3722	| 9704	| 34041632|

## **6 - Conclusions and Prospects**
