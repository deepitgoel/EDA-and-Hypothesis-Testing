# EDA-and-Hypothesis-Testing
Performing Data Analysis for a well known electric cycle rental startup to find out: 
 - Which variables are significant in predicting the demand for shared electric cycles in the Indian market?
 - How well those variables describe the electric cycle demands
We will be using different hypothesis tests to find the significance of different features that effect the demand.

## Basic Observations from Data 
- SHAPE: There are 12 columns and 10886 rows in the dataset
- Data types : datetime column converted to datetime data type. Season, holiday, working day, weather are categorical features and rest are continuous. count is the target variable (dependent) and all others are independent.
- Missing Values : There are no null values in our dataset

## General Insights
 - We have almost same count of datapoints for all 4 seasons
 - We observe majority (66%) of bookings are in weather category 1 - Clear, Few clouds, partly cloudy, partly cloudy
 - 97 % of bookings are made on non holiday days.
 - 68% of bokings are on a working day and 32% on non-working days.
 - For most bookings done temperature is around 14-15 degree celcius and median temp is around 20 degree celcius. 
 - For most bookings done feeling temperature is around 22-26 degree celcius with median at 25
 - For most bookings done occuring windspeeds are between 5-15 with many outliers being present.


## Relation between Features and Count:

- Working day: 
    - The mean count of rental bikes for working and non working days is almost same with slightly higer for working day
 -- The max and median count for working day is greater as compared to the non working day

- Holiday: 
 -- The mean and median count of rental bikes for holidya and non-holidays is almost same with slightly higher for non holiday.

- Season:
 -- The mean and median of count of rentals is highest in season 3 - fall and lowest in season 1 - spring.

- Weather :
 -- the mean and median of count of rentals is highest during weather category 1 and least in category 3

- Temperature and feeling temperature:
 -- The highest count of rentals is between 31-36 degree celcius while the highest frequency (density) is between 8-17 degrees and count of rentals around 100.
 -- we see as temp increases there is an increase in the count of rentals

 -- The highest count of rentals is between 36-40 degree Celsius feeling temperature while the highest frequency (density) is between 12-16 degrees and count of rentals around 100.
 -- We see as feeling temp increases there is an increase in the count of rentals.

- Humidity:
 -- The count of rentals is very low for humidity less than 18 but is maximum at 20.
 -- After humidity level 20 the count of rentals decreases as humidity increases

- Windspeed :
 -- the count is maximum between windspeed of 12-30 approx.
 -- above windspeeds of 35 we can observe a decrease in the count of rentals

## Results from significance testing



