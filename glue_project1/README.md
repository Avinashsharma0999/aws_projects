# AWS aws-glue-etl-csv-to-parquet Project

An end-to-end data transformation workflow using AWS Glue, converting CSV files stored in Amazon S3 into Parquet format and storing the transformed data back in S3.

It utilizes multiple AWS Glue components: crawlers to infer schema and create metadata tables, the data catalog to store metadata definitions including databases and tables, and ETL jobs to perform the actual data transformation.

The process begins by configuring an S3 bucket with source and target folders and uploading the CSV data file.

An IAM role is created to grant AWS Glue permissions to access S3 and other AWS services securely.

A Glue database is created in the data catalog, logically grouping table definitions; then a crawler is configured to scan the S3 source folder, automatically detect the CSV schema using built-in classifiers, and populate the catalog with table metadata.

The crawler runs on demand, and its results are verified by examining the created table schema in the Glue console.

An ETL job is created using AWS Glue Studio’s visual interface with a blank canvas, configuring three nodes: source (the Glue catalog table), transform (applying mappings such as data type changes and renaming columns), and target (writing output as a Parquet file to the S3 target folder).

The job is configured with appropriate IAM roles, worker types, scripting language (Python 3), and optionally auto-scaling and retry policies.

Upon running, the job extracts data from the Glue catalog table, applies transformations, and writes the Parquet output back to S3.

The output file is validated by querying it directly in S3 using S3 Select, confirming the successful format conversion and transformation.

The tutorial provides a practical example of how AWS Glue components can be orchestrated to automate and simplify large-scale ETL workflows in a cloud-native environment.
# Workflow
<img width="1132" height="107" alt="image" src="https://github.com/user-attachments/assets/6eee3b58-32f3-4215-adbf-c78d6d6c904e" />

<img width="825" height="373" alt="image" src="https://github.com/user-attachments/assets/1bf3f7f0-60bf-488c-90d6-ab4e7cd27f69" />

# ETL Pipeline Visuals
<img width="542" height="470" alt="image" src="https://github.com/user-attachments/assets/71a2e9bf-f8ff-4ac3-8c27-5e76ec795091" />


 


