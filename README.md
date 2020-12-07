# Real Estate: STAT 350 fall 2020 Final Project Group15

![](/images/map.png)
map

### Table of Contents
   - [Abstract](#abstract)
   - [Introduction](#introduction)
   - [Data Description](#data-description)
   - [Data Source](#data-source)
   - [Methods](#methods)
   - [Conclusion](#conclusion)




### Abstract

This project presents a statistical analysis of real estate data of New Taipei, Taiwan. The primary interest is in estimating the association of transaction date, house age, distance to the MRT station, longitude, number of present convenience stores on house price of unit area. We built a regression model using cross-validation to identify linear relationship between the house price of unit area and other predictor variables in the time frame of 2012 August to 2013 July. The model identified the linear relationship between the house price and distance to the MRT(Mass Rapid Transit) station, latitude, number of present convenience stores, but not longitude and transaction date. This model accounts for 60 percent of its variability.



### Introduction




### Data Description

The dataset “Real estate.csv” is a record of the transactions of real estates in Taiwan from 2012 August to 2013 July. Each single datapoint is a transaction of a real estate with properties that describe it. The original dataset consists of a single response variable, House price of unit area and 6 predictor variables: X1 Transaction Date, X2 houseage, X3 Distance to nearest MRT, X4 Number of convenience stores, X5 Latitude, and X6 Longitude. In this project we introduced 2 new data points, to see if our model can identify them as outliers. The first point, 415 has a much greater house price per unit area than its nearby real estates. The second point 416 represents the opposite, a much smaller house price per unit area than its nearby real estates. 

### Data Source

“Real estate price prediction” from kaggle by Bruce:(https://www.kaggle.com/quantbruce/real-estate-price-prediction)

### Data Limitation 

The data set does not provide concise definition of its variables. We do not know the unit of distance for distance to MRT station and the unit of house price. We are not aware of what methods are used for data collection.

### Methods and Results
First method we used was the pairs plot. Pairs plot verified linear relationship and correlation between any two given variables.

![](/images/corplot.png)

The pairs plot showed that linear model was appropriate, and we decided to implement cross-validation. We used a sampling size of 80% for the training set and the other 20% for testing. After building a model, we investigated insignificant predictor variables. If any of the given p-values for each predictor variable had a value greater than 0.05, then we removed the variable. Succeeding the removal of the non-significant predictor variables we performed the residual analysis for potential outliers on the trained linear model, and concluded that there are no outliers.

![](/images/Cook's Distance 2, Train.png)


We then checked for any signs of multicollinearity by calculating the variance inflation factor of the model. In this model, we did not find any multicollinearity. We performed log transformation as the variance was not consistent.

![](/images/Residual vs Fitted,Train.png)

For variable selection, the stepwise regression determined whether or not the model should include all the predictor variables. With the finalized model, we tested with the test data set, and computed its R-squared, root mean sqaure error(RMSE) and mean absolute percentage error(MAE).

![](/images/Predicted vs Actual.png)


### Conclusion

We discovered longitude and transaction date are not significant as their p-values were larger than 0.05. Transaction date must be a crucial factor determining house price, but due to insufficient amount of data, the model does not capture it as significant. Distance to the MRT station, house age, latitude, number of present convenience stores have linear relationship with the house price of the unit area. Residual analyses showed there are no presence of outliers in the data set, although we introduced two outliers, one having high cost, the other having low cost. Variance inflation factor indicated that there is no presence of multicollinearity. Adjusted R-Squared value of the model is 0.6 and Root mean square error(RMSE) divided by the standard deviation equals 2.69, which does not adequately explain the variability of the data set.

### Appendix


