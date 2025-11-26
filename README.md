# Snowflake Retail Analytics & AI Project (UCI Online Retail II)

End-to-end data engineering & analytics project built on **Snowflake AI Data Cloud** using a **Bronze–Silver–Gold** architecture.  
The project ingests raw retail transactions from the **UCI Online Retail II** dataset (Kaggle), transforms them into curated analytical layers, and enables **BI dashboards** and **AI/ML features** using **Snowpark** and **Cortex AI**.

---

## 🚀 Project Goals

- Build a **production-style data pipeline** in Snowflake (from raw to curated).
- Design **Bronze–Silver–Gold** layers for retail analytics.
- Deliver **business-ready views** for KPIs like:
  - Sales by country / customer segment  
  - Monthly revenue trends  
  - Top products & repeat customers  
- (Optional) Add **AI & ML**:
  - Demand forecasting with **Snowpark ML**
  - Text insights / summaries using **Cortex AI**

---

## 🧱 Architecture Overview

**Layers**

- **Bronze (Raw Layer)**  
  - Directly holds ingested CSV/Parquet from UCI Online Retail II.  
  - Minimal transformations, mainly data type & basic quality checks.

- **Silver (Cleaned & Modeled Layer)**  
  - Cleaned tables with:
    - Validated data types  
    - Removed invalid rows (negative quantities, bad invoices, etc.)  
    - Standardized dates & currencies  
  - Dimensional structures start here (e.g., `dim_customer`, `dim_product`, `fact_sales`).

- **Gold (Analytics & KPI Layer)**  
  - Business-friendly tables & views:
    - `sales_kpi_monthly`
    - `top_customers`
    - `product_performance`
  - Directly consumable by BI tools (Power BI, Tableau, etc.)

---

## 🛠️ Tech Stack

- **Cloud Warehouse:** Snowflake (Standard/Enterprise, Trial is fine)
- **Compute:** Virtual Warehouses in Snowflake
- **Data Processing:**
  - Snowflake SQL
  - Snowpark (Python) – optional, for ML / complex logic
  - Cortex AI – optional, for AI text features
- **Orchestration (Optional):**
  - Snowflake Tasks & Streams
  - Or any external scheduler (Airflow, ADF, etc. – not required for core project)
- **Visualization (Optional):**
  - Power BI / Tableau / Streamlit / Snowsight Dashboards

---

## 📦 Dataset

**Dataset:** UCI Online Retail II – available on Kaggle  
- **Source:** Kaggle → “UCI Online Retail II Data Set”  
- **Description:**  
  - Transactions from a UK-based online retailer  
  - Fields like `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`
- **Use in this project:**
  - Base for all sales & customer analytics
  - Perfect for demonstrating real-world retail KPIs

---

## 📁 Project Structure

Example repo layout:

```bash
snowflake-retail-ai-project/
├─ README.md
├─ sql/
│  ├─ 01_create_objects.sql         # Warehouses, DB, Schemas
│  ├─ 02_stage_and_file_format.sql  # Stages, file formats
│  ├─ 03_bronze_load.sql            # Load raw data
│  ├─ 04_silver_transform.sql       # Cleansing & modeling
│  ├─ 05_gold_views.sql             # KPI views
├─ snowpark/
│  ├─ retail_forecast_snowpark.py   # Example Snowpark ML script
│  ├─ requirements.txt
├─ data_sample/
│  ├─ online_retail_II_sample.csv
└─ docs/
   ├─ architecture-diagram.png
   └─ kpi-definitions.md
