# Olist Customer Analytics Pipeline

End-to-end ETL pipeline that extracts, cleans, and transforms 96K+ Brazilian 
e-commerce orders and visualizes insights in Tableau.

## Dashboard
[View Live Tableau Dashboard](https://public.tableau.com/shared/W4M2NYHCH)

## Code
[View Full Pipeline Notebook (Google Colab)](https://colab.research.google.com/drive/1hC441L1AwPbUfyMNnb0Hkc_QBFL0599m?usp=sharing)

## Project Overview
Built a complete data pipeline using the [Kaggle Olist dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) 
to simulate a real-world customer reporting workflow.

## Pipeline Architecture
Raw CSVs → Python (pandas) → Cleaned DataFrames → Exported CSVs → Tableau

## Tools & Technologies
- **Python** (pandas) — data extraction, cleaning, transformation
- **Tableau Public** — interactive dashboard and reporting
- **Google Colab** — development environment

## Data
- Source: Kaggle Olist Brazilian E-Commerce Dataset
- 96,475 delivered orders across 27 Brazilian states
- 8 relational CSV files merged into a single master dataframe

## Key Steps
1. Loaded and explored 8 CSV files (customers, orders, payments, items, etc.)
2. Cleaned data — converted date columns, filtered undelivered orders, removed nulls
3. Resolved duplication from multi-payment orders by aggregating to order level
4. Engineered features: delivery days, on-time status, order month/year
5. Built 3 analytical summary tables: customer summary, monthly trends, state summary
6. Exported cleaned datasets as CSVs and loaded directly into Tableau
7. Connected Tableau to exported data and built 3-visual dashboard

## Key Findings
- SP (São Paulo) accounts for ~40% of total revenue across all 27 states
- Orders grew 10x from Oct 2016 to Nov 2017 before stabilizing
- Average delivery time is 12 days with ~85% on-time rate nationally

## Files
- `Customer Data Pipeline.ipynb` — full ETL pipeline notebook
