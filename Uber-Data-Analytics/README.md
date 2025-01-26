# Uber Data Analytics | Modern Data Engineering GCP Project
## Introduction
This project focuses on performing advanced data analytics on NYC taxi data by leveraging modern data engineering tools and technologies. The objective is to design and implement a scalable pipeline for ingesting, transforming, and analyzing trip data, ultimately delivering actionable insights using GCP services and analytics tools.

## Architecture
The architecture involves integrating multiple GCP services and modern data tools to build an end-to-end data engineering workflow. Key components include:

## Ingestion and storage of raw trip data.
Data cleaning and transformation using a modern pipeline tool.
Analytics and visualization of results using BigQuery and Looker Studio.
## Technology Used
### Programming Language:
Python

### Google Cloud Platform (GCP):

**Google Storage:** Storing raw and processed trip data.

**Compute Instance:** Running ETL/ELT jobs and custom Python scripts.

**BigQuery:** Executing SQL queries on large datasets for analytics.

### Visualization:

**Looker Studio:** Creating dashboards and visualizations for actionable insights.

### Modern Data Pipeline Tool:

**Mage:** Building, orchestrating, and automating ETL/ELT pipelines for efficient data workflows.

## Key Objectives
Ingest NYC taxi data into GCP storage.

Build and automate data pipelines using Mage for transformation.

Analyze and query data using BigQuery for meaningful insights.

Visualize findings in Looker Studio for better decision-making.
## Data Modelling:
Data modeling is the process of creating a conceptual, logical, and physical structure to represent data and its relationships in a systematic way. It involves analyzing and organizing data entities, attributes, and their relationships to design a blueprint that supports efficient storage, retrieval, and management of information. Data modeling is critical for building robust data pipelines, enabling scalable data warehousing, and powering advanced analytics.

In this project, I used data from the https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page that contains detailed records of taxi trips, including pickup and drop-off locations, timestamps, fares, payment types, and more. This dataset is perfect for demonstrating data modeling techniques and designing a pipeline for analysis.

## Explanation of Entities in the Data Model
Before that you need to know about star schema vs snow flake schema.

**Star Schema**: A star schema is a simple and denormalized design with a central fact table connected directly to multiple dimension tables, forming a "star" shape.

**Snow Flake Schema**: A snowflake schema is a normalized design where dimension tables are further split into sub-dimension tables, forming a "snowflake" shape.

### Fact Table:
A fact table contains quantitative measures or metrics that are used for analysis.They typically contains foreign keys that link to dimension tables.They contains columns that have high cardinality and change frequently.They contains columns that are not useful for analysis by themselves but are necessary for calculating metrics

**Central table containing the core trip details such as:**

vendor_id: Identifies the vendor.

datetime_id: Links to the datetime_dim table.

pickup_location_id and drop_location_id: Reference the pickup and drop-off location dimensions.

Trip-specific metrics like fare_amount, tip_amount, total_amount, etc.

### Dimension Table:
A Dimension table contains columns that describes attributes of the data being analyzed.and they typically contains primary keys that link to fact tables.They contains columns that have low cardinality and dont change frequently,used for grouping or filtering data for analysis.

**Datetime Dimension (datetime_dim):**

Tracks temporal details of trips.

Attributes include pickup_datetime, dropoff_datetime, hour, day, month, year, and weekday.

**Pickup Location Dimension (pickup_location_dim):**

Contains geospatial data for pickup locations.

Attributes include pickup_latitude and pickup_longitude.

**Drop Location Dimension (drop_location_dim):**

Similar to pickup_location_dim but for drop-off locations.

Tracks drop_latitude and drop_longitude.

**Passenger Count Dimension (passenger_count_dim):**

Tracks the number of passengers in a trip.

Useful for analyzing trips by passenger groups.

**Trip Distance Dimension (trip_distance_dim):**

Represents trip distance categories.

Useful for categorizing and analyzing trips based on distance traveled.

**Rate Code Dimension (rate_code_dim):**

Represents different rate codes used for trips.

Attributes include rate_code_id and rate_code_name.

