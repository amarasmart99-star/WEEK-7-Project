# Weather Data ETL Pipeline

**AnalystLab Africa — Data Analytics Internship (Batch B)**
**Week 7: Data Pipelines & Automation**

## Project Overview
This project builds a simple ETL (Extract, Transform, Load) pipeline that pulls
real-time weather data from the OpenWeather API for five cities, cleans it
with pandas, and stores it as both a CSV file and a SQLite database.

## Data Source
OpenWeather API — https://openweathermap.org/api
Cities collected: Kano, Lagos, Abuja, London, New York

## ETL Process
**Extract:** Looped through each city and called OpenWeather's current
weather endpoint using an API key, collecting the raw JSON response for each.

**Transform:** Flattened each city's JSON into a row (city, temperature,
feels-like, humidity, weather condition/description, wind speed, timestamp),
combined into a pandas DataFrame, and enforced correct data types
(floats for temperature, integer for humidity, real datetime for timestamp).

**Load:** Saved the cleaned dataset to `weather_data.csv` and to a SQLite
database (`weather_data.db`, table `weather`).

## Tools Used
Python, requests, pandas, sqlite3, Jupyter Notebook

## Key Findings
- Hottest city: New York (33.54°C)
- Coldest city: Abuja (23.49°C)
- Most humid city: Lagos (93%)
- All five cities were cloudy at data-collection time, but cloud cover
  ranged from "few clouds" (Abuja) to "overcast clouds" (Lagos) — the
  heavier cloud cover in Lagos lines up with it also having the highest humidity.