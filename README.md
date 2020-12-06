# Real Estate: STAT 350 fall 2020 Final Project Group15

### Table of Contents
   - [Abstract](#abstract)
   - [Introduction](#introduction)
   - [Data Description](#data-description)
   - [Data Source](#data-source)
   - [Methods](#methods)
   - [Conclusion](#conclusion)




### Abstract

This project presents a statistical analysis of real estate data of New Taipei, Taiwan. The primary interest is in estimating the association of transaction date, house age, distance to the MRT station, longitude, number of present convenience stores on house price of unit area. We built a regression model using cross-validation to identify linear relationship between the house price of unit area and other predictor variables in the time frame of 2012 August to 2013 July. The model identified the linear relationship between the house price and distance to the MRT(Mass Rapid Transit) station, latitude, number of present convenience stores, but not longitude and transaction date. This model does account for 60 percent of its variability.



### Introduction




### Data Description

This dataset Real estate.csv is a record of the transactions of real estates in Taiwan from August 2012 to July 2013. Each single datapoint is a transaction of an estate with properties that describe it. The original dataset consists of a single response variable, House price of unit area and 6 predictor variables: X1 Transaction Date, X2 houseage, X3 Distance to nearest MRT, X4 Number of convenience stores, X5 Latitude, and X6 Longitude. In this project we introduced 2 new data points. (not complete i dont know why we chose those specific points, prof wanted us to state why we chose the datapoints we did)

### Data Source

“Real estate price prediction” from kaggle by Bruce:(https://www.kaggle.com/quantbruce/real-estate-price-prediction)


### Methods
In order to determine what the best model for the given data set was, we had to use multiple different analysis tools and techniques. One of the first methods we used was the pairs plot. This plot was used to determine if there was a linear relation, whether it be positive or negative, between any two given variables. It also told us if there was any strong correlation between two independent variables that we might have to watch out for. After we determined that a linear model was appropriate to use we used cross validation inorder to use some data to predict the rest. We used a sampling size of 80% for the training set which meant the remaining 20% went to the test set. Taking the training set we made a model and tested it against the test set. This method helps us determine the accuracy of the model and whether it is considered to be adequate or not



### Conclusion

We discovered longitude and transaction date are not significant as their p-values were larger than 0.05. Transaction date must be a crucial factor determining house price, but due to insufficient amount of data, the model does not capture it as significant. Distance to the MRT station, house age, latitude, number of present convenience stores have linear relationship with the house price of the unit area. Residual analyses showed there are no presence of outliers in the data set, although we introduced two outliers, one having high cost, the other having low cost. However, adjusted R-Squared value of the model is 0.6 and Root mean square error(RMSE) divided by the standard deviation equals 2.69, which does not adequately explain the variability of the data set.
