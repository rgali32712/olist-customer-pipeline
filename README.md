# Supply Chain Analytics: Delivery Performance & Risk Prediction 

## Business Context
Supply chain teams rely on data to answer one critical question: *will this order arrive on time?* 
Late deliveries drive up costs, damage supplier relationships, and hurt customer satisfaction — 
all key concerns for purchasing and operations teams.

This project simulates a real-world supply chain analytics workflow — analyzing delivery 
performance across 96K+ orders, predicting late shipments using machine learning, and surfacing 
logistics inefficiencies by region and freight type. The pipeline mirrors tools and techniques 
used in procurement and supply chain operations: ETL, predictive modeling, cloud data warehousing 
(Snowflake), and executive dashboards (Tableau).

Built to demonstrate end-to-end data engineering and supply chain analytics skills applicable 
to sourcing, procurement, and operations roles.

## Dashboard
[View Live Tableau Dashboard](https://public.tableau.com/shared/2M24HQPC8)

## Code
[View Full Pipeline Notebook (Google Colab)](https://colab.research.google.com/drive/1hC441L1AwPbUfyMNnb0Hkc_QBFL0599m?usp=sharing)

## Project Overview
Built a complete end-to-end supply chain analytics pipeline using the Kaggle Olist Brazilian (https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) E-Commerce Dataset to simulate real-world procurement and logistics workflows. The project covers the full data lifecycle — from raw data ingestion and cleaning, to predictive modeling and executive dashboard reporting — mirroring the analytical processes used by supply chain 
and purchasing teams to monitor delivery performance, identify sourcing risks, and support data-driven operations decisions.

## Pipeline Architecture
Raw CSVs → Python (pandas, NumPy) → EDA & Feature Engineering → scikit-learn ML Model → Snowflake → Tableau

## Tools & Technologies
- **Python** (pandas, NumPy, scikit-learn, Matplotlib, Seaborn) — data processing, modeling, visualization
- **Snowflake** — cloud data warehouse for storing analytical tables
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
4. Conducted EDA and engineered features: delivery days, on-time status, order month/year
5. Built 3 analytical summary tables: customer summary, monthly trends, state summary
6. Loaded all 3 tables into Snowflake (OLIST_DB) using snowflake-connector-python
7. Built late delivery classification model using Logistic Regression + Random Forest
8. Exported CSVs and built interactive Tableau dashboard

## ML Model — Late Delivery Prediction
- **Target:** Whether an order will be delivered late (binary classification)
- **Features:** total payment, item count, freight value, customer zip code, order year
- **Models:** Logistic Regression, Random Forest (scikit-learn)
- **Accuracy:** 92% on held-out test set (80/20 split)
- **Key Finding:** Customer zip code and freight value are the strongest predictors of late delivery

## Key Findings
- SP (São Paulo) accounts for ~40% of total revenue across all 27 states
- Orders grew 10x from Oct 2016 to Nov 2017 before stabilizing
- Average delivery time is 12 days with ~85% on-time rate nationally
- Customer location (zip code) is the top predictor of late delivery

## Files
- `Supply_Chain_Delivery_Pipeline.ipynb` — full ETL + ML pipeline notebook
