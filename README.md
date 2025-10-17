# Analyzing Real Estate Trends (Database Systems Project)

This project analyzes **Zillow’s open housing datasets** to explore how home sales, values, and forecast indices change across U.S. metro regions over time.  
It demonstrates end-to-end database design — from **data cleaning and schema creation** to **SQL-based analysis and forecasting.**

---

## Objectives
- Design a **normalized relational database** to store multi-source housing data.
- Clean and merge multiple Zillow datasets for market, sales, and forecast metrics.
- Execute **advanced SQL queries** to analyze market performance by region and time.
- Build **indexes and relationships** for query optimization.

---

## Tools & Technologies
| Category | Tools |
|-----------|-------|
| Database | PostgreSQL / MySQL |
| Query Language | SQL (DDL + DML + Analytical queries) |
| Data Cleaning | Excel / Python (Pandas) |
| Visualization | Matplotlib / Seaborn |
| Source | Zillow Open Data Portal |

---

## Database Design

- **Schema:** 4 normalized tables (`Sales`, `MarketIndex`, `Forecast`, `Region`)
- **Relationships:** One-to-many between `Region` and `Sales/Forecast`
- **Indexes:** On `RegionID` and `Month` for optimized time-series querying

---

## SQL Scripts

| File | Description |
|------|--------------|
| [`sql/DDL-Statements.txt`](sql/DDL-Statements.txt) | Database & Table creation scripts |
| [`sql/DML-Statements.txt`](sql/DML-Statements.txt) | Analytical queries + indexes + forecast trend analysis |

---

## Datasets
All datasets used in this project are available in the [`datasets/`](datasets/) directory.

- **Source:** The raw housing data was obtained from the [Zillow Housing Dataset on Kaggle](https://www.kaggle.com/datasets/zillow/zecon) and other publicly available Zillow resources.  
- **Description:** The dataset includes monthly home value indices, sales counts, market performance metrics, and forecast indicators for U.S. metro areas.  
- **Usage:** Raw data was cleaned, normalized, and imported into a relational database for querying and trend analysis.  

---

#### Folder Structure
- **`raw/`** → Original Zillow datasets downloaded for analysis.  
- **`cleaned/`** → Processed, formatted, and normalized datasets ready for database import.  

---
