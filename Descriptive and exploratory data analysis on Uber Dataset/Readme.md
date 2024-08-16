# Uber Rides Analysis in New York City (April-September 2014)

## Table of Contents
1. [Introduction](#introduction)
2. [Data Preparation](#data-preparation)
3. [Temporal Analysis](#temporal-analysis)
   3.1 [Hourly Analysis](#hourly-analysis)
   3.2 [Daily Analysis](#daily-analysis)
   3.3 [Monthly Analysis](#monthly-analysis)
   3.4 [Day of Week Analysis](#day-of-week-analysis)
4. [Base Analysis](#base-analysis)
5. [Heat Map Visualizations](#heat-map-visualizations)
6. [Geospatial Analysis](#geospatial-analysis)
7. [Conclusion](#conclusion)

## 1. Introduction <a name="introduction"></a>

This report presents an in-depth analysis of Uber ride data in New York City from April to September 2014. The analysis explores various temporal and spatial patterns in ride frequency, providing insights into usage trends across different time scales and geographical areas. Understanding these patterns can help optimize service delivery, inform marketing strategies, and improve overall user experience.

## 2. Data Preparation <a name="data-preparation"></a>

The analysis began with loading and preprocessing data from six CSV files, each representing a month from April to September 2014. Key steps included:

- Combining monthly data into a single dataset (`data_2014`)
- Parsing and formatting date and time information using `lubridate` functions
- Creating new columns for day, month, year, day of the week, hour, minute, and second
- Ensuring proper data types for each column to facilitate analysis

This preparatory step was crucial for enabling the subsequent detailed temporal and spatial analyses.

## 3. Temporal Analysis <a name="temporal-analysis"></a>

### 3.1 Hourly Analysis <a name="hourly-analysis"></a>

We analyzed the distribution of rides across different hours of the day.
![Trips Every Hour](https://github.com/user-attachments/assets/1a60ed39-10f4-45d7-8815-aa122dd288ca)

*Figure 1: Distribution of trips across 24 hours*
This bar chart shows the number of Uber trips taken during each hour of the day. The x-axis represents the 24 hours of a day, while the y-axis shows the total number of trips. Key observations:

1. Peak hours are clearly visible, with the highest number of trips occurring around 6 PM (18:00).
2. There's another significant peak in the morning, around 8 AM (08:00).
3. The lowest number of trips occurs in the early morning hours, between 3 AM and 5 AM.
4. Trip volume gradually increases from early morning, peaks in the evening, and then declines into the night.

We also examined how hourly patterns changed across different months.

![Trips by Hour and Month](https://github.com/user-attachments/assets/b400a4bb-2b68-4e7a-903a-311564e5bca9)

*Figure 2: Hourly trip distribution by month*
This image shows a stacked bar chart titled "Trips by Hour and Month".

The chart displays the total number of trips taken across different hours of the day (0-23 on the x-axis) and months (represented by different colors in the legend).

1. The y-axis represents the total number of trips, ranging from 0 to about 350,000.

2. Each bar is divided into colored segments representing different months from April to September, with an additional "NA" category.

3. Trip volumes are lowest in the early morning hours (around 2-5 AM) and highest in the late afternoon/evening hours (around 4-7 PM).

4. The busiest months appear to be July and August, represented by the green colors which occupy large portions of the bars during peak hours.

5. There's a clear daily pattern with trip volumes increasing throughout the day, peaking in the evening, and then declining into the night.

6. Weekday commute patterns are visible, with noticeable peaks during morning and evening rush hours.

7. The "NA" category is minimal, suggesting most data points have been successfully categorized by month.

This visualization effectively shows both the daily cycle of trip patterns and how these patterns vary across different months of the year, likely reflecting seasonal changes in travel behavior.
### 3.2 Daily Analysis <a name="daily-analysis"></a>
*Figure 3: Trip frequency by day of the month*  
![Trips Every Day](https://github.com/user-attachments/assets/2ce292c3-184b-485c-a770-277e5d64b12e)
This bar chart shows the total number of trips taken on each day of a month, titled "Trips Every Day". Here are the key observations:

1. The x-axis represents the days of the month, from 1 to 31, plus an "NA" category.

2. The y-axis shows the total number of trips, ranging from 0 to about 175,000.

3. Most days see between 125,000 and 170,000 trips.

4. There's some variation in trip numbers from day to day, but no clear weekly pattern is immediately apparent.

5. The highest number of trips occurs on day 30, with just over 175,000 trips.

6. The lowest number of trips (excluding NA) is on day 1, with about 125,000 trips.

7. There's a very small bar for the "NA" category, suggesting there are some trips that couldn't be assigned to a specific day.

8. Days 31 and NA have noticeably fewer trips than other days, likely because not all months have 31 days.

9. There's no clear trend of increasing or decreasing trip numbers as the month progresses.

This visualization provides a good overview of daily trip patterns throughout a month, showing that while there is some day-to-day variation, the number of trips remains relatively consistent most days.

We investigated how ride frequency varied across days of the month and across different months.
![Trips by Day and Month](https://github.com/user-attachments/assets/cee7ee90-466a-427e-a462-e73f400726ed)
This stacked bar chart titled "Trips by Day and Month" displays the number of trips taken each day, broken down by month. Here are the key observations:

1. The x-axis represents days of the month (1-31) plus an "NA" category.
2. The y-axis shows the total number of trips, ranging from 0 to about 175,000.
3. Each bar is divided into colored segments representing different months from April to September, with an additional "NA" category.
4. July and August (yellow and light gray) consistently have the highest number of trips across most days.
5. April (red) and May (dark gray) generally have fewer trips compared to the summer months.
6. September (blue) appears to have the lowest number of trips among the full months shown.
7. There's variation in trip numbers from day to day, but no clear weekly pattern is immediately apparent.
8. The 31st day and the "NA" category have noticeably fewer trips, likely because not all months have 31 days.
9. The total number of trips per day is relatively consistent throughout the month, with most days seeing between 125,000 and 170,000 trips.
10. There's no clear trend of increasing or decreasing trip numbers as the months progress.

This visualization effectively shows both the daily patterns of trips and how these patterns vary across different months, likely reflecting seasonal changes in travel behavior.

*Figure 4: Daily trip patterns across months*
![pic 5](https://github.com/user-attachments/assets/01e13536-3fd1-4380-adf4-3bd96b90adde)

This bar chart titled "Trips by Month" shows the total number of trips taken in each month from April to September, with an additional "NA" category. Here are the key observations:

1. The x-axis represents the months from April to September, plus an "NA" category.
2. The y-axis shows the total number of trips, ranging from 0 to over 1,000,000.
3. There's a clear increasing trend in the number of trips from April to September.
4. September has the highest number of trips, exceeding 1,000,000.
5. April has the lowest number of trips among the full months, at around 500,000.
6. The number of trips increases steadily each month from April to August.
7. There's a significant jump in trips from August to September.
8. The "NA" category has a very small number of trips compared to the other months.
9. The summer months (June, July, August) show higher trip numbers compared to the spring months (April, May).
10. The difference in trip numbers between the lowest month (April) and the highest month (September) is substantial, with September having about twice as many trips as April.

This visualization effectively illustrates the seasonal variation in trip numbers, with a clear trend towards more trips as the months progress from spring to summer and early fall.

### 3.3 Monthly Analysis <a name="monthly-analysis"></a>

We examined the overall trend in ride volume across the six months.

![pic 6](https://github.com/user-attachments/assets/d283f30d-f972-4bd2-b5b0-9c7d6044b132)


*Figure 5: Monthly distribution of trips*

Observations:
- There's a clear upward trend in ride volume from April to September.
- The largest increase appears to be between May and June.
- September has the highest number of rides, possibly due to a combination of good weather and increased business activity after summer vacations.

### 3.4 Day of Week Analysis <a name="day-of-week-analysis"></a>

We analyzed how ride patterns differed across days of the week and how these patterns changed from month to month.

![Trips by Day and Month]()
![pic 7](https://github.com/user-attachments/assets/fc3cf9b6-4448-4752-adca-0cd4c4b8c19f)

*Figure 6: Trip patterns by day of week and month*

Observations:
- Fridays and Saturdays consistently show the highest ride volumes across all months.
- Sundays and Mondays tend to have the lowest ride volumes.
- The difference between weekday and weekend ride volumes becomes more pronounced in the summer months.

## 4. Base Analysis <a name="base-analysis"></a>

We investigated the distribution of rides across different Uber bases and how base usage varied over time.

![Trips by Bases]()

*Figure 7: Distribution of trips across Uber bases*

![Trips by Bases and Month]()

*Figure 8: Base usage patterns by month*

![Trips by Bases and DayofWeek]()

*Figure 9: Base usage patterns by day of week*

Observations:
- Base B02617 handles the highest number of rides, followed by B02598.
- The relative usage of bases remains fairly consistent across months, with all bases showing the general upward trend from April to September.
- Some bases show more pronounced weekend spikes than others, suggesting they might be located closer to entertainment districts.

## 5. Heat Map Visualizations <a name="heat-map-visualizations"></a>

We created several heat maps to visualize complex patterns in the data:

![Heat Map by Hour and Day]()

*Figure 10: Heat map of trips by hour and day*

![Heat Map by Month and Day]()

*Figure 11: Heat map of trips by month and day*

![Heat Map by Month and Day of Week]()

*Figure 12: Heat map of trips by month and day of week*

![Heat Map by Month and Bases]()

*Figure 13: Heat map of trips by month and base*

![Heat Map by Bases and Day of Week]()

*Figure 14: Heat map of trips by base and day of week*

Observations:
- The hour-day heat map clearly shows the daily rush hour patterns.
- The month-day heat map reveals an overall increase in intensity (ride volume) as months progress.
- The month-day of week heat map shows that Friday and Saturday intensities increase more dramatically in summer months.
- The month-base heat map confirms that all bases see increased activity in later months.
- The base-day of week heat map shows that some bases have more pronounced day-of-week patterns than others.

## 6. Geospatial Analysis <a name="geospatial-analysis"></a>

We mapped the geographical distribution of Uber rides in NYC.

![NYC MAP BASED ON UBER RIDES DURING 2014 (APR-SEP)]()

*Figure 15: Geographical distribution of all Uber rides*

![NYC MAP BASED ON UBER RIDES DURING 2014 (APR-SEP) by BASE]()

*Figure 16: Geographical distribution of Uber rides by base*

Observations:
- Ride density is highest in Manhattan, particularly in Midtown and Lower Manhattan.
- There are also high concentrations of rides in parts of Brooklyn and Queens, likely in popular commercial or residential areas.
- Each base seems to have a primary area of operation, though there is significant overlap.
- Some bases appear to specialize in airport rides, as indicated by concentrations near JFK and LaGuardia airports.

## 7. Conclusion <a name="conclusion"></a>

This analysis of Uber ride data in New York City from April to September 2014 reveals several key insights:

1. Temporal Patterns: Clear daily patterns with morning and evening rush hour peaks, weekly patterns with higher weekend usage, and a monthly trend of increasing ride volumes from spring to late summer.

2. Seasonal Effects: Summer months see higher ride volumes, particularly in evening hours and weekends, likely due to increased tourism and outdoor activities.

3. Base Operations: While some bases handle significantly more rides than others, all follow similar temporal patterns and saw growth over the analyzed period.

4. Geographical Concentrations: Rides are heavily concentrated in Manhattan, with secondary hotspots in parts of Brooklyn, Queens, and around airports.

These findings can inform strategic decisions such as:
- Adjusting driver availability to match hourly and weekly demand patterns
- Tailoring marketing efforts to capitalize on seasonal trends
- Optimizing base operations and coverage areas
- Focusing expansion efforts on high-demand areas and times

Future analyses could benefit from incorporating additional data such as weather conditions, local events, and broader transportation trends to provide even deeper insights into ride-sharing patterns in New York City.
