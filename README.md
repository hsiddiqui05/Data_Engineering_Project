## Azure Data Engineering: Medallion Architecture Pipeline
# Project Overview
This project demonstrates an automated end-to-end ETL/ELT pipeline built on the Azure Cloud Platform. It ingests raw AdventureWorks data from a GitHub source, processes it through structured layers using PySpark, and serves it via Synapse Serverless SQL for business intelligence.

## 🛠️ Tech Stack
**Orchestration**: Azure Data Factory (ADF)
**Storage: Azure**: Data Lake Storage (ADLS) Gen2
**Computation**: Azure Databricks (PySpark)
**Data Warehousing**: Azure Synapse Analytics (Serverless SQL Pools)
**Architecture**: Medallion (Bronze, Silver, Gold)
**Visualization**: Power BI (optional)

## Project Workflow

# Data Pipeline Architecture
Ingestion (Bronze): Azure Data Factory triggers an HTTP-based ingestion to pull CSV files from a GitHub repository, landing them in their raw format in ADLS Gen2 (Bronze Layer).
# Transformation (Silver): 
Azure Databricks utilizes PySpark to clean data, handle schema enforcement, and convert raw CSVs into optimized Parquet files stored in the Silver Layer.
# Serving (Gold): 
Synapse Serverless SQL creates a semantic layer using SQL Views. These views reference the Parquet files via OPENROWSET, providing a cost-effective "Gold Layer" without moving data into a dedicated SQL pool.
# Reporting(optional): 
Power BI connects to the Synapse Gold views to deliver a comprehensive sales and inventory dashboard.

## Tools & Services Used
- Azure Data Factory
- Azure Data Lake Gen2
- Azure Databricks
- Azure Synapse Analytics (Serverless SQL)
- PySpark
- SQL
- GitHub

## Key Transformations
- Date parsing and type casting
- Union of yearly sales data (2015–2017)
- Derived columns (Month, Year, FullName)
- Schema standardization

## Status
⚠ Azure services were provisioned using a free trial and are currently inactive.
All scripts, architecture, and logic are available in this repository.
Data_Engineering_Project
