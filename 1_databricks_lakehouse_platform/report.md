## Section 1: Databricks Lakehouse Platform

#### What is a data lake?

- Centralized repository that ingests and stores large volumes of data in its original form. The data can then be processed and used as a basis for a variety of analytic needs. Due to its open, scalable architecture, a data lake can accommodate all types of data from any source, from structured (database tables, Excel sheets) to semi-structured (XML files, webpages) to unstructured (images, audio files, tweets), all without sacrificing fidelity.
- The data files are typically stored in staged zones (bronze, silver and gold) raw, cleansed, and so that different types of users may use the data in its various forms to meet their needs. Data lakes provide core data consistency across a variety of applications, powering big data analytics, machine learning, predictive analytics, and other forms of intelligent action.
- The goal of a data lake is to keep raw data consolidated, integrated, secure, and accessible. Scalable storage tools like Azure Data Lake Storage can hold and protect data in one central place, eliminating silos at an optimal cost. The data can then be used to feed upstream data visualization and ad-hoc reporting needs.

#### Describe the relationship between the data lakehouse and the data warehouse  

- A data lake captures both relational and non-relational data from a variety of sources without having to define the structure or schema of the data until it is read. Schema-on-read ensures that any type of data can be stored in its raw form. As a result, data lakes can hold a wide variety of data types, from structured to semi-structured to unstructured, at any scale. Their flexible and scalable nature make them essential for performing complex forms of data analysis using different types of compute processing tools like Apache Spark or Azure Machine Learning.

- By contrast, a data warehouse is relational in nature. The structure or schema is modeled and optimized for SQL query operations. While a data lake holds data of all structure types, including raw and unprocessed data, a data warehouse stores data that has been treated and transformed with a specific purpose in mind, which can then be used to source analytic or operational reporting.

#### Identify the improvement in data quality in the data lakehouse over the data lake

- Schema Enforcement: Data lakehouses enforce schema at write time, ensuring that all data written to the lakehouse adheres to predefined schema rules. This enforcement helps prevent data quality issues that arise from schema mismatches or unexpected data formats, which are common in data lakes where schema is applied on read (schema-on-read).

- ACID Transactions: Data lakehouses support ACID (Atomicity, Consistency, Isolation, Durability) transactions. This means changes to data are performed with guaranteed consistency, including multi-table transactions and rollbacks in case of failures, thus improving the reliability and quality of the data stored.

- Data Governance and Auditing: Enhanced capabilities for data governance and auditing are integral to data lakehouses. This includes features like data versioning, tracking data lineage, and detailed audit logs, which help maintain high data quality by providing visibility into data modifications and usage over time.

Overall, the data lakehouse model aims to offer the scalability and flexibility of data lakes with the structured management and data quality features of data warehouses. This results in significant improvements in data quality and usability.

#### Compare and contrast silver and gold tables, which workloads will use a bronze table as a source, which workloads will use a gold table as a source

- *Bronze tables* are the rawest form of data storage in the lakehouse architecture. They store unrefined, unprocessed data directly ingested from various sources. This data may include logs, system files, and other unstructured or semi-structured data. Workloads using bronze tables as a source:

    1. Data cleansing and processing jobs: These workloads transform raw data into a more usable format. They might include jobs for filtering, deduplication, and error correction.

    2. ETL (Extract, Transform, Load) processes: Initial extraction and transformation tasks pull data from bronze tables to process and load them into more structured silver tables.

- *Silver tables* contain processed data that has been cleansed, validated, and transformed from the bronze tables. This data is more structured and standardized than bronze data, and may involve applying business logic or integrating data from multiple sources. Workloads using silver tables as a source:

     1. Further data transformation jobs: These might refine the data further, perhaps aggregating it or performing more complex transformations based on business logic.

  1. Machine learning pipelines: Data scientists often use the cleaned and somewhat processed data in silver tables to train and validate machine learning models.

- *Gold tables* are highly curated datasets that provide the most value to business users. They contain aggregated, summarized, or otherwise enriched data that is directly used for decision-making and reporting. Workloads using gold tables as a source:

  1. Business intelligence and analytics: Gold tables are the primary source for BI tools and analytical platforms that generate reports, dashboards, and visualizations for end-users.

  2. Advanced analytics: These include complex queries and data analysis performed for high-level business insights, often using the concise and high-quality data found in gold tables.
Comparison and Contrast

Bronze tables have the lowest data quality (raw data), silver tables have moderate quality (processed data), and gold tables have the highest quality (refined and business-ready data).
Purpose: Bronze is for raw data capture, silver for data cleaning and business logic application, and gold for delivering insights and analytics.

Users: Bronze tables are typically used by data engineers, silver tables also by data engineers and data scientists for intermediate processing, and gold tables are primarily used by business analysts and decision-makers.

In essence, data moves through these layers from bronze to gold, increasing in value and usability at each step, with each subsequent layer typically sourcing its data from the preceding one. This structured approach facilitates efficient data management and maximizes data utility across different organizational needs. This structure is called the medaillon structure.

#### What is located in the data plane versus the control plane and what resides in the customer’s cloud account

#### Differentiate between all-purpose clusters and jobs clusters

#### Identify how cluster software is versioned using the Databricks Runtime

#### Identify how clusters can be filtered to view those that are accessible by the user

#### Describe how clusters are terminated and the impact of terminating a cluster

#### Identify a scenario in which restarting the cluster will be useful

#### Describe how to use multiple languages within the same notebook

#### Identify how to run one notebook from within another notebook

#### Identify how notebooks can be shared with others

#### escribe how Databricks Repos enables CI/CD workflows in Databricks

#### Identify Git operations available via Databricks Repos

#### Identify limitations in Databricks Notebooks version control functionality relative to Repos
