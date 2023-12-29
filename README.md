# Bayesian-Uber-Pickup

## Overview

This project analyzes Uber pickup patterns across New York City counties over time using Bayesian modeling techniques. The goals are to understand spatial, temporal, and spatial-temporal interactions and predict pickup frequencies. 

Bayesian models are developed to predict Uber pickup events at the county level, incorporating zone characteristics, spatial dependencies, and temporal dependencies. The project involves data pulling, processing, exploratory analysis, modeling, and evaluation.

The final report summarizing the project's findings is available in the file `Final Report.pdf`.

## Data
The raw data comes from two sources:
 
  * Uber pickup: latitude/longitude, date/time [(Kaggle)](https://www.kaggle.com/fivethirtyeight/uber-pickups-in-new-york-city)
  * NYC county boundaries and zone characteristics: total population, employed population, housing unit [(NHGIS)](https://data2.nhgis.org/main)

## Model
Hierarchical Bayesian models are applied. At the first level, the number of pickups (𝑌_𝑖𝑡) follows a Poisson distribution, where 𝑛𝑖 is the base pickup frequency for each county and 𝑅_𝑖𝑡 is the pickup rates of each county 𝑖 at a 𝑡-th time interval.
$$
\Y_it = 𝑃𝑜𝑖𝑠𝑠𝑜𝑛(n_i* R_it)
$$

## Files
  * `GeoData-Processing.ipynb` This script serves as a comprehensive data pipeline, including data fetching, quality assurance and quality control (QAQC), modeling, geo-simulation modeling, and model evaluation.
  * `Uber_Prediction.ipynb`:  This script automates the processes involved in uploading the simulation results to a PostGIS database using the shp2pgsql tool.

## Output
The repository generates a series of priority maps for stink bug monitoring, which are published on ArcGIS Online for easy access and utilization.
