# Intech Data Engineering Project

**Author:** Kaedyn Samuel Padayachee  
**Date:** 2025  

---

## Project Overview

This is a full-scale **Data Engineering project** built using Microsoft Azure services. The project demonstrates end-to-end data management, from secure storage and ingestion to transformation and analytics. It showcases best practices in Azure data engineering, including security, orchestration, and scalable pipeline design.

The project uses the following Azure components:

- **Azure Key Vault**: Securely stores secrets and connection strings.  
- **Azure Databricks**: Performs ETL, data transformations, and analytics using PySpark.  
- **Azure Data Factory (V2)**: Orchestrates pipelines and moves data between sources.  
- **Azure Synapse Analytics**: Stores transformed data for analytical queries and reporting.  
- **Azure Storage Account**: Holds raw and processed data in a secure and scalable way.  

---

## Architecture Diagram

```mermaid
flowchart LR
    %% Data Source
    SMSSData[📥 SMSS Data Source] --> Storage[🗄️ Azure Storage Account]

    %% Pipelines
    Storage --> DF[🔄 Azure Data Factory]

    %% Transformation
    DF --> DB[💻 Azure Databricks]

    %% Analytics
    DB --> Syn[📊 Azure Synapse Analytics]

    %% Reporting
    Syn --> PB[📈 Power BI Dataset]

    %% Security
    KeyVault[🔑 Azure Key Vault] --- DB
    KeyVault --- DF






## How the Project Works

This project implements a full **end-to-end data engineering pipeline** using Azure services. The flow is designed for efficiency, scalability, and security. Here's how it works step by step:

1. **Data Ingestion from SMSS (📥)**  
   - Raw data is collected from the **SMSS** system.  
   - Data is securely stored in the **Azure Storage Account (🗄️)**.  
   - This ensures a persistent and centralized source for all subsequent processing.

2. **Orchestration with Data Factory (🔄)**  
   - **Azure Data Factory pipelines** orchestrate the movement of data from storage into processing layers.  
   - Pipelines handle scheduling, dependencies, and error handling automatically.  

3. **Data Transformation in Databricks (💻)**  
   - **Azure Databricks notebooks** perform ETL (Extract, Transform, Load) operations.  
   - Data is processed according to **Bronze, Silver, Gold layers**:  
     - **Bronze Layer:** Raw, ingested data is stored as-is for traceability.  
     - **Silver Layer:** Data is cleaned, validated, and structured for analysis.  
     - **Gold Layer:** Fully transformed, enriched, and aggregated data ready for analytics and reporting.  

4. **Storage and Analytics in Synapse (📊)**  
   - Transformed data is loaded into **Azure Synapse Analytics**.  
   - Synapse allows fast analytical queries, reporting, and further data exploration.

5. **Visualization in Power BI (📈)**  
   - **Power BI datasets** automatically update after pipeline runs.  
   - Dashboards reflect the latest processed data, giving stakeholders real-time insights.  

6. **Security with Key Vault (🔑)**  
   - All credentials, keys, and secrets are securely stored in **Azure Key Vault**.  
   - Databricks and Data Factory retrieve secrets at runtime, ensuring no sensitive information is hardcoded.

**Summary:**  
The project demonstrates a secure, scalable, and automated **data engineering workflow**, from ingestion (SMSS) → orchestration (Data Factory) → transformation (Databricks: Bronze, Silver, Gold) → storage/analytics (Synapse) → reporting (Power BI), all while following medial architecture principles.

