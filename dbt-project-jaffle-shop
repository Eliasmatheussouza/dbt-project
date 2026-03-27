🚀 dbt-project — Analytics Engineering Portfolio

Project developed during the dbt Fundamentals course by dbt Labs, showcasing skills in data modeling, ELT transformation, and Analytics Engineering best practices.


📌 About the Project
This repository contains a data transformation pipeline built with dbt (data build tool), simulating the analytical environment of a fictional store (Jaffle Shop) integrated with Stripe payments.
The goal is to demonstrate the ability to structure data layers (staging → marts), ensure quality through testing, and document models in a professional manner.

🗂️ Project Structure
dbt-project/
├── models/
│   ├── staging/
│   │   ├── jaffle_shop/
│   │   │   ├── _src_jaffle_shop.yml        # Source definitions
│   │   │   ├── _stg_jaffle_shop.yml        # Model docs & tests
│   │   │   ├── _stg_jaffle_shop__customers.sql
│   │   │   └── _stg_jaffle_shop__orders.sql
│   │   └── stripe/
│   │       ├── _src_stripe.yml
│   │       └── _stg_stripe__payment.sql
│   └── marts/
│       ├── finance/
│       │   └── dim_customers.sql
│       └── marketing/
│           └── fact_orders.sql
├── seeds/
│   ├── jaffle_shop_customers.csv
│   ├── jaffle_shop_orders.csv
│   └── stripe_payments.csv
├── dbt_project.yml
└── packages.yml

🧱 Data Architecture
RAW (Seeds CSV)
      │
      ▼
┌─────────────┐     ┌──────────────────┐
│  jaffle_shop │     │     stripe        │
│  customers   │     │     payments      │
│  orders      │     │                  │
└──────┬───────┘     └────────┬─────────┘
       │                      │
       ▼                      ▼
  STAGING LAYER          STAGING LAYER
  stg_jaffle_shop__      stg_stripe__
  customers / orders     payment
       │                      │
       └──────────┬───────────┘
                  ▼
            MARTS LAYER
       ┌────────────────────┐
       │  dim_customers      │  ← customer lifetime value
       │  fact_orders        │  ← orders + payments joined
       └────────────────────┘

📊 Main Models
dim_customers (mart)
Customer dimension table with aggregated metrics:

Total orders per customer
Total amount spent (lifetime value)
First and last order dates

fact_orders (mart)
Orders fact table with:

Join between orders and payments
Amount paid per order (coalesce to handle nulls)
Order status and dates
