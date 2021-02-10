# sqlalchemy-challenge

# SQLAlchemy Homework - Surfs Up!

To help with your trip planning, you need to do some climate analysis on the area. The following outlines what you need to do.

## Step 1 - Climate Analysis and Exploration

Python and SQLAlchemy was used to do basic climate analysis and data exploration of your climate database. All of the following analysis was completed using SQLAlchemy ORM queries, Pandas, and Matplotlib.

### Precipitation Analysis: The following are the steps completed.

* Design a query to retrieve the last 12 months of precipitation data.

* Select only the `date` and `prcp` values.

* Load the query results into a Pandas DataFrame and set the index to the date column.

* Sort the DataFrame values by `date`.
![DF](Images/precip_aug_2016_17.png)

* Plot the results using the DataFrame `plot` method.

![precipitation](Images/1_aug_precip.png)

* Use Pandas to print the summary statistics for the precipitation data.
![sumstats](Images/sum_stats_precip.png)

### Station Analysis

* Design a query to calculate the total number of stations.

* Design a query to find the most active stations.

  * List the stations and observation counts in descending order.
  ![activestations](Images/most_active_stations.png)

  * Which station has the highest number of observations?  Calculate the highest, lowest and average observations, functions `func.min`, `func.max`, `func.avg`, and `func.count` were used in the queries.
  ![mostactive](Images/low_high_av_station_high.png)

* Design a query to retrieve the last 12 months of temperature observation data (TOBS).

  * Filter by the station with the highest number of observations.

  * Plot the results as a histogram with `bins=12`.

    ![station-histogram](Images/Highest_temp_obs.png)

- - -

## Step 2 - Climate App

Flask API was designed based on the queries that were developed.


### Routes

* `/`

  * Home page.

  * List all routes that are available.

* `/api/v1.0/precipitation`

  * Convert the query results to a dictionary using `date` as the key and `prcp` as the value.

  * Return the JSON representation of your dictionary.

* `/api/v1.0/stations`

  * Return a JSON list of stations from the dataset.

* `/api/v1.0/tobs`
  * Query the dates and temperature observations of the most active station for the last year of data.
  
  * Return a JSON list of temperature observations (TOBS) for the previous year.

* `/api/v1.0/<start>` and `/api/v1.0/<start>/<end>`

  * Return a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.

  * When given the start only, calculate `TMIN`, `TAVG`, and `TMAX` for all dates greater than and equal to the start date.

  * When given the start and the end date, calculate the `TMIN`, `TAVG`, and `TMAX` for dates between the start and end date inclusive.


- - -

