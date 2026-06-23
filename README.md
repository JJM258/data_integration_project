# Data Integration Project

## Overview
An ETL (Extract, Transform, Load) pipeline built using Databricks.
This project covers the full data pipeline structure, from data extraction, cleaning, transformation, analysis and visualisation. 

## Project Structure

### data - folder that contains raw data files
Sourced from:
https://dados.cm-lisboa.pt/tr/dataset/condicionamentos-de-transito-historico
### ETL - Extraction.ipynb - load and inspect raw data and create raw data tables need for cleaning and visualisation
### ETL - Cleaning.ipynb - remove null values, duplicates and normalise inconsistencies 
### ETL - Transform.ipynb - merge relevant tables/columns and create a data analysis table
### ETL - Data Analysis.ipynb - data analysis and insights
### README.md


Pipeline Overview

Stage 1 — Extraction (ETL - Extraction.ipynb)

Loads raw data from source files into pandas DataFrames. Performs an initial inspection of shape, data types, and null counts to understand the dataset before any modifications.

Stage 2 — Cleaning (ETL - Cleaning.ipynb)

Handles data quality issues including missing value imputation (median fill for numerics), dropping irrelevant or sparse columns, removing rows with critical nulls, and standardising string casing across key fields.

Stage 3 — Transform (ETL - Transform.ipynb)

Applies feature engineering such as datetime parsing and extraction of year, month, and day components. Converts columns to correct numeric types, renames columns to snake_case, and prepares the dataset for analysis or modelling.

Stage 4 — Data Analysis (ETL - Data Analysis.ipynb)

Performs exploratory data analysis on the cleaned and transformed dataset. Includes descriptive statistics, distribution analysis, and pattern identification across key fields.


## Technological Requirements

- Apache Spark
- Databricks (Catalog, Workspace, SQL Warehouse)
- Power BI


## How to Run

### Option 1
- Create a catalog "etl_project" in databricks catalog, create a schema "etl_schema ", and create a volume "etl_data", in volume "etl_data" create a folder called "condicionamentos"
- Download the raw data given in the folder "data" here on github, and upload it to the folder "condicionamentos"
- Run the notebooks in order within databricks workspace:
  1. ETL - Extraction.ipynb
  2. ETL - Cleaning.ipynb
  3. ETL - Transform.ipynb
  4. ETL - Data Analysis.ipynb
- Then using Power BI desktop the user can create there own visual insights based on the Data Analysis notebook (the visualisation I created are upload here on the github/pdf upload)

### Option 2

Key Design Decisions


Median imputation is used for numeric nulls to avoid skewing distributions with mean values.
Columns with high sparsity (e.g. platform-specific metrics) are dropped to keep the dataset lean and focused on core Spotify features.
Snake_case column naming is enforced after transformation to ensure consistent, programmatic access across all downstream steps.
Notebooks are kept stage-isolated — each notebook reads from source and produces clean output, making individual stages easy to debug or rerun independently.



Author

JJM258****
