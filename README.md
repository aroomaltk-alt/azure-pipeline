Azure Weather Data Engineering Pipeline
Project Overview

This project demonstrates an end-to-end Azure Data Engineering pipeline built using modern cloud technologies. The pipeline ingests real-time weather data from a Weather API, stores it in Azure Data Lake Storage, transforms the data using Azure Databricks, and visualizes insights in Power BI.

The project follows the Medallion Architecture approach:

Bronze Layer → Raw Ingestion
Silver Layer → Cleaned & Transformed Data
Gold Layer → Analytics & Reporting
Architecture Diagram
Weather API
     │
     ▼
Azure Data Factory
     │
     ▼
ADLS Raw Layer
     │
     ▼
Bronze Layer (Databricks)
     │
     ▼
Silver Layer (Databricks)
     │
     ▼
Gold Layer (Databricks)
     │
     ▼
Power BI Dashboard
Technologies Used
Service	Purpose
Azure Data Factory	Data ingestion and orchestration
Azure Data Lake Storage Gen2	Data storage
Azure Databricks	Data transformation
PySpark	Data processing
Delta Lake	Reliable storage format
Power BI	Reporting & visualization
Weather API	Source system
Project Workflow
1. Data Ingestion
Weather data is fetched from Weather API using Azure Data Factory.
Raw JSON files are stored in ADLS Gen2 Raw Layer.
2. Bronze Layer
Raw API data is loaded into Databricks Bronze tables.
Data is stored as-is for historical tracking.
3. Silver Layer

Data transformations performed:

Schema enforcement
Data cleaning
Null handling
Timestamp conversion
Flattening nested JSON
4. Gold Layer

Business-ready tables created:

Daily weather summary
Temperature trends
Humidity analysis
City-wise weather reports
5. Reporting
Gold layer tables connected to Power BI.
Interactive dashboards created for analytics.
Folder Structure
azure-weather-pipeline/
│
├── adf-pipelines/
│
├── databricks-notebooks/
│   ├── bronze/
│   ├── silver/
│   └── gold/
│
├── arm-template/
│
├── architecture-diagram/
│
├── powerbi-dashboard/
│
└── README.md



