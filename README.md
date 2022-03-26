# PyBer_Analysis
## Project Overview
PyBer, a rideshare company, has asked for visualizations of all rideshare data from January to May 2019 to help with plans to improve access to ride-sharing services and determine affordability for underserved neighborhoods. 
### Purpose
After analyzing all data, it is requested that a new analysis be done to create a summary of the ride-sharing data by city type and to produce a multiple-line graph that shows the total weekly fares for each city type. Along with a summary of findings and how the data differs by city type, PyBer will use the results to make decisions about their services.  
## Resources
* Data Source: schools_complete.csv, students_complete.csv
* Software: Python 3.7.11
## Results
### Summary Dataframe
After running analysis on the Pyber data by city type using the groupby function to create the summary Dataframe below, it could be seen that: 
* The number of total rides and total number of drivers was highest in Urban cities, with total rides in Rural cities being the lowest
* The total fares were highest in Urban cities, with the lowest total fares in Rural cities and Suburban total fares in between
* The average fare per ride and the average fare per driver was highest in the Rural cities and lowest in the Urban cities
![Summary by CIty Type](https://user-images.githubusercontent.com/99205688/160250521-17711943-73f7-4076-bf46-318f1a9b58a7.PNG)
### Multiple Line Plot showing Total Fare by City type
To analyze the data by total weekly fares, a new dataframe was created using the groupby function to show the sum of the fares for each date with the indices being city type and date

 ![Dataframe group by city type and date](https://user-images.githubusercontent.com/99205688/160250803-f59357f9-1764-4560-8f37-004164cb4618.PNG)

The index was then reset and the pivot function was used to get total fares for each city type by date. Then the loc function was used to create a new DataFrame for the given dates from January 1 to April 29.

![Pivot Loc](https://user-images.githubusercontent.com/99205688/160250861-4f6b621a-a8d0-4299-bd2c-799a6e603d2c.PNG)

After setting the date index to a datetime datatype, a new DataFrame was created with the resample function to organize the data by the sum of fares for each week
![Resample](https://user-images.githubusercontent.com/99205688/160250957-0e26e27a-9e6b-419f-9d7c-147a5c0c12d6.PNG)
A multiple line chart was then created to produce a summary of the total fares by city over time:

![PyBer_fare_summary](https://user-images.githubusercontent.com/99205688/160251013-cf5d78c5-6dd2-482f-938f-3ebafbb143cd.png)

The chart shows that the total fares by city type were highest in Urban cities. All city types saw fares hit a peak in late February, with total fares being relatively stable until a slight decline in Urban and Rural areas in late April, and an increase in mid-to late April in Suburban areas. 

## Summary
Based on the analysis, three business recommendations to the CEO for addressing any disparities among the city types are:
* Given that Rural cities have the highest average fare per ride total and lowest number of drivers, it is most likely that Rural city drivers drive the furthest distances and have the least competition. Increasing drivers in Rural cities would improve accessibility for riders by increasing competition. 
* Deploy additional drivers in the Suburban cities in April when Suburban cities saw an uptick in total fares, but both Urban and Rural cities saw a decline in total fares.
* Total drivers in Urban cities outnumber the total rides. Reducing density and restributing drivers into Suburban and Rural areas would help with decreasing the average fare per ride in those cities which would increase affordability.
