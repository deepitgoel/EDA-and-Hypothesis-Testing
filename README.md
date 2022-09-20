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
    - The max and median count for working day is greater as compared to the non working day

- Holiday: 
    - The mean and median count of rental bikes for holidya and non-holidays is almost same with slightly higher for non holiday.

- Season:
    - The mean and median of count of rentals is highest in season 3 - fall and lowest in season 1 - spring.

- Weather :
    - the mean and median of count of rentals is highest during weather category 1 and least in category 3

- Temperature and feeling temperature:
    - The highest count of rentals is between 31-36 degree celcius while the highest frequency (density) is between 8-17 degrees and count of rentals around 100.
    - we see as temp increases there is an increase in the count of rentals

    - The highest count of rentals is between 36-40 degree Celsius feeling temperature while the highest frequency (density) is between 12-16 degrees and count of rentals around 100.
    - We see as feeling temp increases there is an increase in the count of rentals.

- Humidity:
    - The count of rentals is very low for humidity less than 18 but is maximum at 20.
    - After humidity level 20 the count of rentals decreases as humidity increases

- Windspeed :
    - the count is maximum between windspeed of 12-30 approx.
    - above windspeeds of 35 we can observe a decrease in the count of rentals

## Results from significance testing
### Workday with Count of rentals
    - **Null Hypothesis Ho** : The means of count of non working day and working day are equal.
    - **Alternate Hypothesis Ha**: The means of count of non working day and working day are not equal.
    - **Significance level** = 5% = 0.05
    - To test our null hypothesis we will use the **2-sample t test** as population standard deviations are not present.
    - Results:
       - P-value= 0.22607559007082925
       - P-value is greater than the significance level ,therefore we fail to reject the null hypothesis. 
       - **we conclude that the means of count of rentals on working and non-working days are equal and thus working day feature doesnot affect the count**
       
### Weather with Count of rentals:
    - **Null Hypothesis Ho** : There is no difference between means of count of rentals of different weather groups.
    - **Alternate Hypothesis Ha**: There is some difference between means of count of rentals of different weather groups
    - **Significance level** = 5% = 0.05
    - To test our null hypothesis we will use the **ANOVA** as we need to compare means of multiple groups.
    - Results:
        - We can observe that none of the count of rentals for a weather group is normally distributed. Also, the variance is not same.
        - Both log-transform and boxcox transform failed to transform count of rentals for each weather group to Gaussian.
        - Since both requirements are not fulfilled we cannont use Anova. Therefore we cannot test our null hypothesis.
    - Therefore we will use the **non parametric equivalent** of Anova , that is, **Kruskal-Wallis Test** to test the null hypothesis.
    - Results :
        - P -value = 1.572144018491876e-147 ~ 0
        - P-value is very less than the significance level, therefore we reject the null hypothesis.
        - **We conclude that There is some difference between means of count of rentals of different weather groups.**
        
### Dependence of Weather on Season
    - **Null Hypothesis Ho** : Season has no effect on Weather
    - **Alternate Hypothesis Ha**: Season has some effect on Weather
    - **Significance level** = 5% = 0.05
    - To check the dependence we can use **chi-squared test** since both feature are categorical
    - Results:
        - P-value= 2.8260014509929403e-08 = 2.8 * 10^(-8)
        - P-value is much less than the significance level, therefore we reject the null hypothesis. 
        - We conclude that Weather is dependent on Season.





