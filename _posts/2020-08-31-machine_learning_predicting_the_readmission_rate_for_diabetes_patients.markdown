---
layout: post
title:      "Machine Learning: Predicting the Readmission Rate for Diabetes Patients"
date:       2020-09-01 03:26:54 +0000
permalink:  machine_learning_predicting_the_readmission_rate_for_diabetes_patients
---


I.	Introduction

Diabetes is a chronic disease in which the body’s ability to produce or respond to the hormone insulin is impaired that causes elevated levels of glucose in the blood and urine. Insulin is a hormone secreted by the pancreas to maintain normal blood glucose levels by facilitating cellular glucose uptake, regulating carbohydrate, lipid, and protein metabolism (1). There are two types of diabetes. In type 1 diabetes, patients don't produce insulin and in type II diabetes, patients don't respond well to insulin. Both can lead to diabetes complications such as irreversible damage to the eyes, kidneys, heart, brain, feet, and nervous system if the illness is not managed. People with the disease need regular care such as daily glucose monitoring and maintain a healthy diet to prevent a high concentration of sugar in the blood.  

In recent years, government agencies and healthcare providers have been focusing on 30-day readmission rates as a method to measure the quality of care. Deaths after 30 days releasing from a hospital may have less to do with the care given at the hospital. In 2012, the Centers for Medicare and Medicaid Services (CMS) launched its Hospital Readmission Reduction Program under the Patient Protection and Affordable Care Act (2). The program promotes reduction within 30 days of readmission rates by providing tax incentives for hospitals with healthy readmission rates. Readmission rates are excessive when the hospital's readmission rates are higher than the national average given the same sex, age, and co-existing conditions (3). 

Currently, the program does not cover diabetes as one of the illnesses. However, many hospitals and government agencies use the 30-day readmission rate as a method to analyze the quality of care. A high readmission rate causes a high burden on healthcare systems and patients. Diabetes remains one of the greatest risk factors for readmission (4). According to the CDC, 34.2 million Americans (10% of Americans) have diabetes (5). Diabetes cost the nation almost 250 billion dollars in 2012 (6). Hospitals may have more insights on how to improve the quality of care as well as reduce cost by measuring and analyzing the 30 days readmission rates for diabetes patients.

Project Goals

The goal of this project is to use machine learning to predict the readmission rate for diabetes patients. Among those who returned to the hospital, what were the commonalities? One study found that the diabetes patients who were treated with insulin were 80% more likely to return to the hospital compared to the non-insulin treated group in case of severe dysglycemia, an abnormality in blood sugar stability (7). 	

II.	Prediction Model

Random Forest was chosen as the model for the project. Random Forest is a supervised learning algorithm that is made of many decision trees. Each tree is trained using a bootstrap aggregating method where a random sample is chosen out of a set via replacing method then the algorithm is applied to that selected sample before combining them for a final prediction. Random Forest takes the average results of all the trees. The random forest provides certain benefits that make it more attractive than other models. Random Forest takes the averages the results over many decision trees from sub-samples, it gives a more accurate and stable prediction. 

In addition, Random Forest is also a powerful algorithm that optimizes both the number of trees and the number of features at each node. It works well with hyperparameters, categorical and numerical features. It does not require an extensive feature selection to find the most important feature. Instead, it searches for the best feature among a random subset of features. It can handle thousands of input variables without variable elimination. The Random Forest also has two methods of replacing missing values. The first method is to compute the median and replace the missing value with it. The second method is to replace the missing value only with the training set. It first calculates a rough estimation of what the value should be and then fill in the value by computing proximities. 


III.	Analysis of the chosen model

i.	Feature Importance

Artificial intelligence has been driven by understanding and unpacking the complex relations between different features in the data. Each can have a negative or positive effect on the outcome of the data. Random Forest embedded feature selection which makes it a robust to a noisy variable. There are a total of 115 features in the diabetes data but not all of them are equally important to make predictions.  These important features are identified as the number of diagnoses, number of inpatients, number of emergencies, number of medications, lab procedures, and discharge IDs with the addition of insulin, diabetes medication columns. They are selected by embedded methods within the Random Forest.  From a medical standpoint, if a patient had many diagnoses, many lab procedures, and prescribed many drugs, the patient was in a more serious condition comparing to those who needed fewer medications and lab tests and had a shorter list of diagnoses.  Thus, they would have a higher chance of returning to the hospital. These features are all important for predicting the likelihood of a patient returning to the hospital.  

i.	Missing Data

