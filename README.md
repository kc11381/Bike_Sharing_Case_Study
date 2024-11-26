# Bike Sharing predictors analysis case study
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

    1. Which variables are significant in predicting the demand for shared bikes.
    2. How well those variables describe the bike demands


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
A US based bike-sharing system wants to know
    1. Which variables are significant in predicting the demand for shared bikes.
    2. How well those variables describe the bike demands
- We need to find the predictors and their effect for count(total bike shared) so that company can take an informed decision.
  A linear regression model is used here.
- Dataset - Bike sharing dataset is used. 

  - It is provided by upgrad(day.csv)
  =========================================
    Dataset characteristics
  =========================================	
    day.csv have the following fields:
	
	- instant: record index
	- dteday : date
	- season : season (1:spring, 2:summer, 3:fall, 4:winter)
	- yr : year (0: 2018, 1:2019)
	- mnth : month ( 1 to 12)
	- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
	- weekday : day of the week
	- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
	+ weathersit : 
		- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
		- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
		- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
		- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
	- temp : temperature in Celsius
	- atemp: feeling temperature in Celsius
	- hum: humidity
	- windspeed: wind speed
	- casual: count of casual users
	- registered: count of registered users
	- cnt: count of total rental bikes including both casual and registered

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Technologies Used
- python - 3.10.11
- numpy - 1.26.4
- pandas - 2.2.1
- matplotlib - 3.9.1
- seaborn - 0.13.2
- sklearn - 1.2.2
- statsmodels - 0.14.4

## Conclusions
- We have variables like temp which is lineraly related to cnt. So linear regression makes sense here.
- Predictors for cnt and their coefficients are
    yr            0.2348
    workingday    0.0547
    temp          0.4354
    windspeed    -0.1609
    spring       -0.0713
    summer        0.0354
    winter        0.0903
    dec          -0.0467
    jan          -0.0526
    july         -0.0466
    nov          -0.0447
    sep           0.0652
    sat           0.0670
    Light_Snow   -0.2969
    Misty        -0.0818

- Equation of the model is

cnt = 0.2348yr + 0.0547workingday + 0.4354temp - 0.1609windspeed - 0.0713spring + 0.0354summer + 0.0903winter - 0.0467dec - 0.0526jan - 0.0466july - 0.0447nov + 0.0652sep + 0.0670sat - 0.2969Light_Snow - 0.0818Misty

- There is a significant rise in count(cnt) from 2018 (0) to 1 (2019).
- There is a drastic drop in count(cnt) in the month of Dec and Nov.
- When wheather is clear then count(cnt) is higher and when its Light and snow its drastically low.
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Acknowledgements
Give credit here.
- This project was inspired by Linear Regression Model learning at Upgrade as part of AI/ML course.
- This project was based on [this tutorial](https://learn.upgrad.com/course/5810/segment/56042/334812/1013171/5064649).


## Contact
Created by [@kc11381] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
