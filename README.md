# Air-pollution-forecast-for-Krakow-districts
Air pollution forecast from kaggle data for 2017 for the next year in the period from June to September


The city of Krakow organizes a series of summer outdoor cultural events every year. One of the biggest problems of the city is one of the highest levels of pollution in Europe. How to reconcile spending time outside the home and taking care of your health? The purpose of the poroject was to create a model predicting the pollution index values based on the forecasted atmospheric factors for a given district. The product was to be an application that, after the user uploads data containing the days of the event, district number and forecast temperature, pressure and humidity, will return the district with the lowest predicted air pollution index.

The project uses data from kaagle:
https://www.kaggle.com/datasets/datascienceairly/air-quality-data-from-extensive-network-of-sensors

- .csv files containing observations from sensors (temperature, pressure, humidity, indicators PM25, PM10, PM1) collected every hour during 2017

- a file with the sensor's ID and its X and Y coordinates

![image](https://user-images.githubusercontent.com/94246903/181913777-92eda115-9e2e-4acf-a0dc-6fccf7e65f3a.png)


The following steps were performed:

1. An analysis of features was performed and a selection of features for prediction was performed
2. Data gaps were supplemented, cleaned and the original table was transformed
3. The mutual correlations of the features were checked
4. Prepared data for processing by the model (standardization / one hot encoder)
5. Several models were made (Decision tree, random forest, polynomial regression) and the metrics and evaluation charts were checked
6. The most favorable model was selected and saved


The code for the proposed "application" is stored in a separate file, which loads the model, data provided by the user and selects the district with the lowest pollution on a given day based on the forecasts.


The output data sets, a file with a saved model, and a test table uploaded to the application by the user are attached to the repository.
