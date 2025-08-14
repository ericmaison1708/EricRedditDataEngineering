# Data Pipeline with Reddit

A full-stack ETL pipeline that collects Reddit data, processes it, and loads it into Amazon Redshift for analytics — powered by Apache Airflow, Celery, PostgreSQL, Amazon S3, AWS Glue, and Amazon Athena.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [System Setup](#system-setup)

## Overview

The pipeline is designed to:

1. Extract data from Reddit using its API.
2. Store the raw data into an S3 bucket from Airflow.
3. Transform the data using AWS Glue and Amazon Athena.
4. Load the transformed data into Amazon Redshift for analytics and querying.

## Architecture
![RedditDataEngineering.png](assets%2FRedditDataEngineering.png)
1. **Reddit API**: Source of the data.
2. **Apache Airflow & Celery**: Orchestrates the ETL process and manages task distribution.
3. **PostgreSQL**: Temporary storage and metadata management.
4. **Amazon S3**: Raw data storage.
5. **AWS Glue**: Data cataloging and ETL jobs.
6. **Amazon Athena**: SQL-based data transformation.
7. **Amazon Redshift**: Data warehousing and analytics.

## System Setup in Windows
1. Clone the repository and fix your PostgresSQL database, AWS and Reddit ID in config.conf
   ```bash
    git clone 
   ```
2. Create a virtual environment.
   ```bash
    python -m venv venv
   ```
3. Activate the virtual environment.
   ```bash
    source venv/Scripts/activate
   ```
4. Install the dependencies.
   ```bash
    pip install -r requirements.txt
   ```
5. Rename the configuration file and the credentials to the file.
   ```bash
    mv config/config.conf.example config/config.conf
   ```
6. Starting the containers
   ```bash
    docker-compose up -d
   ```
7. Launch the Airflow web UI.
   ```bash
    start http://localhost:8080
   ```
