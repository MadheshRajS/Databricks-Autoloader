# Insurance Data Pipeline with Delta Lake

This project demonstrates an end-to-end data pipeline for processing insurance-related data (customers, policies, and claims) using Databricks, Spark, and Delta Lake. The pipeline follows a medallion architecture (Bronze → Silver → Gold layers) for data quality and business insights.

## Features

### Data Generation
- Generate synthetic datasets for Customers, Policies, and Claims as CSV files
- Display dataset sizes for verification

### Bronze Layer - Raw Data Ingestion
- **Auto Loader Configuration**: Ingest raw CSV files efficiently
- Display records after ingestion for validation

### Silver Layer - Data Cleaning & Enrichment
- Handle null values and invalid records
- Standardize data formats (e.g., uppercase conversion)
- Add derived columns (e.g., Policy Age in Days)
- Join datasets (Claims + Policies + Customers)
- Handle duplicate records
- Write cleaned data to Delta tables

### Gold Layer - Business Insights
- **Key Aggregations**:
  - Total claims per customer
  - Average claim amount by policy type
  - Monthly claims trend analysis
  - Claims by day of the week
- Write aggregated data to optimized Delta tables

### Performance Optimizations
- Partitioning Delta tables (e.g., by `claim_date`)
- Caching frequently accessed DataFrames
- Delta Lake optimizations (`OPTIMIZE` and `ZORDER`)

### Visualization
- Inline visualizations using `display()`:
  - Monthly claims trend charts
  - Total claims per customer graphs
- Interactive dashboards with Databricks widgets:
  - Filter data by policy type

### Schema Evolution
- Handle new records seamlessly
- Add new columns to existing datasets
- Modify existing column definitions

## Technical Stack
- Databricks
- Apache Spark
- Delta Lake
- Python
