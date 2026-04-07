# Customer Analytics Pipeline & ML Model 

## Business Context
Supply chain teams rely on data to answer one critical question: *will this order arrive on time?*

Late deliveries drive up costs, damage supplier relationships, and erode customer satisfaction — all central concerns for purchasing and operations teams. This project simulates a real-world supply chain analytics workflow: building a production-grade ETL pipeline across 96K+ orders, engineering features that expose delivery risk, predicting late shipments using machine learning, and surfacing logistics inefficiencies by region and freight type through an executive dashboard.

The pipeline mirrors tools and techniques used in procurement and supply chain operations — ETL, predictive modeling, cloud data warehousing (Snowflake), and stakeholder-ready reporting (Tableau) — built to demonstrate end-to-end data engineering and analytics skills applicable to sourcing, procurement, and operations roles.

## Dashboard
[View Live Tableau Dashboard](https://public.tableau.com/shared/2M24HQPC8)

## Code
[View Full Pipeline Notebook (Google Colab)](https://colab.research.google.com/drive/1hC441L1AwPbUfyMNnb0Hkc_QBFL0599m?usp=sharing)

## Project Overview
Built a complete end-to-end supply chain analytics pipeline using the [Kaggle Olist Brazilian E-Commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) to simulate real-world procurement and logistics workflows. The project covers the full data lifecycle — raw ingestion and auditing across 8 relational CSV files, feature engineering, binary classification modeling, cloud warehousing in Snowflake, and executive dashboard reporting in Tableau.
Built to mirror the analytical processes supply chain and operations teams use to monitor delivery performance, diagnose sourcing risks, and support data-driven decisions — from a single reliable data foundation through to actionable findings.

## Pipeline Architecture
Raw CSVs → Python (pandas, NumPy) → EDA & Feature Engineering → scikit-learn ML Model → Snowflake → Tableau

## Tools & Technologies
- **Python** (pandas, NumPy, scikit-learn, Matplotlib, Seaborn) — ETL, modeling, visualization
- **Snowflake** — cloud data warehouse for storing analytical summary tables
- **Tableau Public** — interactive KPI dashboard and executive reporting
- **Google Colab** — development environment

## Data
- Source: Kaggle Olist Brazilian E-Commerce Dataset
- 96,475 delivered orders across 27 Brazilian states
- 8 relational CSV files merged into a single master dataframe

## ETL Pipeline

Building a reliable analytical foundation required careful auditing and cleaning before any modeling could begin:

1. Loaded and profiled 8 relational CSV files (customers, orders, payments, items, sellers, products, reviews, geolocation)
2. Audited data quality — identified and resolved null values, type mismatches, and duplicate records caused by multi-payment orders (aggregated to order level)
3. Filtered to delivered orders only; converted all date columns to datetime for accurate time calculations
4. Engineered features: delivery days, on-time binary flag, order month and year
5. Built 3 analytical summary tables: customer summary, monthly trends, state-level performance
6. Loaded all tables into Snowflake (OLIST_DB) via snowflake-connector-python
7. Exported CSVs for Tableau ingestion

## ML Model — Late Delivery Prediction

- **Problem:** Binary classification — will this order arrive late?
- **Features:** freight value, customer zip code, total payment, item count, order year
- **Models:** Logistic Regression and Random Forest (scikit-learn), 80/20 train-test split
- **Result:** 92% accuracy on held-out test set
- **Early-warning indicators:** Freight value and customer geography (zip code) emerged as the strongest predictors of late delivery — enabling earlier intervention before shipments are at risk

## Key Findings

- **Geography drives delay risk** — customer zip code is the top predictor of late delivery, with significant variation across Brazil's 27 states
- **Freight value signals risk** — higher freight costs correlate strongly with late delivery, surfacing a practical early-warning indicator for operations teams
- **São Paulo dominates volume** — SP accounts for ~40% of total revenue nationally
- **Rapid growth period** — order volume grew 10x between Oct 2016 and Nov 2017 before stabilizing
- **National baseline** — average delivery time is 12 days with an ~85% on-time rate across all states

## Files
- `Customer Analytics Pipeline & ML Model.ipynb` — full ETL, feature engineering, ML modeling, and Snowflake load pipeline


