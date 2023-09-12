# featureExtraction_NICU

## Introduction
Women are considered to be the backbone of a happy family and a progressive
nation, and their ability to carry out multiple roles with great efficiency is
widely appreciated. Childbirth is one of the most significant responsibilities that
women undertake, and they need to be both physically and mentally strong to
enable a healthy pregnancy and childbirth experience. Here we aim to
investigate the impact of various maternal factors on the health outcomes of
infants at birth. The project focuses on identifying the key factors that

contribute to adverse birth outcomes, such as preterm birth, low birth weight, c-
section delivery and requirements for nicu-stay. By analyzing these factors, the

project aims to provide a better understanding of the complex interactions
between maternal health and birth outcomes.

## Related Works
Several studies have examined the relationship between various maternal
factors and birth outcomes. S study by Smith et al. (2018) found that maternal
age was a significant predictor of birth weight and gestational age, with older
mothers having a higher risk of preterm birth and low birth weight infants.
Another study by Jones et al. (2019) examined the impact of maternal education
on birth outcomes and found that higher levels of education were associated
with better birth outcomes, including higher birth weight and lower risk of
preterm birth. In this project we have followed the work of Himani Deshpande
and Leena Ragha on “Mother’s Lifestyle Feature Relevance for NICU and
Preterm Birth Prediction”.
[Ref: https://www.itm-conferences.org/articles/itmconf/pdf/2021/05/
itmconf_icacc2021_03039.pdf]

3. Motivation
Recent research has highlighted the importance of maternal factors in
determining birth outcomes. However, much of the existing literature has
focused on single factors in isolation, rather than considering the combined
impact of multiple factors. This study aims to fill this gap by investigating the
interplay between various maternal factors and birth outcomes.

1

## Objective
1. To investigate the associated risk in pregnancy
2. To investigate features affecting low birth weight and making a predictive
model
3. To investigate features that would cause C-section delivery and making a
predictive model
4. To investigate features that would require NICU stay requirements and
making a predictive model
## Dataset
We are going to use the MSF dataset that is publicly available on ieee website

(https://ieee-dataport.org/open-access/mother%E2%80%99s-significant-feature-
msf-dataset).

The dataset contains 23 mother’s physical and health features, 19 social
features, 8 stress features, 71 lifestyle features and 10 health outcome features.

## Implementation
## Workflow Diagram
![image](https://github.com/partho2001/featureExtraction_NICU/assets/42618752/db2d57bc-f227-4d42-8d54-0fbee0f0779d)

## Feature Selection
One of the main objective of out project is to identify the most affecting
features on birth outcome. Generally there are 3 methods to do feature
selection:
1. Filter method: In this method, the features are evaluated independently of
the target variable, and a ranking is created based on some statistical metric
like f_classif. The features with the highest score are then selected.
2. Wrapper method: This method involves selecting a subset of features by
evaluating the model's performance using different combinations of
features. A model is trained and tested on different subsets of features, and
the subset that gives the best performance is selected. For example we have
used Recursive Feature Elimination here in our project.
3. Embedded method: In this method, feature selection is embedded within
the learning algorithm itself. The model is trained and features are selected
based on their importance in the model. For example, we have used
Random Forest algorithm that uses information gain to select best features.
After applying these 3 methods on our three target variables namely
“Weight_Baby_Kg”, “NICU_Stay”, “C-section”, we came across 3 different
sets of ranking for each variable and later we selected those features which are
common in the result of 3 methods.
## feature extraction result
The result is as follows:
1. For the feature “Weight_Baby_Kg
[‘IVF’,'BMI','Age_Of_Mother','Contraceptive_Time','Excercise_During_Pr
egnency','Pollution_During_Pregnency','PCOS','Issues_Pregnancy_Cold_Vi
ral','Weight_Before_Pregnency','More_Dairy_Products_Marraige']
2. For the feature “NICU_Stay”
[‘BMI','Hemoglobin','Outside_Food_During_Teenage','Pollution_During_P
regnency','Excercise_During_Teenage','Weight_Before_Delivery','Intercour
se','Issues_Pregnancy_Gastric_Issues','Time_Spent_Mobile_Teengage','Issu
es_Pregnancy_Low_Amniotic']
6
3. For the feature “C-section”
['Your_Support_Others', 'More_Dairy_Products_Pregnency',
'Excercise_During_Pregnency', 'Time_Spent_Mobile_During_Pregnency',
'Fertility_Treatment', 'Travel_Mode_Pregnency', 'Education', 'BMI',
'Fruits_Salads_Marraige', 'Sibling', 'More_Dairy_Products_Marraige',
' A g e _ O f _ M o t h e r ' , ' I s s u e s _ P r e g n a n c y _ D i a b e t e s ' ,
'Alcohol_During_Pregnency', ‘Outside_Food_During_Teenage']

## Model Building

Firstly we split our dataset into two parts training data and testing data.
Now among the three target variable that we are dealing with, two of them
(“NICU_Stay”, “C-section”) are discrete variables and one
(“Weight_Baby_Kg”) is continuous variable.
So for those discrete target variable we have applied various classification
algorithms like Logistic Regression, Decision Tree, Random Forest and KNearest Neighbours and for that continuous variable we have use regression
algorithms like Linear Regression and Random Forest Regressor on our training
data.

## Result and Analysis

After applying the algorithms on our target variables the result that we get are
compared with the existing experimental data to validate our model’s accuracy.
It has been seen that for “Weight_Baby_Kg” the algorithm that mostly suited is
LinearRegression , for “NICU_Stay” it is K-Nearest-Neighbours and for “Csection” it is Decision Tree Classifier.
Then after performing hyper-parameter tuning on this algorithms we came to a
point that:
For “Weight_Baby_Kg” our model performs with a mean squared error of
0.387
For “NICU_Stay” our model performs with accuracy of 79.76% and
For “C-section” our model performs with accuracy of 67.67%.
7
The confusion matrix for the two classification models are shown below:


![image](https://github.com/partho2001/featureExtraction_NICU/assets/42618752/4a0b5465-4b58-4425-9609-12322aa51eba)

![image](https://github.com/partho2001/featureExtraction_NICU/assets/42618752/f1fca983-156c-4ba5-a7db-c5841ac0e816)

## Conclusion
In conclusion, this project highlights the importance of understanding the
impact of a mother's health on her child's birth. By analyzing the MSF dataset,
we identified several significant features that can be used to predict child health
outcomes. Our results suggest that decision trees and knn are effective machine
learning algorithms for predicting the impact of these features on child health.
This project has significant implications for healthcare providers, policymakers,
and families, as it provides insights into the factors that can impact child health
and highlights the importance of addressing maternal health to improve child
health outcomes


