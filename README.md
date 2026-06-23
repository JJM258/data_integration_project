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

## Technological Requirements

- Apache Spark
- Databricks (Catalog, Workspace, SQL Warehouse)
- Power BI


## How to Run (Recommend Option 1)

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
- On databricks, click the user icon
- After click settings and then under __user__ click __linked accounts__
- Next click the butten __Git Integration__, and link your personal git account
- Then clone this git repository into your github
- Finally, in databricks, create a new workspace using a Git Folder

Author

__JJM258__
