# Medallion Architecture Data Pipeline with DQ Framework & Star Schema Analytics

# 🚀 Project Overview
This project implements a complete, production‑grade data pipeline using the Medallion Architecture (Bronze → Silver → Gold) to transform raw operational data into trusted, analytics‑ready insights. It demonstrates modern analytics engineering best practices, including rule‑based data quality validation, quarantine logic, dimensional modeling, and the creation of business‑ready fact and dimension tables.
The pipeline ingests raw e‑commerce data (customers, products, orders, order items), validates it through a robust DQ framework, and models it into a clean star schema suitable for BI dashboards and KPI reporting.
# 🎯 Objective
The objective of this project is to design and implement an end‑to‑end data pipeline that ensures data reliability, transparency, and analytical usability. This includes:
• Enforcing data quality rules
• Capturing invalid records in quarantine tables
• Producing clean, deduplicated Silver‑layer entities
• Modeling a Gold‑layer star schema for analytics
• Preparing the foundation for KPIs, semantic modeling, and dashboards.
# 🏗️ Architecture
![Architecture Diagram](https://github.com/aetekpo/-databricks-medallion-architecture/blob/main/Medallion_Architecture.png?raw=true)
• Bronze: Raw ingested data
• Silver: Cleaned, validated, typed, deduplicated data
• Gold: Business‑ready star schema (facts + dimensions)
## 🛡️ Data Quality Framework
The Silver layer includes a comprehensive DQ system:
## ✔ Rule‑based validation
Each table has explicit rules (e.g., no null IDs, valid dates, positive quantities).
## ✔ Quarantine tables
Invalid rows are redirected into:
• quarantine_customers
• quarantine_products
• quarantine_orders
• quarantine_order_items
Each record includes:
• 	Original row (JSON)
• 	Rule name
• 	Failure reason
• 	Severity
• 	Timestamp
## ✔ Deduplication logic
CTEs identify duplicates using ROW_NUMBER() and quarantine all but the “best” record.
## ⭐ Gold Layer: Star Schema
The Gold layer contains a clean, analytics‑optimized star schema:
### Dimensions
• dim_customers
• dim_products
### Facts
•fact_orders
•fact_order_items
### Key Features
• Surrogate keys(customer_sk, product_sk)
• Conformed dimensions
• Clear grain definition
## 🧩 Technologies Used
• Databricks SQL
• Delta Lake
• Medallion Architecture
• Star Schema Modeling
• SQL Window Functions
• Data Quality & Validation Frameworks
## 🏁 Conclusion
This project delivers a fully functional analytics engineering pipeline that transforms raw data into trusted, business‑ready insights. With a strong data‑quality foundation, a clean star schema, and a scalable architecture, the system is ready for the next phase: defining KPIs, building a semantic layer, and designing dashboards that unlock real analytical value.


   




