# Databricks Lakeflow Declarative Pipeline
The goal of this platform is to provide regional analytics for city managers while ensuring scalable and efficient data processing using modern Lakehouse architecture.
Databricks Lakeflow Spark Declarative Pipelines (SDP) and follows the Medallion Architecture pattern.

Raw Data → Bronze → Silver → Gold → Analytics

The system ingests raw ride data from Amazon S3, performs incremental processing with Auto Loader, applies data validation and CDC logic, and produces analytics-ready datasets for regional managers.

pipeline:

<img src="https://github.com/Sneha-mav/Databricks-lakeflow-pipeline/blob/main/pipeline.png">

### Bronze Layer:
Key implementations:<br>
-> batch ingestion for dimension data <br>
-> streaming ingestion using Databricks Auto Loader <br>
-> metadata tracking <br>
-> schema evolution support <br>
-> Change Data Feed enabled <br>

### Silver Layer
Key transformations:<br>
-> schema standardization <br>
-> column renaming<br>
-> data validation<br>
-> CDC <br>

### Gold Layer
-> Provide denormalized business-ready tables<br>
-> City-specific views created for regional managers<br>

Main dataset: transportation.gold.fact_trips
Constructed by joining:
silver.trips,
silver.city, 
silver.calendar
