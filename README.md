# Project Title 
> Assignment - Advanced Regression.

> Problem Statement :
A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them at a higher price. The company wants to know

Which variables are significant in predicting the price of a house, and
How well those variables describe the price of a house.
Based on various market surveys, the consulting firm has gathered a large dataset of different types of cars across the American market.

> Business Goal :
Build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.
Determine the optimal value of lambda for ridge and lasso regression.
This model will then be used by the management to understand how exactly the prices vary with the variables
They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns.
The model will be a good way for the management to understand the pricing dynamics of a new market.


## Table of Contents
0. Basic Stuff
1. Understanding the Data
2. Data Cleaning / Imputation / Deriving colums 
3. Data Visualization
4. Data Preparation
5. Splitting set into Train and test
6. RFE
7. Model Building


## Conclusions
# 1. Understanding the Data
Shape  (1460, 81)

# 2. Data Cleaning / Imputation / Deriving colums 
Removed categorical attributes that have more than 90% data associated to one value
21 cols remvoed from analysis that may have contained skewed data

Remove numerical attributes that have more than 90% data associated to one value
1 cols remvoed from analysis that may have contained skewed data

Derived col 1 -- IsRemodelled
Derived col 2 -- BuiltOrRemodelledAge 
Derived col 3 -- if the Garage is old or new.

there are no null values in the dataset
there are no duplicte values in the dataset

Removed values beyond 98% for LotArea
Removed values beyond 98% for MasVnrArea
Removed values beyond 98% for TotalBsmtSF
Removed values beyond 98% for WoodDeckSF
Removed values beyond 98% for OpenPorchSF

percentage of data retained --> 90.21
--> Shape (1317, 47)


# 3. Data Visualization
--> The target value "SalePrice" is normalized
--> TotRmsAbvGrd and GrLivArea show 83%
--> Garage Area and Garage Cars show 89%


# 4. Data Preparation
After Creating dummies
--> Shape (1317, 112)

# 5. Splitting set into Train and test
X_train.shape (921, 111)
X_test.shape (396, 111)
y_train.shape (921,)
y_test.shape (396,)

# 6. RFE
RFE to get the best 50 features out of the 111 features 


# 7. Model Building
Fitting 5 folds for each of 27 candidates, totalling 135 fits
MSE of Ridge with alpha 10 is 0.010818669121321043
MSE of Lasso with alpha 0.0005 is 0.010953019379927487

# 8. Conclusion
Conclusion : The optimal lambda value in case of Ridge and Lasso is as below:

Ridge - 10
Lasso - 0.0005
The Mean Squared error in case of Ridge and Lasso are:

Ridge - 0.010818669121321043
Lasso - 0.010953019379927487

The Mean Squared Error of Ridge is "extremely" slightly lower than that of Lasso

But as Lasso helps in feature reduction (as the coefficient value of one of the feature became 0), Lasso has a better edge over Ridge.

Hence based on Lasso, the key factors that generally affect the price are the - 
1. Zoning classification
2. Overall quality
3. Total basement area in square feet
4. Foundation type of the house
5. condition of the house
6. Number of cars that can be accomodated in the garage




