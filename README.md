# Taxi-Demand-Prediction-Study

## Task definition
This is a time-series forecasting and regression problem. It takes the previous three hours pick-up data as given input to predict the next 5min/15min/30min future’s number of pickups.

## Dataset
New York City Taxi and Limousine Commission (TLC) Trip Record Data is leveraged in this study project.
the whole dataset is huge, yellow taxi pick-up happened in Manhattan after Y2018 (Jan to June) is
used. In addition, Y2020’s data is much less than before because of the COVID-19 impact, which may cause a big
difference in data distribution between the data of Y2020 and before Y2020. So in this demo, Y2020’s data is not
included. The following is the finally split of the dataset:
* Train Data: 9 months (2018/1 ~ 2018/6 and 2019/1 ~ 2019/3)
* Test Data :3 months (2019/4 ~ 2019/6)<br/>
All data can be downloaded in the following URL:<br/>
https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page

## Data Cleaning
Records meet the following conditions are dropped.
* ID of pick-up location not in Manhattan
* Trip duration are below 0 or longer than 24 hours
* Trip distance is longer than 200 miles

## Feature engineering
Records in dataset are binned in 5-minutes period. For one prediction, the input is a 36-element-length array (3 hours)
and the next 6-element-length array (30 minutes) will be calculated as true labels.
![image](https://github.com/ohmycola/Taxi-Demand-Prediction-Study/blob/main/images/feature.png)

## Model selection
A LSTM model is used as baseline model.
I have tried a 1D-CRNN model, but the performance is not good, I will try to fine-tuning in the future.
Other model results will coming soon.

## Performance metrics
* Mean Absolute error (MAE)
* Root Mean Squared error(RMSE)
