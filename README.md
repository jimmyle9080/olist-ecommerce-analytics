# Brazilian E-Commerce (Olist) - Sales & Customer Analytics EDA

**Author:** Jimmy Le-Nguyen  
**GitHub:** [github.com/jimmyle9080](https://github.com/jimmyle9080)

## Overview

An end-to-end exploratory data analysis project built on the Brazilian E-Commerce Public Dataset by Olist. The dataset contains **99,441 real orders across 9 relational tables** spanning 2016-2018, covering customers, sellers, products, payments, reviews, and geolocation data.

This project demonstrates the ability to work with multi-table relational data, perform SQL joins and aggregations across normalized datasets, engineer meaningful business features, and deliver Power BI-ready analytical outputs -- skills directly applicable to data analyst, business analyst, and consulting roles.

## Key Business Findings

| Finding | Detail |
|---|---|
| Total orders | 99,441 across 2016-2018 |
| Revenue growth | Strong YoY growth from 2017 to 2018 |
| Top revenue category | Health & Beauty |
| Top revenue state | SP (São Paulo) |
| Most used payment type | Credit card |
| Avg review score | ~4.1 / 5.0 |
| Late delivery rate | ~8% of delivered orders |
| Peak order hour | Early afternoon |

## Dataset

- **Source:** [Kaggle - Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **9 relational tables** | **99,441 orders** | **2016-2018**

> Download all 9 CSV files from Kaggle and place them in the `data/` folder before running.

### Required Files
```
data/
├── olist_customers_dataset.csv
├── olist_geolocation_dataset.csv
├── olist_order_items_dataset.csv
├── olist_order_payments_dataset.csv
├── olist_order_reviews_dataset.csv
├── olist_orders_dataset.csv
├── olist_products_dataset.csv
├── olist_sellers_dataset.csv
└── product_category_name_translation.csv
```

## How to Run

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run everything (VS Code: just press the play button on main.py)
python main.py
```

## Project Structure

```
olist_project/
├── data/               # Kaggle CSVs (download separately)
├── outputs/
│   ├── charts/         # 6 professional visualizations
│   └── exports/        # Power BI-ready CSV exports
├── main.py             # Single entry point — run this
├── requirements.txt
└── README.md
```

## Outputs

### Charts (outputs/charts/)
| File | Description |
|---|---|
| 1_revenue_trends.png | Monthly revenue and order volume 2017-2018 |
| 2_category_analysis.png | Top 10 product categories by revenue and avg price |
| 3_payment_analysis.png | Payment type distribution and avg order value |
| 4_satisfaction_delivery.png | Review scores and delivery performance by state |
| 5_revenue_by_state.png | Revenue and satisfaction by customer state |
| 6_order_timing.png | Hourly and day-of-week order patterns |

### Power BI Exports (outputs/exports/)
| File | Description |
|---|---|
| orders_master.csv | Full joined dataset (99,441 orders) |
| customer_segments.csv | Customer segmentation by spend tier |
| monthly_revenue.csv | Monthly revenue trends 2017-2018 |
| revenue_by_state.csv | State-level revenue and satisfaction analysis |
| top_categories.csv | Top product categories by revenue |
| payment_type_analysis.csv | Payment behavior breakdown |
| delivery_performance.csv | Delivery KPIs by state |
| review_score_distribution.csv | Customer satisfaction breakdown |
| hourly_orders.csv | Order timing patterns |

## Technical Approach

### Multi-Table SQL Joins
This project works with 9 relational tables joined through a series of aggregations and merges:
- Orders joined to customers (customer demographics)
- Payments aggregated to one row per order
- Order items aggregated to order-level totals
- Reviews aggregated to order-level scores
- Products joined to category translation table

### Feature Engineering
- `delivery_days` -- actual days between purchase and delivery
- `delivery_delta` -- actual vs estimated delivery (positive = late)
- `delivered_late` -- binary flag for late deliveries
- `purchase_year/month/hour/dow` -- time-based features for trend analysis
- `customer_segment` -- spend-tier segmentation (Budget / Mid-tier / Premium / VIP)

### Customer Segmentation
Customers segmented by total lifetime spend:
- **Budget:** $0-100
- **Mid-tier:** $100-300
- **Premium:** $300-1,000
- **VIP:** $1,000+

## Skills Demonstrated

- **SQL** -- SQLite with multi-table joins, aggregations, window functions, GROUP BY
- **Python** -- Pandas multi-table merging, datetime parsing, feature engineering
- **EDA** -- Revenue trends, customer behavior, geographic analysis, satisfaction analysis
- **Data Modeling** -- Working with normalized relational schema across 9 tables
- **Business Storytelling** -- Translating transactional data into actionable insights
- **Power BI Integration** -- Structured CSV exports for live dashboard connection

## License

Dataset licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).  
Code: MIT License.
