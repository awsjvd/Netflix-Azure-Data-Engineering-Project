# Netflix Azure Data Engineering Project

## Project Overview  
This project demonstrates an **end-to-end Azure Data Engineering pipeline** using **Azure Data Factory, Databricks, Data Lake Gen2, Delta Live Tables, and Unity Catalog**. The pipeline is designed to **ingest, process, and transform incremental data** using **AutoLoader and Delta Live Tables (DLT)** while ensuring **secure data access between Databricks and Data Lake Gen2 using Access Control**.

## Tech Stack  
- **Azure Data Factory (ADF)** – Data ingestion from GitHub to Azure Data Lake Gen2  
- **Azure Data Lake Gen2 (ADLS Gen2)** – Storage for raw and transformed data  
- **Azure Databricks & AutoLoader** – Incremental data processing  
- **Delta Live Tables (DLT)** – Automated and scalable data transformation  
- **Parameterized Databricks Notebooks** – Dynamic and reusable transformation logic  
- **Unity Catalog (Databricks)** – Storage for structured (Gold Layer) datasets  
- **Azure Databricks Access Connector** – Secure access between Databricks and ADLS Gen2  
- **Azure Key Vault** – Secure credentials management  
- **Notebook-Based Scheduling** – Conditional execution based on the **7th day of the week**  
- **Power BI (Planned Enhancement)** – Interactive data visualization and reporting  

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
   - The raw data from the **Bronze Layer** is cleansed, transformed, and stored in the **Silver Layer** of **Azure Data Lake Gen2**.  
   - **Delta Live Tables (DLT)** ensure **automated, scalable, and fault-tolerant transformations**.  

   ![Delta Live Tables Pipeline](https://github.com/awsjvd/Netflix-Azure-Data-Engineering-Project/blob/main/Databricks/Delta%20Live%20Tables.JPG)  

### **4. Data Serving using Unity Catalog (Gold Layer)**  
   - The **structured and processed data** is stored in **Unity Catalog** to enable **centralized governance, fine-grained access control, and optimized querying**.  

### **5. Scheduling & Conditional Execution (Runs on the 7th Day of the Week)**  
   - The pipeline includes a **notebook-based conditional scheduling mechanism**.  
   - A **Weekday Lookup Notebook** checks if the current day is the **7th day of the week**.  
   - If **True**, the **SilverMasterData** notebook executes.  
   - If **False**, an alternative notebook **FalseNoteBook** runs.   

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
- **Automated Scheduling & Conditional Execution**  
  - The **pipeline dynamically determines whether to process Silver data or execute an alternative workflow** based on the **day of the week**.  
- **Centralized Governance with Unity Catalog**  
  - The **Gold Layer is stored in Unity Catalog**, ensuring **fine-grained access control, schema governance, and Databricks SQL compatibility**.  

## Future Enhancements    
- Implement **CI/CD with Azure DevOps** for seamless deployment.  
- Optimize **querying performance** by integrating **Azure Synapse Analytics**.  
- Extend **Unity Catalog policies** for better governance and security.  
- **Integrate with Power BI for interactive reporting and dashboards**.  
