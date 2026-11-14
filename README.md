# Olist Marketplace Analysis: Sales, Delivery and Customer Satisfaction

Exploratory data analysis of the public Olist Brazilian e-commerce dataset (about 100K orders, 2016–2018). The notebook cleans and joins nine tables, analyzes sales, customers, sellers, payments and reviews, and ends with business recommendations.

**Notebook:** [`olist_ecommerce_data.ipynb`](olist_ecommerce_data.ipynb)

## Business problem

Olist is a Brazilian marketplace: independent sellers list products, and orders are delivered through logistics partners. Olist does not own inventory or set prices, so growth depends on how much its sellers sell and how reliably orders are fulfilled.

The analysis takes the view of Olist's management and asks how to grow sales, improve delivery performance and raise customer satisfaction, separating what depends on customers, sellers and logistics.

## Key findings

The analysis covers 96,478 delivered orders (September 2016 – August 2018), BRL 13.22M GMV and 93,358 unique customers.

- **Growth has plateaued.** Monthly GMV grew from BRL 40K (Oct 2016) to BRL 0.86–0.98M by mid-2018 and has been flat since March 2018.
- **Demand is geographically concentrated.** Seven states generate 81% of GMV; São Paulo alone generates 38%.
- **Missed delivery dates are associated with much lower satisfaction.** Only 6.8% of delivered orders arrive late, yet the share of 1–2 star reviews rises from 9.2% for early orders to 41–79% for late ones. The gap also appears among orders of similar duration (21+ days: 66.5% low ratings for late vs 15.5% for on-time orders).
- **Retention is very low.** Only 3% of customers ordered more than once, so growth depends almost entirely on acquiring new customers.
- **Seller revenue is highly right-skewed.** The average seller generates BRL 4,452 but the median seller only BRL 846, which suggests that a small group of large sellers carries a disproportionate share of GMV (the exact share was not measured).
- **Installments are linked to larger baskets.** 51.5% of orders use installments; they have a 72% higher average order value and account for 65% of GMV.

The notebook turns these into six business recommendations: prioritize delivery-date reliability, enforce seller handover SLAs, investigate extreme delays, convert one-time buyers, grow strong categories and small sellers, and protect installment availability.

## What is in the notebook

1. **Data overview and cleaning:** schema, missing values, duplicates, outliers and type fixes for each of the nine tables.
2. **Data integration:** joining the tables into order-, customer- and seller-level datasets.
3. **Sales analysis:** GMV, order value, revenue trend, order composition, operational performance, order status.
4. **Customer analysis:** repeat purchases, revenue per customer, geographic concentration (Pareto analysis by state).
5. **Product and seller analysis:** category performance and seller distribution.
6. **Payment analysis:** payment methods, installments and their link to order value.
7. **Review analysis:** how delivery time and delivery delay relate to review scores (group comparisons, Kruskal-Wallis tests, same-duration comparison of late vs on-time orders).
8. **Conclusion, recommendations and limitations.**

## Tools

Python (pandas, NumPy, SciPy), Matplotlib and Seaborn for charts, Jupyter notebook.

## How to run

The notebook downloads the dataset automatically with [`kagglehub`](https://github.com/Kaggle/kagglehub), so the data files are not included in this repository. You need an internet connection, and Kaggle may ask you to log in.

```bash
pip install -r requirements.txt
jupyter notebook olist_ecommerce_data.ipynb
```

It also runs in Google Colab: upload the notebook and run all cells.

Dataset: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) on Kaggle. Please check the dataset's license on Kaggle before reusing the data.

## Limitations

- The dataset covers September 2016 – August 2018 and ends mid-month, so the final period is incomplete and excluded from trend charts.
- Order value is measured as GMV (item prices only). Olist's actual revenue (commissions and subscription fees) is not in the dataset, so profitability cannot be assessed.
- The data is observational: all relationships are associations, not proven causation.

## Author

Oleksandra Korostil, Data Analyst. [LinkedIn](https://www.linkedin.com/in/oleksandra-korostil/)
