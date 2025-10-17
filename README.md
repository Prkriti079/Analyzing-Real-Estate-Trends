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

## 🧩 SQL Scripts

| File | Description |
|------|--------------|
| [`sql/DDL-Statements.txt`](sql/DDL-Statements.txt) | Database & Table creation scripts |
| [`sql/DML-Statements.txt`](sql/DML-Statements.txt) | Analytical queries + indexes + forecast trend analysis |

Example queries:
```sql
-- Average Home Value by Region
SELECT region_name, ROUND(AVG(home_value), 2) AS avg_home_value
FROM sales
GROUP BY region_name
ORDER BY avg_home_value DESC;

-- Year-over-Year Growth
SELECT region_name,
       (MAX(home_value) - MIN(home_value)) / MIN(home_value) * 100 AS yoy_growth
FROM market_index

GROUP BY region_name;
