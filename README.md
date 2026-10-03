# Receiving Quality Analytics

A Streamlit application that tracks inbound receiving issues and measures error rates against daily receiving volume.

> Built and deployed in my operations leadership role at a contract apparel decoration and fulfillment operation. Company, customer, and employee data have been removed.

## Problem

Receiving discrepancies (shorts, overages, damaged goods, and factory defects) were tracked on paper tags and spreadsheets. There was no way to measure an error rate, compare customers, or see whether problems were improving over time.

## Solution

A web application where the receiving team logs each problem tag with its SKU detail, records daily receiving volume as a baseline, and gets live analytics on error rates by customer, team, and month.

## Features

- **Problem tag submission:** multiple SKU lines per tag, with size, color match, and short or heavy status on each line
- **Short and heavy pairing:** links shortage and overage lines so offsetting errors are tracked correctly
- **Daily receiving baseline:** orders received and estimated units per day, used as the denominator for error rates
- **Analytics:** daily error rate, monthly trends, and error rate and error units by customer
- **Filtering:** by date range, production team, and customer
- **Admin:** manage customer and employee lists without touching code

## Key Metric

**Receiving error rate = error units / total units received**

## Tech Stack

- Python, Streamlit, Plotly
- SQLAlchemy with SQLite by default, PostgreSQL optional
- Relational schema: problem tags, tag line items, daily receiving data, customers, and employees

## Setup

1. Install dependencies:
```bash
   pip install -r requirements.txt
```
2. Run the app:
```bash
   streamlit run app.py
```

The app creates a local SQLite database (`receiving.db`) and its tables on first run. No database setup is required.

**Optional: PostgreSQL.** To use a hosted database instead, create `.streamlit/secrets.toml`:
```toml
db_url = "postgresql://USER:PASSWORD@HOST:PORT/DBNAME?sslmode=require"
```

## Author

Brandon Bell
