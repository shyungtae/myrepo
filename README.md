# Real Estate: STAT 350 fall 2020 Final Project Group15

![](/images/map.png)
*Map view of the real estate*

## Table of Contents
   - [Abstract](#abstract)
   - [Introduction](#introduction)
   - [Data Description](#data-description)
   - [Data Limitation](#data-limitation)
   - [Data Source](#data-source)
   - [Methods and Results](#methods-and-Results)
   - [Conclusion](#conclusion)
   - [Appendix](#Appendix)




## Abstract

This project presents a statistical analysis of real estate data of New Taipei, Taiwan. The primary interest is in estimating the association of transaction date, house age, distance to the MRT(Mass Rapid Transit) station, longitude, latitude, number of present convenience stores on house price of unit area. We built a regression model using cross-validation to identify linear relationship between the house price of unit area and other predictor variables in the time frame of 2012 August to 2013 July. The model identified the linear relationship between the house price and distance to the MRT station, latitude, number of present convenience stores, but not longitude and transaction date. This model accounts for 63 percent of its variability.



## Introduction

For this project, we are using the real estate data set found at https://www.kaggle.com/quantbruce/real-estate-price-prediction, and introduced two additional data points. The main goal is to see if we can make an acceptable model to show the relationship between the given variables. We want to determine the association between the house price of unit area with the transaction date, house age, distance to nearest MRT station, number of convenience stores, latitude, and longitude. Additionally, we ask: are there any outliers in the data set? The presence of these outliers can drastically change the model by having a significant impact on the coefficients of each estimated beta. The final question we ask is: Are there any signs of multicollinearity? The existence of multicollinearity in the data can be detrimental to the overall linear model. Multicollinearity occurs when a variable is highly correlated with any of the other variables. This is a major issue since it can cause the coefficients of the model to sway, and it can reduce the accuracy of the estimated coefficients. 


## Data Description

The dataset “Real estate.csv” is a record of the transactions of real estates New Taipei, Taiwan from 2012 August to 2013 July. Each single datapoint is a transaction of a real estate with properties that describe it. The original dataset consists of a single response variable, House price of unit area and 6 predictor variables: X1 Transaction Date, X2 houseage, X3 Distance to nearest MRT, X4 Number of convenience stores, X5 Latitude, and X6 Longitude. In this project we introduced 2 new data points, to see if our model can identify them as outliers. The first point, 415 has a much greater house price per unit area than its nearby real estates. The second point, 416 represents the opposite, a much smaller house price per unit area than its nearby real estates. 

## Data Source

“Real estate price prediction” from kaggle by Bruce:(https://www.kaggle.com/quantbruce/real-estate-price-prediction)

## Data Limitation 

The dataset does not provide concise definition of its variables. We are unaware of the unit of distance for distance to MRT station and the unit of house price. We are not aware of what methods are used for data collection. We can provide more accurate interpretation of the result we found with concise definition of the variables.

## Methods and Results
The first step was to conduct a pairs plot. Pairs plot verified the linear relationships and correlations between any two given variables.

### Pairs Plot
![](/images/pairsplot.png)

### Correlation Plot
![](/images/corplot.png)


The pairs plot showed that the usage of a linear model was appropriate, and we decided to implement cross-validation. We used a sampling size of 80% for the training set and remaining 20% for testing. After building a model, we investigated for insignificant predictor variables.We removed the predictor variable if any of the p-values for each predictor variable had a value greater than 0.05. In our case, both the longitude and transaction had p-values greater than 0.05.

### Summary Table
![](/images/summary_table1.png)

Succeeding the removal of the non-significant predictor variables we performed the residual analysis for potential outliers in the trained linear model. We found that there were no evident outliers. More residual analysis can be found in Appendix A.

### Cook's Distance
![](/images/cook's_distance.png)

We then checked for any signs of multicollinearity by calculating the variance inflation factor of the model. In this model, we did not find any multicollinearity. We performed log transformation as the variance was not consistent. More residual analysis on transformation can be found in Appendix B.

### Log Transformation Residuals
![](/images/logTransformation,train,resd.png)


For variable selection, the stepwise regression determined whether or not the model should include all the predictor variables. With the finalized model, we tested with the test data set, and computed its R-squared, root mean sqaure error(RMSE) and mean absolute percentage error(MAE). Figures can be found in Appendix C.

### Predicted vs Actucal
![](/images/Predicted_vs_Actual.png)


## Conclusion

We discovered longitude and transaction date are not significant as their p-values were larger than 0.05. Transaction date must be a crucial factor determining house price, but due to insufficient amount of data, the model does not capture it as significant. Distance to the MRT station, house age, latitude, number of present convenience stores have a linear relationship with the house price of the unit area. Residual analyses showed there are no presence of outliers in the data set, even though we introduced two outliers, one having high cost, the other having low cost. Variance inflation factor indicated that there is no presence of multicollinearity. Adjusted R-Squared value of the model is 0.63 and Root mean square error(RMSE) divided by the standard deviation equals 2.69, which does not adequately explain the variability of the data set.

## Appendix

### Appendix A

### Train model - residual analysis

![](/images/residual_analysis,train.png)

### Appendix B

### Log transformation - residual analysis
![](/images/residual_analysis,log.png)

### Square-root transformation - residual analysis
![](/images/residual_analysis,sq.png)

### Appendix C

### Stepwise summary
![](/images/stepwise.png)

### Appendix D

codes can be found here.
Bruce:(https://github.com/shyungtae/myrepo/blob/main/final-Japnoop.rmd)
