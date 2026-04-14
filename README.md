🚀 Databricks Lakehouse Pipeline – Medallion Architecture
📌 Overview

This project demonstrates an end-to-end data engineering pipeline built using Databricks Lakeflow (Spark Declarative Pipelines).

The pipeline ingests raw data from AWS S3, processes it using Apache Spark, and transforms it into analytics-ready datasets using the Medallion Architecture (Bronze → Silver → Gold).

🏗️ Architecture
Source: AWS S3 (CSV / JSON files)
Processing Engine: Apache Spark (Databricks)
Pipeline Framework: Databricks Lakeflow (Declarative Pipelines)
Storage Format: Delta Lake
Architecture Pattern: Medallion Architecture
🔄 End-to-End Pipeline Workflow

Master-Table Facttrips.png

Databricks pipeline showing Bronze → Silver → Gold transformations

🔄 Data Pipeline Flow
🟤 Bronze Layer – Data Ingestion
Ingested raw data from AWS S3 using Auto Loader
Stored data in Delta format for reliability
Minimal transformations applied
Supports structured and semi-structured data (CSV, JSON)

⚪ Silver Layer – Data Transformation
Performed data cleansing and standardization
Handled null values and deduplication
Applied data validation rules
Enriched datasets using business logic

🟡 Gold Layer – Data Aggregation
Built fact tables for analytics
Joined multiple datasets (trips, city, calendar)
Optimized for BI and reporting use cases
Created city-level analytical views
Gold-Fact-trips Master table sample data.png
1 Gold-Fact-trips Master table sample data.png

🧱 Medallion Architecture
Bronze Layer → Raw ingestion from AWS S3
Silver Layer → Cleaned, validated, and transformed data
Gold Layer → Aggregated, business-ready datasets

📸 Pipeline Screenshots
🟤 Bronze Layer – Raw Data
Streaming ingestion from AWS S3 using Auto Loader
1 Bronze-trips AWS s3 data ingestion dry run .png
2 Bronze-trips dry run .png
3 Bronze-city Sampledata.png
4 Full View bronze.png
⚪ Silver Layer – Transformed Data
Date dimension with enriched attributes
Cleaned and validated trips data
1 Silver-Calendar sample data.png
2 Silver-Trips Timestamp SampleData.png
🟡 Gold Layer – Final Output
Final fact table combining trips, city, and calendar
1 Gold-Fact-trips Master table sample data.png
2 Trips-Chandigarh.png

⚙️ Key Features
✅ Built using Databricks Lakeflow (Declarative Pipelines)
✅ End-to-end ETL/ELT pipeline design
✅ Integrated AWS S3 with Databricks Auto Loader
✅ Implemented Medallion Architecture (Bronze, Silver, Gold)
✅ Applied data validation and quality checks
✅ Used Delta Lake features:
ACID transactions
Schema enforcement
Time travel
✅ Optimized Spark transformations for performance
📊 Business Use Case
This pipeline enables analytics on transportation data by creating a centralized fact_trips table:

Combines trip data with city and calendar dimensions
Supports city-level performance analysis
Enables reporting on:
Distance traveled
Revenue (sales)
Passenger and driver ratings

🛠️ Technologies Used
Apache Spark (PySpark)
Databricks (Lakeflow / Declarative Pipelines)
AWS S3
Delta Lake

SQL
🚀 What I Learned
Designing scalable data pipelines using Databricks
Implementing Medallion Architecture
Working with distributed data processing using Spark
Building end-to-end ETL workflows
Integrating cloud storage (S3) with processing engines
Applying data validation and transformation techniques

📂 Project Structure
databricks-lakehouse-pipeline/
│
├── notebooks/
│   ├── bronze/
│   │   ├── city.py
│   │   ├── trips.py
│   │
│   ├── silver/
│   │   ├── calendar.py
│   │   ├── city.py
│   │   ├── trips.py
│   │
│   ├── gold/
│       ├── trips_gold.sql
│       ├── city_views.sql
│
├── images/
│   ├── data_ingestion/        # AWS S3 ingestion screenshots
│   ├── bronze/                # Raw data (Bronze layer)
│   ├── silver/                # Cleaned & transformed data
│   ├── gold/                  # Fact tables & analytics output
│   ├── master/                # Final master dataset views
│
├── README.md

👤 Author
Naga Revathi Settipalli
Data Engineer | Analytics Engineer
Skilled in SQL, Python, Databricks, and Data Pipelines
