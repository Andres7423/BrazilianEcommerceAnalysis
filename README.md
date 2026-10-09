# Brazilian E-Commerce Performance Analysis

End-to-end analysis of the Olist marketplace dataset: data cleaning, a layered pipeline (bronze / silver / gold), and business insights on revenue, customers, delivery, sellers and products.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/notebook/YOUR_NOTEBOOK.ipynb)

**Full report:** [`report/Brazilian_Ecommerce_Analysis_Report.pdf`](report/Brazilian_Ecommerce_Analysis_Report.pdf)

## Business questions

- How does revenue evolve over time, and how is it distributed across states, categories and customers?
- How can customers be segmented by loyalty?
- How reliable is delivery against the estimated date?
- Which sellers lead in revenue, order volume and review score?
- Which product categories lead on volume, and which are rated worst?

## Key findings

| Area | Finding |
|---|---|
| Revenue | R$15.2M from 95,118 delivered orders (Oct 2016 - Aug 2018) |
| Growth | Jan-Aug 2018 revenue is about 2.4x Jan-Aug 2017; monthly revenue plateaued around R$1.0M in 2018 |
| Seasonality | November 2017 peak of R$1.14M, up 55% on October |
| Retention | 97% of customers (89,330 of 92,071) bought only once |
| Geography | Sao Paulo = 37% of revenue; SP + RJ + MG = 63% |
| Delivery | 91.9% of orders arrived by the estimated date |
| Quality | Category review scores range from 4.67 (music CDs/DVDs) to 2.50 (insurance and services) |

## Approach

1. **Bronze layer:** load the 9 raw CSV files from Kaggle.
2. **Silver layer:** profile missing values and duplicates, standardise text and dates, de-duplicate items and payments, drop products without a category.
3. **Gold layer:** join orders, items, products, customers, payments, reviews and sellers into consolidated datasets, then compute revenue, segmentation, delivery and seller metrics.

## Repository structure

```
.
├── README.md
├── notebook/
│   └── YOUR_NOTEBOOK.ipynb
└── report/
    └── Brazilian_Ecommerce_Analysis_Report.pdf
```

## How to run

1. Click the **Open in Colab** badge above.
2. Run all cells. The dataset downloads automatically through `kagglehub`.

## Tools

Python, pandas, NumPy, Google Colab, Kaggle Hub

## Limitations and next steps

- Items were reduced to one row per order ID, which can understate multi-item orders (revenue comes from payments, so totals are largely unaffected).
- Recency should be measured against the last date in the dataset, enabling a full RFM model and an "At Risk" segment.
- Planned: delivery time vs. review score, seller revenue concentration (Pareto), smoothed category growth and an interactive dashboard (Power BI / Tableau).

## Data source

[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) on Kaggle. Please check the licence on the dataset page.

## Author

Andres Moncada | [www.linkedin.com/in/jerson-moncada-a67276219]
