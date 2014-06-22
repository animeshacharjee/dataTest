Objective
========================================================


In this problem two data sets are given. One of the data set is acting as training data (pml-training) and other one is test data (pml-testing).  In the training data,  "classe" acting as response variable which really made up of different types of classes such as "A", "B", "C", "D" and "E". I  need to build a model with the training data set which can predict the "Class" (ID Numbers) in the test data

Data quality checks
=======================================================
Training data consists of 19622 observations (rows) and 160 features including response variable. To make the problem simple, I removed some columns which are denoted almost all the rows "NA" values. After removing those columns the total features were 53. So, the dimensions of the matrix are following: number of Observations (n)=19622 and number of features(p)= 53
In the similar way, the dimensions of the test data were, number of observations (n)=20 and number of features(p)= 53


Model building
=======================================================
Before model building the training dataset were pre-processed by auto-scaled (variance=1, mean=0) hence giving same weight for all the features. It was done to compare the effect of the features on the response variable. The response is a multiple class such as "A", "B", "C", "D", and "E". I tried to fit a classification algorithm which is based on multiple decision trees called as "Random Forest". Each decision tree is built from a bootstrap sample of the original data set. That is, some samples will be included more than once in a particular bootstrap sample, whereas others will not appear at all. Generally, about two thirds of the samples will be included in a bootstrap sample and one third will be left out (called the out-of-bag samples or OOB samples). We used for the "mtry" parameter one third of the total number of variables used which means around ~17 features were used. 

Cross validation and error estimation
======================================================
To optimize the extra parameters in Random Forest method, we optimize the parameters like "mtry" using 10 fold cross validation. And choose that value in the model for fitting test data set. The out of bag (OOB) estimate of error rate: 0.13, which was low and give confidence to apply this model on test data set. The result is stored in the object in R. And then test data is fitted in the model and the response 
ID nr are           1   2  3  4   5   6  7  8  9  10 11 12 13 14 15 16 17 18 19 20
and predicted values for each of the id numbers are following:       B  A  B  A  A  E  D  B  A  A  B  C  B  A  E  E  A  B  B  B