Medical records are highly sensitive data that comes with many restrictions about how the data is published and what information to include without revealing sensitive information about the patients. Medical data often comes with missing data. Unfortunately, missing data can hugely introduce biases in the estimate of the correlations. Random Forest can handle mixed types of missing data. It does it by update the missing data using proximity of the data, handles missing data through scaling, alternating the missing value when growing a forest. The data used in the project only contains 10% information about weight reported in a wide range such as >200lb. because the values are highly variable and majority of them are missing, they are dropped from the data. Another feature with missing data is race, max_glu_serum and A1Cresult. Since Race has only 2% of missing data, it is filled out as “Unknown”. As for A1Cresult, the missing values are handled by Random Forest model. 

ii.	Random Forest Parameters

Parameters chosen for the model are number of trees, tree depth, number sample splits, and number sample leaves. Each is chosen by running a base model through a list of possible values applicable for each parameter. The model gives a list of results for training and testing. Each parameter is set with a value that gives the best AUC score for both training and testing as shown in the example below. As the tree depth increases, the accuracy scores also increase. The ideal tree depth to pick from is the one with both high accuracy scores and the scores are consistent between training and testing datasets. The tree depth = 9 gives the best ACU training and test results in this case.
![](http://)
 
The Random Forest gives an accuracy score of 0.61 both for testing and training data. It indicates that there is some signal. However, it is not very strong. The Accuracy scores for Gradient Boosting Classifier and eXtreme Gradient Boosting are also very similar to those of Random Forest. 

V.	Conclusion

Prediction of hospital readmission for diabetes patients is possible using hospital record data about the diagnostics, medication, lab test results, medical specialty information and procedures given to patients. The models demonstrated that predictions can be made for readmission for diabetes patients. All models (Logistic Regression, XGBoost, and Random Forest) gave an accuracy score of ~ 61%. The model’s accuracy is slightly better than a coin toss. However, the score can be improved by tuning important features. These features may be best selected by those who have skills and training to understand what roles they play in the prediction. A patient with diabetes may return to the hospital within 30 days for many reasons according to a study published by "Journal of General Internal Medicine". Heart failure is the most common reason (8). The article also mentions that the vast majority of readmissions were not caused directly by diabetes. However, diabetes caused by severe dysglycemia is the 11th most common cause for hospitalization and the 14th most common for readmission (8). This may suggest that a patient is readmitted to the hospital initially for a non-diabetes reason, but later it turns out to be related to diabetes. The data is best analyzed with the help of a medical expert. This is where domain knowledge becomes key to selecting features and analyzing data.

IV.	References

1. Wilcox G. Insulin and insulin resistance. Clin Biochem Rev. 2005;26(2):19-39.

2. Ostling, S., Wyckoff, J., Ciarkowski, S.L. et al. The relationship between diabetes mellitus and 30-day readmission rates. Clin Diabetes Endocrinol 3, 3 (2017). https://doi.org/10.1186/s40842-016-0040-x

3. McIlvennan CK, Eapen ZJ, Allen LA. Hospital readmissions reduction program. Circulation. 2015;131(20):1796-1803. doi:10.1161/CIRCULATIONAHA.114.010270

4. Rozalina G. McCoy, Kasia J. Lipska, Jeph Herrin, Molly M. Jeffery, Harlan M. Krumholz, Nilay D. Shah. Hospital Readmissions among Commercially Insured and Medicare Advantage Beneficiaries with Diabetes and the Impact of Severe Hypoglycemic and Hyperglycemic Events. Journal of General Internal Medicine, 2017; DOI: 10.1007/s11606-017-4095-x.

5. Centers for Disease Control and Prevention. National Diabetes Statistics Report, 2020. Atlanta, GA: Centers for Disease Control and Prevention, U.S. Dept of Health and Human Services; 2020.

6. Diabetes—A Major Health Problem. https://www.cdc.gov/diabetes/ndep/pdfs/ppod-guide-diabetes-major-health-problem.pdf

7. McCoy RG, Lipska KJ, Herrin J, Jeffery MM, Krumholz HM, Shah ND. Hospital Readmissions among Commercially Insured and Medicare Advantage Beneficiaries with Diabetes and the Impact of Severe Hypoglycemic and Hyperglycemic Events. J Gen Intern Med. 2017;32(10):1097-1105. doi:10.1007/s11606-017-4095-x

8. McCoy, R.G., Lipska, K.J., Herrin, J. et al. Hospital Readmissions among Commercially Insured and Medicare Advantage Beneficiaries with Diabetes and the Impact of Severe Hypoglycemic and Hyperglycemic Events. J GEN INTERN MED 32, 1097–1105 (2017). https://doi.org/10.1007/s11606-017-4095-x






