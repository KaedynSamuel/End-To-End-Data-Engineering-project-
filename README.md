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
    Storage[Azure Storage Account] --> DF[Azure Data Factory]
    DF --> DB[Azure Databricks]
    DB --> Syn[Azure Synapse Analytics]
    KeyVault[Azure Key Vault] --- DB
    KeyVault --- DF
