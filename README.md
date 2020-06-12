# PyBer_Analysis
## Backgound and Purpose
Analyse the PyBer ride sahring data using PAndas and matplotlib to viualize the analysis, inferfrom the data and
make recommendation.Creating visualizations of rideshare data for PyBer to help improve access to ride-sharing services 
and determine affordability for underserved neighborhoods.
**Module exercises**
1. Rural area , average fare per ride is higher than suburban and suburban is higher than urban
2. A expected the number of rides in rural is much less than suburban , which is less than rural
3. Whisker plot shows an outlier for urban number of rides and suburban/rural are within range.
4. Whisker of Fares by City Type shows that the fares under ditribution with no outliers and similar to (1) outcome,

## Challenge
### Purpose
creating a summary DataFrame of the key metrics for the ride-sharing data by city type; 
creating a multiple-line graph that shows the total fares for each week by each city type and future recommendation
**A : 1st**
### Technical Analysis
Analyze the PyBer rides to compute the Fare data by week and breakdown it by city type.
   - Filtered the dataframe with relevant columns of interest
   {'city':'City', 'date':'Date','fare':'Fare', 'ride_id': 'Ride Id','driver_count': 'No. Drivers', 'type':'City Type'}
   - Pivoted the dataframe. Row - ride. Columns - city type. Filtered for fare. 
   - Index is Date, and this was converted to DateTimeIndex with pandas pd.DateTimeIndex.
   - Filtered the resulting frame for the period ['2019-01-01':'2019-04-28'] using loc on index.
   - Used resample with W for week by week analysis
   - Plotted using matplotlib line plots for all the city types.
   - Also used mdates to set xaxis major locator to months. (mdates.Monthlocator())
### Results
*Weekly Fare Dataframe by City Type*

|City Type  |**Rural**|**Suburban**|**Urban**|
|-----------|-------|--------|-------|
|**Date**			
|2019-01-06|187.92|721.60|1661.68
|2019-01-13|67.65|1105.13|2050.43
|2019-01-20|306.00|1218.20|1939.02
|2019-01-27|179.69|1203.28|2129.51
|2019-02-03|333.08|1042.79|2086.94
|2019-02-10|115.80|974.34|2162.64
|2019-02-17|95.82|1045.50|2235.07
|2019-02-24|419.06|1412.74|2466.29
|2019-03-03|175.14|858.46|2218.20
|2019-03-10|303.94|925.27|2470.93
|2019-03-17|163.39|906.20|2044.42
|2019-03-24|189.76|1122.20|2368.37
|2019-03-31|199.42|1045.06|1942.77
|2019-04-07|501.24|1010.73|2356.70
|2019-04-14|269.79|784.82|2390.72
|2019-04-21|214.14|1149.27|2303.80
|2019-04-28|191.85|1357.75|2238.29  
 
Fare Data by week plot is in the Analysis folder FareData_Month.png
![](/analysis/FareDate_Month.png)
### Summary
Fares from Urban  > Fars from Suburban > Fares from Rural for all weeks. 
   -Also Urban is approximately twice Surburban and Suburban is 3 to 10 times Rural. The swings are similar till 
   the month of April, when we see an upward trend in Surburban and levelling off /slight decline for both Urban and Rural
   -There is spike for all three in late feburary. Urban sees a few weekly swings in the month of March


**B : 2nd**
## Challenges Encountered and Overcome
1. Need to get the date to datetime format. It looks like datetime initially, but internally  it has to converted.
   For resample (grouping by weeks, months etc) , datetime fromat is necessary.
   Pivoting to get the city type and fare was not vry clear at first. But it made the work a lot easier. 
   Alternatively, could have sorted ans summed by city type. A little bit longer.  X-axis ticks.
2. Google to find out solutions for monthlocator etc and to set major_locator to months.

**C : 3rd**
## Recommendations and Next Steps
1. Urban city type is an important major revenue generator and recommend expanding to get additional revenues, 
   though the fare per ride is less than the others
2. Surburban is showing a growing trend, and can add more revenue and increase the average fare per pride, recommend additional analysis
3. Rural is consistent and provides high fare per ride, recommend maintain current level of activity
### Additional Analysis 1
1. Rides by city type and by driver count. It may  highlight the shortages of drivers and certain city type/cities
2. Also may be worthwhile to do analysis by weekday/weekend and also by time periods in the day to get ride_count by city type and weekday/weekend, 
   and ride_count by time of th e day ( like 7-9, 11-1, 4-6 etc).
### Addional Analysis 2
1. Time stamp is available in the current data set.That could be used for time group analysis. Also weekday / weekend could be determined with 
   current date input for weekda/weekend analysis.