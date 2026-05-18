🎬 Movie Ratings Analytics Platform

🚀 Scalable PySpark ETL Pipeline using Databricks & Delta Lake

📌 Project Overview

This project builds a production-grade data engineering pipeline to process and analyze movie ratings data at scale using PySpark on Databricks.

The pipeline ingests raw user ratings, cleans and transforms the data, performs analytical aggregations, and stores the results in Delta Lake for downstream analytics and reporting.

🎯 Business Problem

A movie streaming company collects millions of user ratings daily. The analytics team needs to:

Analyze user behavior Identify trending/popular movies Calculate average ratings Detect low-quality or corrupt records Generate datasets for dashboards Handle incremental data efficiently

🧱 Tech Stack

Databricks (Unified Analytics Platform) PySpark (Distributed Data Processing) Delta Lake (Storage Layer) Python

📂 Dataset Details

🎥 Movies Table

Column Description movie_id Unique movie ID movie_name Movie name genre Genre release_year Release year

⭐ Ratings Table

Column Description user_id Unique user ID movie_id Movie ID rating Rating (1–5) timestamp Rating timestamp

⚙️ Data Pipeline Architecture

            ┌──────────────────────┐
            │   Raw Ratings Data   │
            │   Raw Movies Data    │
            └──────────┬───────────┘
                       │
                       ▼
            ┌──────────────────────┐
            │   Bronze Layer       │
            │ (Raw Ingestion)      │
            └──────────┬───────────┘
                       │
                       ▼
            ┌──────────────────────┐
            │   Silver Layer       │
            │ Data Cleaning &      │
            │ Validation           │
            └──────────┬───────────┘
                       │
                       ▼
            ┌──────────────────────┐
            │   Data Enrichment    │
            │ (Join with Movies)   │
            └──────────┬───────────┘
                       │
                       ▼
            ┌──────────────────────┐
            │   Gold Layer         │
            │ Aggregations & KPIs  │
            └──────────┬───────────┘
                       │
                       ▼
            ┌──────────────────────┐
            │ Delta Lake Storage   │
            └──────────┬───────────┘
                       │
                       ▼
            ┌──────────────────────┐
            │ Dashboards / BI      │
            └──────────────────────┘
🔄 ETL Workflow

🟤 Bronze Layer (Raw Data)

Ingest raw ratings and movies datasets

⚪ Silver Layer (Data Cleaning)

Remove null ratings

Drop duplicate records

Validate rating range (1–5)

🟡 Data Enrichment

Join ratings with movie metadata

Add genre and movie details

🟢 Gold Layer (Analytics)

Average rating per movie

Trending movies (based on rating count)

Genre-level insights

Low-rated movie detection

📊 Key Transformations

Average Ratings Calculation

Trending Movies Identification

Genre-based Aggregation

Data Quality Filtering

💾 Data Storage

Stored using Delta Lake

👩‍💻 Author

Bipina Poudel
