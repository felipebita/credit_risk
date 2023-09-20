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

For this project, five ML models for classification: Logistic Regression (LR), Random Forest (RF), Light Gradient Boosting Machine (LGBM) and XGBoost (XGB); were evaluted considering five metrics: Balanced Accuracy, Precision, Recall, F1, Kappa and AUC; in a 5-fold cross validation strategy. Scalled and not scalled data were tested and calibration was done for the best model.
  
**2.3 - Company Business Strategy**

After selecting the best model, a business strategy was developed considering different acceptance rates of credit, where portfolio value was estimated and expected loss minimized.
  
**2.4 - Model Deploy**

The best model was saved and deployed. A small dataset was used to test the API and the model.
  
**2.5 - Report Writing**

A report with all relevant information obtained during the project was written. And the notebook with all the code and complamentary analysis was made [available](https://github.com/felipebita/credit_risk/blob/main/notebook/credit_risk_modeling.ipynb).
  
## **3 - Data Analysis Report**
The dataset used in this project was composed of 32580 lending records, with seven features about the borrower. After removing records with NAs and not realistic values of person age and employment length, 28632 records were left consisting of 21.7% are loan defaults. As summarized in **Table 1**, the mean age of the borrowers was 28 years, and the mean loan was 9650$ with a mean interest rate of 11%, the variable person income was the only with extreme higher values in relation to rest of the data **(Figure 1)**. The correlation analysis showed that in general the variables do not have high correlations, except person age with person credit historic length (0.88) and loan amount and loan percent income (0.58). In relation to the variable of interest (loan status), the highest correlations were with loan percent income (0.38) and loan interest rate (0.34) **(Figure 2)**.

**Table 1.** Descriptive statistics of the continuous variables.
| |person_age	| person_income	| person_emp_length	| loan_amnt	| loan_int_rate	| loan_percent_income	| cb_person_cred_hist_length |
|:---------:|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|:--------------:|:--------------:|
|mean |	27.7 |	66426.5 |	4.8 |	9655.3 |	11 |	0.17 |	5.8 |
|std |	6.18 |	51547.5 |	4 |	6327.8 |	3.2 |	0.11	| 4 |
|min |	20 |	4000 |	0 |	500 |	5.4 |	0	 | 2 | 
|max |	84 |	2039784 |	41 |	35000	| 23.2	| 0.83	| 30 |

![image](https://github.com/felipebita/credit_risk/assets/44379044/f7357621-eea1-40ac-b102-1499c513e758)

**Figure 1.** Distribution plots of the continuous variables.

![image](https://github.com/felipebita/credit_risk/assets/44379044/21515b7b-dc9d-4c58-8547-0ac064c7a629)

**Figure 2.** Correlation matrix of the continuous variables.

Considering the discrete variables, it was observed that about 10% of the borrowers have ownership of their house, while around 50% pay rent and the rest have the house mortgaged. Considering the loan status, it was observed that almost 97% of the loans default are from borrowers who pay rent or have the house mortgaged, where 75% is from rent **(Figure 3)**. For the loan intent variable, the classes had similar percentage values, ranging from 11% for home improvemente to 20% for education. Furthermore, when comparing not default and default, it was seen a significant increase in the classes debt consolidation (14% to 21%) and medical (17% to 23%) **(Figure 4)**. 

![figure3](https://github.com/felipebita/credit_risk/assets/44379044/787b6159-18e2-495f-a985-fa121874b456)

**Figure 3.**  Bar plots showing the proportion of each type of home ownership. A) General proportion. B) Proportion in the default and not default loans.

![figure4](https://github.com/felipebita/credit_risk/assets/44379044/e0d1efbf-446b-49aa-9b01-ff28778d9eb5)

**Figure 4.**  Bar plot showing the proportion of each loan intent. A) General proportion. B) Proportion in the default and not default loans.

Continuing, the variable borrowers file (previous loan default) showed that most of the borrowers did not have defaults in their file (80%) and considering not default and default, the percentage of default in the file increased from 16% to 30% **(Figure 5)**. Finally, in respect to the loan grade variable, each class representativeness diminued as it goes from A to G (39% to 0.2%), and comparing not default and default loans, the classes A, B and C showed reductions in their proportions, while D, E, F and G showed increases **(Figure 6)**. Those results shows that there is a higher risk of default in loans made by people who live on rent or have the house mortgaged, that borrowed with the intent of debt consolidation or medical use and have defaults in their default file. Furthermore, the algorithm used for grading the borrowers in fact can give an indication of default loan risk.

![figure5](https://github.com/felipebita/credit_risk/assets/44379044/8c6e0cb5-c097-44e6-b77c-7f8fb0a654b8)

**Figure 5.**  Bar plot showing the proportion of previous defaults in loan record. A) General proportion. B) Proportion in the default and not default loans.

