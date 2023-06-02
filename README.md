![fraud](https://user-images.githubusercontent.com/44379044/131612132-7b78ceaa-09f9-4eef-b86a-b3979fae2909.png)

# **Credit Risk Analysis**

## **1 - Business Understanding**

## **2 - Solution Strategy**
A data science project was developed to build, evaluate and launch a machine learning model capable of classifying transactions as fraudulent or legitimate. The project consists of the following steps:

**2.1 - Data Analysis and Preparation**

In this step the data was analyzed in terms of structure, features information, datatypes, missing data and statistics summary. Furthermore, features were selected and the data prepared to be used in the modeling.

**2.2 - Machine Learning Modeling**

For this project, seven ML models for classification: Naive Bayes (NB), Logistic Regression (LR), K-Nearest Neighbors (KNN), Suport Vector Machine (SVM), Random Forest (RF), Multilayer perceptron (MLP), Light Gradient Boosting Machine (LGBM) and XGBoost (XGB); were evaluted considering four metrics: Balanced Accuracy, Precision, Recall, F1 and Kappa; in a 5-fold cross validation strategy. Scalled and not scalled data were tested and hyperparameter tunning was done for the best model.
  
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

| Balanced Accuracy	| Precision	| Recall	| F1	| Kappa	| AUC |
|:---------:|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|
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
**6.1 What is the model's Precision and Accuracy?**

* The 5-fold cross-validation of the model showed a balanced accuracy of **0.865 +/- 0.013** and a precision of **0.961 +/- 0.021**.

**6.2 How Reliable is the model in classifying transactions as legitimate or fraudulent?**

* The model showed a F1 score of **0.829 +/- 0.017**

**6.3 What is the Expected Billing by the Company if we classify 100% of transactions with the model?**

* Using the model the company can revenue **$63.615.970**.

**6.4 What is the Loss Expected by the Company in case of model failure?**

* The company would return **$6.355.497** for the miss detection of fraud transactions.

**6.5 What is the Profit Expected by the Blocker Fraud Company when using the model?**

* Using the model the company can revenue **$57.260.473**.

## **7 - Conclusions and Prospects**

The final model obtained in this project had a really good performance, which makes the company business profitable. The prospects for the service would be increase the trainig data set and evaluate different classification models such as neural network, aiming to enhance the performance of the service.    
