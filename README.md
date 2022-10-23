# Hourly-electricity-price-forecasting

This dataset contains 4 years of electrical consumption, generation, pricing, and weather data for Spain. Consumption and generation data was retrieved from ENTSOE a public portal for Transmission Service Operator (TSO) data. Settlement prices were obtained from the Spanish TSO Red Electric España.

## Datasets:
#### Weather data

![image](https://user-images.githubusercontent.com/56879680/197404941-7587fa22-fb4e-44fe-86e6-7ebe77ec5f21.png)
#### Energy data

![image](https://user-images.githubusercontent.com/56879680/197404981-1dd66a2b-9730-4e2a-be7c-eb9ee734596d.png)

## Approaches:
#### Base implementation
Feeding bossting models with 2015--->2017 years as training data and 2018 as testing data
#### Multiple train test splits
Test size remains the same, train size increases after each split
![image](https://user-images.githubusercontent.com/56879680/197405378-b6194644-a56f-486b-b6e1-17228c7df09e.png)
#### Walk forward validation
In time series modelling, the predictions over time become less and less accurate and hence it is a more realistic approach to re-train the model with actual data as it gets available for further predictions.
#### Hybrid approach
We adapt the time series data to supervised learning algorithms with a different approach
* Multivariate forecasting function (i.e. using only the previous time-steps of the electricity price vs. also using other features) using a different number of previous time-steps as the features for the models (3, 10 and 25 previous time-steps for all the used features)
* We choose the adequate time lags for the price hourly prediction
-- We concatenate the following datas :
![image](https://user-images.githubusercontent.com/56879680/197405715-3bf7479b-c399-4193-94e1-a2dffd8d31da.png)
--  We choose the adequate time lag using autocorrelation analysis
![image](https://user-images.githubusercontent.com/56879680/197405795-cfa3c0ba-90f4-43bd-ab02-a4c88134e9e1.png)




