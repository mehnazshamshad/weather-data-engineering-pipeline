# weather-data-engineering-pipeline
# Weather Data Engineering Pipeline

## Project Overview

An end-to-end batch data pipeline that extracts historical weather data from the Open-Meteo API, processes it using Python and pandas, stores it in Snowflake, and prepares it for analysis and visualization.

## Architecture

Open-Meteo API → Python & pandas → Cleaned CSV → Snowflake Staging Table → Dimension & Fact Tables → Power BI

## Technologies Used

- Python
- pandas
- REST API and JSON
- Snowflake
- SQL
- Jupyter Notebook
- Power BI (dashboard development)

## Data Scope

- **Cities:** Jamshedpur, Delhi, Mumbai, and Kolkata
- **Date range:** September 1–3, 2026
- **Records:** 12 city-date weather records
- **Weather metrics:** Average temperature, precipitation, and maximum wind speed

## Data Warehouse Design

The project uses a dimensional model with the following tables:

- `STG_WEATHER` — staging table for weather data
- `DIM_DATE` — date dimension
- `DIM_LOCATION` — location dimension
- `FACT_WEATHER` — weather measurements linked to date and location

The intended grain of the fact table is one record per city per date.

## Data Quality Checks

- Checked for missing values and duplicate city-date records.
- Validated weather measurements.
- Verified fact table record counts and joins to dimension tables.

## SQL Analysis

The SQL scripts include:
- Table creation
- Dimension loading
- Fact table loading
- Analytical queries for temperature, precipitation, and wind speed

## Power BI Dashboard

The dashboard is still in progress. The Power BI file and screenshots will be added after the dashboard is completed.

## Repository Contents

- `weather_data_pipeline.ipynb` — Python data extraction and processing
- `weather_cleaned.csv` — cleaned weather dataset
- `create_tables.sql` — table creation statements
- `load_dimensions.sql` — dimension loading statements
- `load_fact_table.sql` — fact table loading statements
- `analysis_queries.sql` — analytical SQL queries

## How to Reproduce

1. Extract historical weather data using the Open-Meteo API.
2. Clean and validate the data using pandas.
3. Export the processed data to CSV.
4. Load the data into the Snowflake staging table.
5. Populate the date and location dimensions.
6. Load the fact table and run analytical queries.
7. Connect Power BI to Snowflake to build visualizations.

Use your own Snowflake account and credentials. Never commit passwords, access tokens, or other secrets.

## Future Improvements

- Automate scheduled batch extraction.
- Extend the historical date range.
- Implement incremental and idempotent loading.
- Add automated tests, logging, and error handling.
