# Air-pollution-forecast-for-Krakow-districts
Air pollution forecast from kaggle data for 2017 for the next year in the period from June to September


The city of Krakow organizes a series of summer outdoor cultural events every year. One of the biggest problems of the city is one of the highest levels of pollution in Europe. How to reconcile spending time outside the home and taking care of your health? The purpose of the poroject was to create a model predicting the pollution index values based on the forecasted atmospheric factors for a given district. The product was to be an application that, after the user uploads data containing the days of the event, district number and forecast temperature, pressure and humidity, will return the district with the lowest predicted air pollution index.

The project uses data from kaagle:
https://www.kaggle.com/datasets/datascienceairly/air-quality-data-from-extensive-network-of-sensors

- .csv files containing observations from sensors (temperature, pressure, humidity, indicators PM25, PM10, PM1) collected every hour during 2017

- a file with the sensor's ID and its X and Y coordinates


## Step one: define your goals

![image](https://user-images.githubusercontent.com/94246903/181913777-92eda115-9e2e-4acf-a0dc-6fccf7e65f3a.png)

## Step two: Understand the data

This was an important step that focused on cleaning up the data, finding out which factor would be used to determine the contamination, and how the others affected it.

![image](https://user-images.githubusercontent.com/94246903/181914213-887264ec-4362-44c6-a1a2-0652572f07a9.png)

For this project, it was decided that the target for prediction would be the PM10 indicator, for which the correlation between the features was checked.

![image](https://user-images.githubusercontent.com/94246903/181914185-a09b46c9-e092-4014-8c73-5812ec21b614.png)

## Step three: breakdown of data into districts of Krakow

Since the problem is to determine the data in the districts, the measurement sensors were presented on the map and then the data was argregated to the districts.

![image](https://user-images.githubusercontent.com/94246903/181914275-44981f03-75fc-4187-b738-5341960aa2ee.png)

## Step four: Split the data into test and training sets
An important element when dividing a set is to take into account changes in parameters over time. A ready-made function was not used for the separation, but the operation was performed manually by allocating the training set of data from March to October, and the training set - data from October to December.

![image](https://user-images.githubusercontent.com/94246903/181915239-5a3b025a-e4fa-4def-a423-fbc78094f062.png)

## Step five: preparation of models and their evaluation

A basic tree model was created for the predictions. However, it did not give good results, so the data was enriched with the days of the week. On the basis of the new sets, subsequent models were made: tree, random forest and polynomial regression. Regression gave the best results in this comparison.
![image](https://user-images.githubusercontent.com/94246903/181915759-23c5bd4a-ca3a-42ec-b91a-a1eb25ccff5e.png)


The following steps were performed:

1. An analysis of features was performed and a selection of features for prediction was performed
2. Data gaps were supplemented, cleaned and the original table was transformed
3. The mutual correlations of the features were checked
4. Prepared data for processing by the model (standardization / one hot encoder)
5. Several models were made (Decision tree, random forest, polynomial regression) and the metrics and evaluation charts were checked
6. The most favorable model was selected and saved


The code for the proposed "application" is stored in a separate file, which loads the model, data provided by the user and selects the district with the lowest pollution on a given day based on the forecasts.

Design development ideas
The models have not yet produced satisfactory results, however the design can be expanded by taking into account the location of the space measurement points. For a better understanding, it would be important to create a heat map that would show how the PM10 values are distributed in space and if there is any relationship. A good idea for refining the design would be to create a user application with an interface.

![image](https://user-images.githubusercontent.com/94246903/181916539-923b0e69-81b4-40b9-8d8a-3b4e1f1cbbde.png)


The output data sets, a file with a saved model, and a test table uploaded to the application by the user are attached to the repository.
