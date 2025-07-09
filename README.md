Customer 360 Data Integration Project

A unified analytics pipeline that integrates customer data from multiple sources and builds actionable insights using Google Cloud and Tableau Public.

🚀 Project Overview

A retail business wants to build a comprehensive Customer 360 view. This includes data from online transactions, in-store purchases, loyalty programs, and customer support systems.

As data engineers, we developed an end-to-end pipeline using GCP tools to load, clean, aggregate, and visualize this data.

🛠️ Tools and Technologies

Google Cloud Storage (GCS) – Raw data storage

BigQuery – Staging (Silver) and Analytics (Gold) layers

Cloud Composer – (Optional) Data pipeline orchestration (Airflow)

Python – Loading data from GCS to BigQuery

SQL – Data cleaning and transformation

Tableau Public – Customer 360 dashboard

🧩 Architecture Diagram

(Insert Draw.io architecture diagram here if available)

📁 Folder Structure (in GitHub)

Customer360-Project/
├── DAGs/
│   └── ingest_to_bigquery.py
├── Scripts/
│   └── load_customer360_staging_data.py
├── SQL/
│   ├── Silver_Cleaning/
│   │   ├── clean_Customers.sql
│   │   ├── clean_Products.sql
│   │   └── ...
│   └── Gold_Aggregations/
│       ├── AverageOrderValue.sql
│       ├── CustomerSegments.sql
│       ├── ChannelActivityTrends.sql
│       └── AgentPerformanceSummary.sql
├── Dashboard/
│   └── tableau_public_link.txt
├── README.md

🔄 ETL Pipeline Process

✅ Step 1: Raw Data Upload

Uploaded CSVs from local system to GCS:

gsutil cp *.csv gs://bootcamp3-raw/

✅ Step 2: Staging Layer (Silver)

Created BigQuery dataset: customer360_silver

Loaded raw CSVs using Python and bq load logic

Cleaned and standardized using SQL (SAFE_CAST, TRIM, etc.)

✅ Step 3: Analytics Layer (Gold)

Created dataset: customer360_gold

Created 4 business-ready aggregate tables:

AverageOrderValue

CustomerSegments

ChannelActivityTrends

AgentPerformanceSummary

✅ Step 4: Dashboard

Built interactive visualizations on Tableau Public:

Dashboard URL: Customer 360 Dashboard (Tableau)

📊 Gold Table Definitions

Table Name

Purpose

AverageOrderValue

AOV by product, category, and store

CustomerSegments

Segments: High-Value, One-Time Buyers, Loyalty Champions

ChannelActivityTrends

Peak activity by channel, day, and time

AgentPerformanceSummary

Resolution rate and volume by support agents

✅ Validation & Quality Checks

Check Type

Performed

Notes

Data Ingestion

✅

GCS to BigQuery loads verified

Schema Conformance

✅

All columns cleaned with safe casting

Referential Integrity

✅

Joins between Customers, Orders, etc.

Dashboard Validation

✅

Compared output with mock sample data

📌 Final Notes

Cloud Composer DAG was Used

Project adheres to Data Vault 2.0 layering (Raw → Staging → Analytics)

Tableau Public used due to ease of access and sharing# Bootcamp-3
