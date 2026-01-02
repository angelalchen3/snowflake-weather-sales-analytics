# Snowflake Weather & Sales Analytics Pipeline

## Overview
This project implements an end-to-end analytics pipeline on Snowflake that ingests raw POS and customer data from S3, enriches it with third-party weather data, and delivers interactive insights using Snowpark and Streamlit. The pipeline follows a layered data model designed for scalable analytics.

## Architecture
**Ingest → Transform → Deliver**

- **Ingest:** Raw CSV data loaded from S3 using Snowflake stages and `COPY INTO`
- **Transform:** SQL- and Snowpark-based transformations across raw, harmonized, and analytics schemas
- **Enrich:** Weather data integrated via a Snowflake Marketplace dataset
- **Deliver:** Interactive Streamlit dashboard powered by Snowpark

## Data Model
- **raw_pos / raw_customer:** Raw POS, order, and customer data  
- **harmonized:** Business-ready views combining sales, customer, and weather data  
- **analytics:** Final analytical views and reusable SQL UDFs  

## Key Features
- Bulk ingestion from S3 using Snowflake external stages  
- Layered data modeling (raw, harmonized, analytics)  
- Complex SQL joins and aggregations for order-level analytics  
- Data enrichment with third-party weather data  
- Snowpark (Python) transformations executed inside Snowflake  
- SQL UDFs for temperature and precipitation normalization  
- Interactive Streamlit dashboard with Altair visualizations  

## Technologies Used
- Snowflake (SQL, Snowpark)  
- Python (Snowpark, pandas)  
- Streamlit  
- Altair  
- AWS S3  

## Repository Structure
snowflake-weather-sales-analytics/
├── sql/
│   ├── ingestion_and_tables.sql
│   ├── harmonized_views.sql
│   ├── analytics_views.sql
│   └── udfs.sql
├── snowpark/
│   └── windspeed_hamburg_snowpark.ipynb
├── streamlit/
│   └── app.py
└── README.md
```


## How to Run
1. Execute the SQL scripts to create schemas, tables, views, and UDFs  
2. Run the Snowpark notebook to create derived weather views  
3. Launch the Streamlit app within Snowflake to explore sales and weather trends  

## Notes
This project emphasizes production-style analytics patterns, including layered data modeling, reusable transformations, and integrated data enrichment, rather than exploratory analysis.

## Acknowledgements
This project was inspired by Snowflake’s Tasty Bytes and Northstar analytics workshop materials. The implementation, organization, and extensions shown here reflect independent work adapted for portfolio presentation. The original repo can be found here: https://github.com/Snowflake-Labs/sfguide-snowflake-northstar-data-engineering

