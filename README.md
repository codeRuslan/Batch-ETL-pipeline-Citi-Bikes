# Citi Bike ETL 

## Project Overview 
This project were build as a final project for Data Engineering Zoomcamp (https://github.com/DataTalksClub/data-engineering-zoomcamp)
My main task with this project were to apply everything that I have learned through out the course.

## Problem Statement 
I should have extracted, transformed and visualize data from Citi Bike Dataset (https://s3.amazonaws.com/tripdata/index.html). As, a final goal I had to present general information about bike users in 2020.

## Data
I have used data from Citi Bike Tripdata S3 bucket (https://s3.amazonaws.com/tripdata/index.html), it was stored in a zipped csv format.
It contains information about bikes sharing in different regions of New York.

## Technologies used 
Technologies:
  1. Setting-up infrastructure: Terraform & Docker
  2. Storing data: GCP Bucket & BigQuery 
  3. Orchestration: Airflow
  4. Transforming data: dbt
  5. Data Visualization: Google Data Studio (another variants are PowerBI(harder to set-up data from Google) or Tableau)
  
## Final Architecture 
![image](https://snipboard.io/b3xr7n.jpg)

1. Data has to be extracted from S3 and unzipped, converted into parquet file format and uploaded into bucket
2. From bucket data has to go into BigQuery, to create optimized partitioned table
3. Data uploaded into dbt Cloud via supported integration with BigQuery
4. Data transformed in dbt Cloud and uploaded back into BigQuery
5. Data visualized with Google Data Studio

## Detailed dbt transformation
1. stg_citibike_tripdata.sql - were used in order to cast all features and to create key for dataframe.
2. fact_citibike_trips.sql - were used to get the most vital data, that would be used for viz
3. dm_monthly_zone_revenue_trip_stats.sql - were used to create grouped values by month.

![image](https://snipboard.io/QhD6En.jpg)

## Final visualization

I have used Google Data Studio, because it was the fastest and easiest way to implement visualization from BigQuery. But still PowerBI and Tableau could also be used.

![image](https://snipboard.io/ObElAJ.jpg)
