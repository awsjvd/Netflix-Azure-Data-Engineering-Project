# Netflix Azure Data Engineering Project

## Project Overview  
This project demonstrates an **end-to-end Azure Data Engineering pipeline** using **Azure Data Factory, Databricks, Data Lake Gen2, Delta Live Tables, and Access Control mechanisms**. The pipeline is designed to **ingest, process, and transform incremental data** using **AutoLoader and Delta Live Tables (DLT)** while ensuring **secure data access between Databricks and Data Lake Gen2 using Access Control**.

## Tech Stack  
- **Azure Data Factory (ADF)** – Data ingestion from GitHub to Azure Data Lake Gen2  
- **Azure Data Lake Gen2 (ADLS Gen2)** – Storage for Bronze, Silver, and Gold layers  
- **Azure Databricks & AutoLoader** – Incremental data processing  
- **Delta Live Tables (DLT)** – Automated and scalable data transformation  
- **Parameterized Databricks Notebooks** – Dynamic and reusable transformation logic  
- **Azure Databricks Access Connector** – **Secure access between Databricks and ADLS Gen2**  
- **Azure Key Vault** – Secure credentials management  

## Process  
### **1. Data Ingestion using Azure Data Factory**  
   - Data is extracted from **GitHub** and ingested into the **Bronze Layer** of **Azure Data Lake Gen2** using **Azure Data Factory (ADF)**.  
   - The process includes **metadata extraction, validation, and file iteration**.  

   ![Azure Data Factory Pipeline](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/DataFactory/Pipeline.JPG)  

### **2. Incremental Data Loading into Bronze Layer using AutoLoader**  
   - **AutoLoader in Azure Databricks** is used to **load incremental data** into the **Bronze Layer** of **Azure Data Lake Gen2**.  
   - AutoLoader enables **schema evolution, efficient file discovery, and optimized ingestion**.  
   - The raw data is stored in **Delta format** to support further transformations.  

### **3. Data Transformation using Parameterized Notebooks & Delta Live Tables (DLT)**  
   - **Parameterized Databricks Notebooks** are used for **flexible transformations**, allowing dynamic configurations.  
   - The raw data from the **Bronze Layer** is cleansed, transformed, and stored in the **Silver Layer**.  
   - **Delta Live Tables (DLT)** ensure **automated, scalable, and fault-tolerant transformations**.  

   ![Delta Live Tables Pipeline](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/Databricks/Delta%20Live%20Tables.JPG)  

### **4. Data Serving using Star Schema (Gold Layer)**  
   - The **transformed data** is structured into a **star schema** for optimized querying and analytics.  
   - This structured data is stored in the **Gold Layer** of **Azure Data Lake Gen2**.  

## **Flow Diagram**  
The data pipeline follows a structured **Bronze-Silver-Gold** architecture. The detailed **data flow diagram** can be viewed here:  

![Data Flow](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/Flow%20Diagram/Flow_Diagram.JPG)  

## Insights  
- **Secure Data Access**  
  - **Azure Databricks Access Connector** ensures **secure, RBAC-controlled access** to **ADLS Gen2**.  
- **Incremental Data Processing**  
  - **AutoLoader** efficiently **loads real-time incremental data** into the Bronze Layer.  
- **Optimized & Flexible Transformation**  
  - **Parameterized Notebooks** allow dynamic data processing configurations.  
  - **Delta Live Tables (DLT)** automate transformations for **scalability and efficiency**.  
- **Structured Data for Querying**  
  - The **Gold Layer** follows a **Star Schema**, making the data **optimized for analytics and reporting**.  

## Future Enhancements  
- Automate pipeline execution using **Azure Data Factory triggers**.  
- Implement **CI/CD with Azure DevOps** for seamless deployment.  
- Optimize **querying performance** by integrating **Azure Synapse Analytics**.  
- Extend **access control policies** for better governance and security.  
