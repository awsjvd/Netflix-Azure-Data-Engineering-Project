# Netflix Azure Data Engineering Project

## Project Overview  
This project demonstrates an **end-to-end Azure Data Engineering pipeline** using **Azure Data Factory, Databricks, Data Lake Gen2, Delta Live Tables, and Access Control mechanisms**. The pipeline is designed to **ingest, process, and transform incremental data** using **AutoLoader and Delta Live Tables (DLT)** while ensuring **secure data access between Databricks and Data Lake Gen2 using Access Control**.

## Tech Stack  
- **Azure Data Factory** (Data Ingestion)  
- **Azure Data Lake Gen2** (Storage for Bronze, Silver, and Gold layers)  
- **Azure Databricks & AutoLoader** (Incremental Data Processing)  
- **Delta Live Tables (DLT)** (Data Transformation)  
- **Azure Databricks Access Connector** (Secure Access to ADLS Gen2)  
- **Azure Key Vault** (Credentials Management)  

## Process  
1. **Data Ingestion**  
   - Data is extracted from **GitHub** and ingested into the **Bronze Layer** of **Azure Data Lake Gen2** using **Azure Data Factory**.  
   - The process includes **metadata extraction, validation, and file iteration**.  

   ![Azure Data Factory Pipeline](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/DataFactory/Pipeline.JPG)  

2. **Data Transformation**  
   - **Azure Databricks AutoLoader** processes **incremental data** from the **Bronze Layer**.  
   - **Delta Live Tables (DLT)** perform structured transformations and store the processed data in the **Silver Layer**.  

   ![Delta Live Tables Pipeline](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/Databricks/Delta%20Live%20Tables.JPG)  

3. **Data Serving & Star Schema**  
   - The **Gold Layer** contains structured datasets optimized using **Star Schema** for efficient querying and analytics.  

## Flow Diagram  
The data pipeline follows a **Bronze-Silver-Gold** architecture. The detailed **data flow diagram** can be viewed here:  

![Data Flow](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/Flow%20Diagram/Flow_Diagram.JPG)  

## Insights  
- **Secure Data Access**  
  - **Azure Databricks Access Connector** provides **RBAC-controlled secure access** to **ADLS Gen2**.  
- **Incremental Data Processing**  
  - **AutoLoader** efficiently handles **real-time incremental data ingestion**.  
- **Optimized Transformation**  
  - **Delta Live Tables (DLT)** ensure **automated, scalable, and fault-tolerant transformations**.  
- **Structured Data**  
  - The **Gold Layer** follows a **Star Schema**, optimizing query performance.  

## Future Enhancements  
- Automate pipeline execution using **Azure Data Factory triggers**.  
- Implement **CI/CD with Azure DevOps** for seamless deployment.  
- Optimize **querying performance** by integrating **Azure Synapse Analytics**.  
- Extend **access control policies** for better governance and security.  
