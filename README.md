# Capital Bikeshare - Visualizing and Predicting Ridership

My project involves 
* building a machine learning model to predict Capital Bikeshare ridership in Washington, DC
* making choropleth maps that illustrate ridership by neighborhood in any given hour since 2015
* building a map that recommends zones for dynamic pricing in real time

Please take a look at the slides that summarize this project and include some interesting graphs [here](https://github.com/josephimathias/Cap_Bikeshare_Project/blob/master/slides.pdf). To make historical choropleths and view the dynamic pricing map, click [here](https://obscure-garden-58632.herokuapp.com).

<p align="center">
  <img src=![alt text](https://github.com/josephimathias/Cap_Bikeshare_Project/blob/master/images/model_gif.gif)>
</p>

![alt text](https://github.com/josephimathias/Cap_Bikeshare_Project/blob/master/images/model_gif.gif)



![alt text](https://github.com/josephimathias/Cap_Bikeshare_Project/blob/master/images/dynamic_pricing_gif.gif)

## Process

#### 1. Collect data

This project includes
* 25 millions rows of trip data downloaded from [Capital Bikeshare](https://www.capitalbikeshare.com/system-data).
* Three weeks of bike station statuses, pulled from Capital Bikeshare's API every 15 minutes using AWS Lambda.
* 10 years of weather data from the [National Oceanic and Atmospheric Administration](https://www.noaa.gov).
* Geographic shapes for building maps taken from [Open Data DC](https://opendata.dc.gov), the DC Government's data sharing website. 

#### 2. Process data

Processing this data included
* Joining trip data and station data
* Creating neighborhood "shapes" and determining trip starting locations by placing geographic coordinates within those shapes
* Syncing weather data and trip data across time
* Converting hours and months into circular features (as opposed to categorical or linear features)

#### 3. Build models and tune hyperparameters

I tested many classifiers and ultimately used random forest. After hyperparameter tuning through grid search, my random forest classifier achieves an r^2 score of **89%**.

#### 4. Build maps

I built two types of maps:
* one to view trends over time
<p align="center">
  <img src=![alt text](https://github.com/josephimathias/Cap_Bikeshare_Project/blob/master/images/model_gif.gif)>
</p>
* the other to propose a solution to a business problem facing Capital Bikeshare
<p align="center">
  <img src=![alt text](https://github.com/josephimathias/Cap_Bikeshare_Project/blob/master/images/dynamic_pricing_gif.gif))>
</p>

As I mentioned above, they can be tested [here](https://obscure-garden-58632.herokuapp.com). 
