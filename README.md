# Online Retail Exploratory Data Analysis with Python

A portfolio project performing exploratory data analysis (EDA) on transactional
data from a UK-based online retail store, using Python, pandas, seaborn, and
Matplotlib.

## Case Study

The dataset contains transactions from a UK-based online retail store between
December 2010 and December 2011. Each row is a line item from a customer
invoice: the product purchased, quantity, unit price, timestamp, customer, and
country. The goal is to explore this data to understand sales trends, customer
behavior, and popular products, and to turn those patterns into data-driven
recommendations for the business.

## Contents

| File | Description |
|---|---|
| `online_retail.ipynb` | The EDA notebook: load, clean, explore, analyze, and summarize findings. |
| `online_retail.csv` | The dataset (~531k rows) used by the notebook. |
| `Task-by-Task Guide - Retail Data Analysis.pdf` | Step-by-step task guide/hints this project is based on. |

## Dataset

| Column | Description |
|---|---|
| `InvoiceNo` | Invoice number of the transaction |
| `StockCode` | Unique code of the product |
| `Description` | Description of the product |
| `Quantity` | Quantity of the product in the transaction |
| `InvoiceDate` | Date and time of the transaction |
| `UnitPrice` | Unit price of the product |
| `CustomerID` | Unique identifier of the customer (`0` marks a guest/unidentified customer) |
| `Country` | Country where the transaction occurred |

## What the notebook does

1. **Load the data** — read the CSV into a pandas DataFrame and take a first look.
2. **Clean the data** — parse `InvoiceDate`, drop duplicate rows, remove non-sales
   rows (zero/negative `UnitPrice`), and filter outliers in `Quantity` and
   `UnitPrice` using the IQR method.
3. **Explore basic statistics** — descriptive stats, mean/median/mode,
   variance/standard deviation for `Quantity`, `UnitPrice`, and `TotalPrice`.
4. **Analyze the data** — monthly revenue trend, busiest days of the week,
   top-selling products by quantity and revenue, revenue by country, most
   valuable customers, and a correlation heatmap.
5. **Findings and conclusions** — a written summary of the key insights (e.g.
   seasonality, top products, customer concentration).

## Getting started

Requirements: Python 3, `pandas`, `numpy`, `seaborn`, `matplotlib`, `jupyter`.

```bash
pip install pandas numpy seaborn matplotlib jupyter
jupyter notebook online_retail.ipynb
```

Run the cells in order — `online_retail.csv` must be in the same directory as
the notebook.

## Key findings

- **Sales are strongly seasonal**, climbing through the autumn and peaking in
  November ahead of the holiday season.
- **A small set of products drives a large share of demand** — items like the
  "WHITE HANGING HEART T-LIGHT HOLDER" and "JUMBO BAG RED RETROSPOT" are
  consistently top sellers by both quantity and revenue.
- **The UK dominates revenue**, with Germany, France, and Ireland (EIRE) as the
  next-largest markets by a wide margin.
- **Order volume matters more than unit price for revenue** — `Quantity`
  correlates with `TotalPrice` more strongly than `UnitPrice` does.
- **A meaningful share of transactions have no identified customer**
  (`CustomerID` encoded as `0`), limiting customer-level analysis for that
  portion of sales.
