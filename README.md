# Project 2 - Ames Housing Data and Kaggle Challenge


## Problem Statement

To build a regression model with the lowest error to predict Sales Price of houses sold in Ames


## Objective
 1) Read 'train.csv' to clean and organise data 
 
 2) Create a regression model based on the Ames Housing Dataser to predict the price of a house at sales in Ames, IA using train-test split
 
 3) Predict Sales Price using predictor values given in 'test.csv' to generate unknown data
 
 
 ## Executive Summary

### Contents:

- [Data Preparation](#1.Data-Preparation)
- [One Hot Encoding](#2.One-Hot-Encoding-for-Categorical-Variables)
- [Feature Engineering](#3.Features-Engineering-with-Lasso)
- [Model Pre-Work](#4.Preparing-Data-For-Modelling-Selections)
- [Train/Test Spilt](#5.Model-Prep:-Train/Test-Split)
- [Instantiation](#6.Model-Prep:-Instantiate-models)
- [Model Selection](#7.Model-Selection)
- [Prediction](#8.Prediction)
- [Summary](#9.Summary)


## Data Dictionary

Refer to the [data description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).


## Model Deployed For Selection

 1) Linear Regression
 
 2) Ridge Regression
 
 3) Lasso Regression
 
 4) Elastic Net
 
 
## Summary
 
Linear Regression (LR) Model is chosen for the modelling of the Ames Housing data, for the prediction of Sale Price. The model is able to achieve a R2 score of 0.887, which means it covers 88.7% of the data. And a RMSE value of **275706** based on Kaggle submission. 

![Kaggle RMSE Score](https://github.com/Singforthelaughter/DSI12_Project2/tree/master/img/Kaggle_Submission.png)

The R2 value differences between LR(0.885) and Lasso(0.887) is very small, which means the model is not overfitting and variance is small. This can be further proven with the small difference between R2 value of LR for model selection (0.885) and model fitting (0.887). 

30 features were used for the LR model:

| **Features**              | **Coefficient**    |
|-----------------------|----------------|
| Neighborhood\_GrnHill | 16899\.599814  |
| Neighborhood\_StoneBr | 57611\.905242  |
| Exterior 1st\_CemntBd | 54873\.019475  |
| Neighborhood\_NridgHt | 32298\.972379  |
| Neighborhood\_NoRidge | 25516\.544566  |
| Foundation\_Slab      | 23970\.306043  |
| Neighborhood\_Crawfor | 19596\.649689  |
| Fireplaces\_2         | 19109\.097456  |
| Exterior 1st\_AsbShng | 15375\.574201  |
| Garage Type\_NA       | 13876\.619812  |
| Exterior 1st\_BrkFace | 12442\.046459  |
| Kitchen Qual          | 11942\.690442  |
| Exter Qual            | 11923\.004578  |
| Overall Qual          | 10415\.860683  |
| Garage Finish         |  3876\.936165  |
| House Style\_SLvl     |  2696\.373104  |
| Total SF              |    38\.337968  |
| Age                   |  \-330\.274008 |
| Neighborhood\_NAmes   | \-1128\.696364 |
| House Style\_1Story   | \-2227\.677653 |
| Exterior 1st\_VinylSd | \-3708\.398254 |
| Neighborhood\_OldTown | \-4297\.397412 |
| Fireplaces\_0         | \-4526\.431922 |
| Remod\_0              | \-5868\.865238 |
| Mas Vnr Type\_BrkFace | \-7395\.776814 |
| MS SubClass\_90       | \-21019\.938726  |
| Exterior 2nd\_AsbShng | \-23354\.881996  |
| MS SubClass\_160      | \-25164\.033226  |
| MS SubClass\_120      | \-28192\.618684  |
| Exterior 2nd\_CmentBd | \-44892\.389644  |

Based on the coefficient, we can see that being in a certain neighbourhood and having certain features in a house will have more effect on the Sale Price of the house. For example, being in the neighbourhood GrnHill will increase the Sale Price by USD 16,899, while having house exterior covered with cement board (Exterior 2nd_CmentBd) will decrease the prices by USD 44,892.

Surprisingly, the Total Square Feet (Total SF) and Age of the house do not affect the Sale Price of the house that much in relatively to other 28 features. We can also possibly deduce where the richer and poorer neighbourhood in AMES based on whether the neighbourhood has + or - coefficient on Sale Price. 

In summary, we can conclude that the LR model for the AMES housing dataset has addressed the problem statement of estimating Sale Price of AMES houses with lowest possible error.