![figure6](https://github.com/felipebita/credit_risk/assets/44379044/32b17c22-585d-4b57-961e-2282f9db4685)

**Figure 6.** Bar plot showing the proportion of loan grade in loan record. A) General proportion. B) Proportion in the default and not default loans.


## **4 - Machine Learning Modeling Results**

In the machine learning modeling step, the best evaluated model was XGB and no difference was observed in relation to scalled and not scalled data **(Table 2)**. Following with the XGB model, the isotonic and sigmoid calibration methods were evaluated. Eventhough the calibration methods provided better results for Precision and F1, in this specific case, once the objective is to avoid the maximum of defaults, the Recall is the most important metric. This way, the not calibrated XGB model showed the best performance. **(Table 3) (Figure 7)**. 

**Table 2.** Results regarding the evaluation metrics for all the classification models.

| Model | Balanced Accuracy	| Precision	| Recall	| F1	| Kappa	| AUC |
|:---------:|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|:--------------:|
|LR |	0.576 +/- 0.004	| 0.741 +/- 0.016	| 0.169 +/- 0.009	| 0.275 +/- 0.012	| 0.212 +/- 0.011	| 0.758 +/- 0.005 |
|MLP |	0.614 +/- 0.088	| 0.764 +/- 0.237	| 0.338 +/- 0.326	| 0.311 +/- 0.227	| 0.229 +/- 0.174	| 0.791 +/- 0.03 |
|LR scaled	|	0.725 +/- 0.005	| 0.741 +/- 0.009	| 0.499 +/- 0.01	| 0.596 +/- 0.009	| 0.511 +/- 0.01	| 0.865 +/- 0.003 |
|MLP scaled	|	0.843 +/- 0.007	| 0.933 +/- 0.014	| 0.7 +/- 0.014	| 0.8 +/- 0.01	| 0.755 +/- 0.012	| 0.919 +/- 0.005 |
|RF scaled |	0.856 +/- 0.007	| 0.976 +/- 0.003	| 0.717 +/- 0.016	| 0.826 +/- 0.009	| 0.787 +/- 0.011	| 0.932 +/- 0.004 |
|RF	|	0.856 +/- 0.007	| 0.974 +/- 0.005	| 0.718 +/- 0.015	| 0.827 +/- 0.01	| 0.788 +/- 0.011	| 0.932 +/- 0.003 |
|LGBM	|	0.86 +/- 0.007	| 0.977 +/- 0.002	| 0.724 +/- 0.014	| 0.832 +/- 0.009	| 0.794 +/- 0.01	| 0.947 +/- 0.003 |
|LGBM scaled	|	0.86 +/- 0.007	| 0.977 +/- 0.002	| 0.724 +/- 0.014	| 0.832 +/- 0.008	| 0.794 +/- 0.01	| 0.947 +/- 0.003 |
|XGB scaled |	0.865 +/- 0.004	| 0.955 +/- 0.008	| 0.74 +/- 0.01	| 0.834 +/- 0.004 | 0.795 +/- 0.005	| 0.952 +/- 0.003 |
|**XGB** |	**0.865 +/- 0.004**	| **0.955 +/- 0.008**	| **0.74 +/- 0.011**	| **0.834 +/- 0.004**	| **0.795 +/- 0.005**	| **0.952 +/- 0.003** |

**Table 3.** Results regarding the evaluation metrics for the calibrated XGB models.

| Model | Balanced Accuracy	| Precision	| Recall	| F1	| Kappa | AUC |
|:---------:	| :---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|isotonic	| 0.854 +/- 0.007	| 0.994 +/- 0.003	| 0.71 +/- 0.014	| 0.828 +/- 0.009	| 0.79 +/- 0.01	| 0.952 +/- 0.003 |
|sigmoid	| 0.863 +/- 0.005	| 0.97 +/- 0.004	| 0.733 +/- 0.012	| 0.835 +/- 0.006	| 0.797 +/- 0.007	| 0.952 +/- 0.002 |
|**XGB**	| **0.865 +/- 0.004**	| **0.955 +/- 0.008**	| **0.74 +/- 0.01**	| **0.834 +/- 0.004**	| **0.795 +/- 0.005**	| **0.952 +/- 0.003** |

After deciding the best modeling technique, 80% of the data was separated to train the final model which was deployed. The evaluation of the final model was done using the remained 20% of the data. The model showed metrics very similar to the results obtained in the cross-validation (

**Table 4.** Results regarding the evaluation metrics for the model selected to be deployed
| Model | Balanced Accuracy	| Precision	| Recall	| F1	| Kappa | AUC |
|:---------:	| :---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|**XGB**	| 0.865	| 0.96	| 0.74 |0.836 | 0.797	| 0.95 |

![image](https://github.com/felipebita/credit_risk/assets/44379044/706e75d5-bca8-4889-b909-b7704de8134f)

**Figure 7.** Confusion matrix of the model selected to be deployed.




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
