# Wind Energy Power Prediction 🌬🍃

This is a web application that shows the estimated wind energy that could be generated from the parameters like wind speed,wind direction and time of the day. The time series in the web app will monitor the estimated power generation for a time wind speed, wind direction. The training of the model will be done with Wind Turbine Scada Dataset 2018. The attributes in the dataset are [Date/Time, LV ActivePower (kW), Wind Speed (m/s), Theoretical_Power_Curve (KWh), Wind Direction (°)].User can use the time series of the web app to fetch the prime hours of production and hence can coordinate with the collaborators.

## Getting Started

A live demo of the project could be viewed from the link:

[**My P-Wind App**](https://immense-reef-43943.herokuapp.com/)

### Prerequisites

* Node-RED
* IBM Watson Studio
* Watson Machine Learning
* Open Weather API
* [Wind Turbine Scada Dataset 2018](https://www.kaggle.com/berkerisen/wind-turbine-scada-dataset)


### Installing

To get the application up and running follow the below steps:

* In the nodered flow import the flows present in the NodeRED flows folder.
* Create a notebook in Watson Studio and import the notebook present under Notebooks/Notebooks/finalNotebook1.ipynb.
* Create a Machine Learning instance in your IBM Cloud services.
* Deploy the model using WatsonMachineLearningAPI with the service credentials of Watson Machine Learning instance.
* Create a scoring_url and store it somewhere.
* Use the OpenWeatherAPI for getting the wind speeds and wind directions.
* In the flow in the "http" nodes modify it with your own credentials and in the last "http" node conected to Pre-Predictions paste the scoring_url.
* Deploy the flow and go to Dashboard UI to see the final model.

![alt text](https://i.ibb.co/sH6t26c/2-Current-Pred.png)

## Running the tests

On the landing page of the app(see above), you can click on refresh to fetch the current wind speed and directions and pass it onto the model to make predictions for those parameters. 

If we click on the sidebar to go to Power vs Wind group we'll see a time series like this:

![alt text](https://i.ibb.co/N6cRtHw/3-Current-Pred.png)

Here we fetch data(speed and direction) for next 4 days at an interval of 3-3 hours and plot it in the time series. 


To see the optimal power generation time simply click on REFRESH and it notifies us with the optimal time to produce power.

![alt text](https://i.ibb.co/YfJS0fv/4-Current-Pred.png)


## Deployment

To deploy this app we just need to link the Dashboard UI address.

## Built With

* [Node-RED](https://nodered.org/docs/) - Developing the dashboard
* HTML/CSS/JavaScript - Creating the webpage
* [IBM Watson Studio](https://cloud.ibm.com/catalog/services/watson-studio) - Used to create notebook
* [Open Weather API](https://openweathermap.org/api) - For fetching current wind speed and directions

## Authors

* **Jashmin Mishra** - [Jashmin](https://github.com/jashminmishra1 )
* **Gurudeep Singh** - [Gurudeep](https://github.com/gudii16 )
* **Aman Kumar** - [Aman](https://github.com/bullet-ant)

## License

This project is licensed under the MIT License