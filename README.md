# Monthly-Amtrak-Ridership-Forecasting Project

# Table of Contents

--------

- [Authors and Collaborators](#authors-and-collaborators)
- [Installation](#installation)
- [Technologies](#technologies)
- [About the Project](#about-the-project)
  * [Problem Statement](#problem-statement)
  * [Justification](#justification)
- [Data Exploration](#data-exploration)
  * [Original Data](#original-data)
  * [Data Set Dictionary](#data-set-dictionary)
- [Data Preprocessing](#data-preprocessing)
- [Data Splitting](#data-splitting)
- [Model Strategies](#model-strategies)
- [Presentations and Reports](#presentations-and-reports)
- [Code](#code)
- [Data Visualizations](#data-visualizations)
- [Performance Results](#performance-results)
- [Conclusion](#conclusion)
- [References](#references)

-------

# Authors and Collaborators
- [Jimmy Nguyen](https://github.com/jimmy-nguyen-data-science)
- [Luke Awino](https://github.com/Lukematic)



# Installation

Data Exploration and Modeling was all done in Rstudio

To clone this repository onto your device, use the commands below:

	1. git init
	2. git clone git@github.com:jimmy-nguyen-cal/Monthly-Amtrak-Ridership-Forecasting.git


## Technologies
- R-programming Language and Rstudio
- Microsoft Powerpoint
- Microsoft Word


# About the Project


## Problem Statement

The Amtrak client would like to know the number of passengers for the next three months. Based on historical data, Amtrak would like to model the behavior of ridership from 1991 to 1999. This will allow Amtrak to understand how well the new high-speed rail service affected the northeast U.S. from 2000 to 2013. The ridership data is collected monthly, reporting
the number of passengers. The task entails forecasting models to predict the number of passengers for the next three months in 2013. The forecasted number of passengers will determine the necessary adjustments to make improvements for the new service system.

## Justification

The purpose of this project is to forecast Amtrak ridership. With this information, Amtrak can better plan how to allocate funds, mainly for changing the routes and equipment management. Deciding whether or not to introduce a new passenger train service or make changes to existing service comes down to one question: how many more people will ride the train after the changes are made?. Being able to forecast which routes are close to their maximum ridership, Amtrak can prioritize these routes by adding rail cars and or more routes. This will increase profitability; using this information, routes and rail cars can be added to busy routes, increasing capacity for more paying customers who may have had to seek other means of transportation by mode or competitor. Amtrak can reallocate resources from slower routes to busier routes with this forecasting information, thereby maximizing their profits by either cutting down on routes or reallocating rail cars.

# Data Exploration

The data set was obtained from the Bureau of Transportation Statistics, which includes monthly Amtrak ridership data from January 1991 until May 2013. There are 269 rows with only two columns containing the timestamp of each month in that respective year and the total counts of ridership. A time-series trend was visible during the exploratory data analysis over the years. This series also shows signs of seasonality where this may be hypothesized as non-stationary


## Original Data 

[Amtrak Ridership](https://www.bts.gov/archive/publications/multimodal_transportation_indicators/2013_08/passenger/amtrak_ridership)

## Data Set Dictionary

- Month: From Jan to Dec in 1991 to 2013
- Number of Passengers: How many passengers were riding during that month of that year. 


# Data Preprocessing

The first steps were renamed to the original columns of the data set to Dates and
Number_of_Passengers. Then the data was converted to a time series object to allow for further
time series analysis. The frequency of the time series object was set to 12 due to the observations
being monthly each year.

- Simple Smoothing Methods
- Dickey-Fuller Test to check for stationarity 
- Differencing to remove trends and seasonality


# Data Splitting 

Forecasting with time-series data also requires the appropriate partitioning to evaluate the performance of the models. There will be a training set, a validation set, and a test set similar to cross-sectional. Although partitioning data into these sets are usually done randomly, this is not the case for a time series. The first step is to decide the different training and validation periods. Meaning, the time window will need to be specified before partitioning into different sets. The training set consists of the earlier periods, while the validation set is the periods the model has not yet been trained on. This will be the later period. For the test period, this partitioning set will be the forecasted months the client has requested. Thus, the data splitting strategy for the Amtrak ridership data will be a fixed-partitioning method. The training period will be from January 1991 to May 2012. The validation period will be from June 2012 to May 2013. While the test period Amtrak requested is from June 2013 to August 2013.


# Model Strategies 

- Automated model selection for optimal exponential model
- Regression-based models
- AR1 Model
- ARIMA models
- Naive Forecast Models


# Presentations and Reports
[Final Report](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Report/Final%20Project%20Report%20-%20Team%203.pdf)
[Final Presentation Slides](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Presentation/Amtrak%20Ridership%20Presentation%20-%20Team%203.pptx)

# Code
[R-studio Notebook - PDF](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Code/Monthly-Amtrak-Ridership-Forecasting-Final-Project---Team-3.pdf)

# Data Visualizations
![EDA](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/EDA.png)
![Moving Averages](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/Moving%20Averages%20Plot.png)
![ACF and PCF plot](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/acf%20and%20pcf%20plots.png)
![Data Preprocessing](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/comparison%20betwern%20different%20differenced%20data.png)
![Optimal Exponential Model](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/Models%20with%20Additive%20or%20multiplicative%20trends.png)
![AR1 Model](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/ar1%20model.png)
![ARIMA Model](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/optimal%20arima%20model.png)
![Seasonal Naive Model][https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/seasonality%20naive%20model.png)

# Performance Results
![Performance Results](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/Final%20Results.PNG)

Based on the results, there are a handful of different performance metrics to evaluate across the models. The following models are competing against each other: the seasonal naive forecast model, the optimal exponential model, and the regression model with a monthly seasonality and linear and quadratic trends, and the ARIMA models. The selected performance metric is the root mean square error (RMSE). Lower values of the RMSE indicate a model with higher performance. A benefit of using this performance metric over the others is that the RMSE will be in the same units as the original data. Previously, the AIC scores were used for comparison for only a quick evaluation of the training set to see the complexity of each model. Since the task is forecasting future values, using the RMSE score from the test set is more appropriate. The following tables in Table 1 display the different performance metrics of the previously stated models.


# Conclusion
![Tableau Final Forecasts](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/Tableau%20Forecast%20Model.png)
![Final Forecasts](https://github.com/jimmy-nguyen-data-science/Monthly-Amtrak-Ridership-Forecasting/blob/main/Plots/final%20forecasts.PNG)

The final model was used to make forecasts for the month of June to August of 2013. June of 2013 is forecasted to have 2,793,575 ridership. Then July of 2013 will see an increase with a total of 2,900,579 ridership. However, the final model forecasted a decrease in ridership with a total of 2,807,599 ridership for the month of August. Table 2 below shows the point forecasts along with the 80% and 95% confidence intervals for the possible low and high forecasts range.


# References

Amtrak ridership. Bureau of Transportation Statistics. (2013). Retrieved December 5,
2020, from https://www.bts.gov/archive/publications/multimodal_transportation_indicators/2013_08/passenger/amtrak_ridership


Waite, M. (n.d.). Why the U.S. needs to get on track with high-speed rail. Greenbiz.
Retrieved November 21, 2021, from https://www.greenbiz.com/article/why-us-needs-get-track-high-speed-rail.


Ramadhani S., Dhini, A., & Laoh, E. (2020). Airline Passenger Forecasting using ARIMA and Artificial Neural Networks Approaches. 2020 International Conference on ICT for Smart Society (ICISS), ICT for Smart Society (ICISS), 2020 International Conference On, CFP2013V–ART, 1–5. https://doi-org.sandiego.idm.oclc.org/10.1109/ICISS50791.2020.9307571


Ye, Y., Chen, L., & Xue, F. (2019). Passenger Flow Prediction in Bus Transportation System using ARIMA Models with Big Data. 2019 International Conference on Cyber-Enabled Distributed Computing and Knowledge Discovery (CyberC), 2019 International Conference On, 436–443. https://doi-org.sandiego.idm.oclc.org/10.1109/CyberC.2019.00
