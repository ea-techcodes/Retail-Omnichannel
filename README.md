## 🛍️ Omnichannel Sales Pipeline Project

A complete data engineering project that unifies sales data from **Shopify (e-commerce)** and **Walmart (in-store)** into a single PostgreSQL/Snowflake data warehouse. The pipeline is fully automated using **Airflow**, transformed using **dbt**, and visualized with **Google Looker Studio**.

---

# 🚀 Project Overview

A mid-sized retailer selling through both Shopify (online) and Walmart (in-store) needs to unify its sales data into a single data warehouse. This will allow the business to track revenue by channel, identify top-selling products, and better understand customer behavior. By automating data collection and analysis, the company can reduce manual work and improve decision-making. The end goal is a real-time, centralized analytics system that supports smarter pricing, promotions, and inventory planning.
---

## 🧱 Tech Stack

| Layer          | Tool                    |
| -------------- | ----------------------- |
| Orchestration  | Apache Airflow          |
| Data Warehouse | Snowflake or PostgreSQL |
| Transformation| dbt Core                |
| Visualization  | Google Looker Studio    |
| Data Sources   | Shopify JSON, Walmart CSV |

---

## 📦 Data Sources

### 1. Shopify E-commerce Data (JSON)
Simulated dataset containing:
- Order dates
- Customer info
- Product SKUs
- Quantity and revenue

### 2. Walmart In-store Data (CSV)
Historical dataset containing:
- Product categories
- Store locations
- Units sold and revenue

---

## 🧪 ETL Pipeline Architecture

### 1. **Extract & Load**
- Shopify (JSON) and Walmart (CSV) files ingested daily
- Data loaded into **Snowflake staging tables**

### 2. **Transform (dbt)**
- Clean & standardize both datasets (SKUs, dates, categories)
- Merge into a **star schema**:
  - Fact table: `sales_transactions`
  - Dimension tables: `products`, `stores`, `customers`, `dates`

### 3. **Visualize**
- Looker Studio dashboard connected to the warehouse
- Dynamic filters by:
  - Channel (Online vs In-Store)
  - Product
  - Store
  - Time range

---

## 📊 Key Performance Indicators (KPIs)

| KPI                            | Goal                             |
| ----------------------------- | -------------------------------- |
| ✅ Data Completeness           | No missing/mismatched records   |
| ⚡ ETL Runtime                 | < 5 minutes daily               |
| 📈 Dashboard Freshness        | Daily auto-refresh              |

---

## 🔍 Exploratory Data Analysis (EDA)

Key business questions explored before modeling:
- Which channel drives higher revenue?
- How do seasonal sales patterns differ?
- Are there popular product bundles?
- Which Walmart store locations perform best?

---

## 🧠 How It Works (Summary)

```mermaid
flowchart TD
    A[Shopify JSON] --> B[Snowflake Staging]
    C[Walmart CSV] --> B
    B --> D[dbt Transformations]
    D --> E[Star Schema]
    E --> F[Looker Studio Dashboard]
