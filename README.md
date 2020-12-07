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

This dataset “Real estate.csv” is a record of the transactions of real estates in Taiwan from 2012 August to 2013 July. Each single datapoint is a transaction of an estate with properties that describe it. The original dataset consists of a single response variable, House price of unit area and 6 predictor variables: X1 Transaction Date, X2 houseage, X3 Distance to nearest MRT, X4 Number of convenience stores, X5 Latitude, and X6 Longitude. In this project we introduced 2 new data points, to see if our model can identify them as outliers. The first point, 415 has a much greater house price per unit area than its nearby estates. The second point 416 represents the opposite, a much smaller house price per unit area than its surrounding estates. 

### Data Source

“Real estate price prediction” from kaggle by Bruce:(https://www.kaggle.com/quantbruce/real-estate-price-prediction)


### Methods
To find out what the best model for the given data set was, we had to use multiple different analysis tools and techniques. One of the first methods we used was the pairs plot. This plot was used to determine if there was a linear relation, whether it be positive or negative, between any two given variables. It also told us if there was any strong correlation that we might have to watch out for. After we determined that a linear model was appropriate to use we used cross-validation in order to use some data to predict the rest. We used a sampling size of 80% for the training set which meant the remaining 20% went to the test set. Taking the training set we make a model and test it against the test set. This method helps us determine the accuracy of the model and whether it is considered adequate or not. After running the model we determine if there are any predictor variables we should remove from the model. We found this out by seeing if any of the given p-values for each predictor variables had a value greater than 0.05. If any of the variables had a p-value of more than 0.05 it meant that they were not significantly associated with the response variables and could be taken out of the model. Succeeding the removal of the non-significant predictor variables we did the residual analysis on the trained linear model. We plotted the model on multiple different plots to determine if there were any outliers, leverage, or influential points. We then checked for any signs of multicollinearity by finding the Vif values of the model. If any values exceeded 5 it indicated that there was multicollinearity in the model and we had to remove the corresponding predictor variable. One of the key methods we used was introducing two different transformations. We did this because we wanted to test the model and see which one was the best from the log and square root model. After choosing the best-transformed model we then determined whether or not there were any outliers, leverage, or influential points. One of the last methods we used was variable selection. The stepwise regression helped us determine whether or not the model we had up until that point was best suited to include all the predictor variables or remove some, which allowed us to finalize our model. The last thing we did was run a full analysis on our final model. We started by using the finalized model and used it to predict the test dataset. With that we were able to find the plot of the prediction, find R-squared, root-mean-square error, and mean absolute percentage error. All these helped us determine how well the model explained the data set. 


### Conclusion

We discovered longitude and transaction date are not significant as their p-values were larger than 0.05. Transaction date must be a crucial factor determining house price, but due to insufficient amount of data, the model does not capture it as significant. Distance to the MRT station, house age, latitude, number of present convenience stores have linear relationship with the house price of the unit area. Residual analyses showed there are no presence of outliers in the data set, although we introduced two outliers, one having high cost, the other having low cost. However, adjusted R-Squared value of the model is 0.6 and Root mean square error(RMSE) divided by the standard deviation equals 2.69, which does not adequately explain the variability of the data set.
