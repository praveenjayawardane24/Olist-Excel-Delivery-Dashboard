# Olist Orders \& Delivery Dashboard

An Excel and Power Query portfolio project that turns monthly e-commerce order files into a dashboard for order volume, delivery performance, and recorded payments.

## What the dashboard shows

* Total orders, on-time delivery rate, average delivery days, and recorded payments in Brazilian reais (BRL).
* Two charts for order volume and on-time delivery by purchase month.
* Slicers for purchase month and customer state.
* A state comparison and an order lookup that traces a result back to the source file.

## Data and workflow

The source is the [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce). I used orders, customers, and payments. The monthly Excel workbooks are extracts from the historical orders CSV, prepared to simulate receiving a new file each month.

1. Split the orders CSV by purchase month and saved the extracts as Excel workbooks with the same headers and an `Orders\_Input` table.
2. Used Power Query to combine the monthly files, set data types, and check order IDs and delivery dates.
3. Joined customer locations by customer ID. Summed multiple payment rows by order ID before joining, so the output kept one row per order.
4. Calculated delivery outcomes and elapsed delivery time. An order delivered on the estimated calendar date counts as on time. The on-time rate uses orders with a valid on-time or late result.
5. Built an Excel formula summary, PivotTables, PivotCharts, slicers, KPI cards, and an XLOOKUP-based order lookup.

## Results and refresh test

|Purchase month|Orders|On-time rate|
|-|-:|-:|
|June 2018|6,167|98.84%|
|July 2018|6,292|96.62%|
|August 2018|6,512|93.81%|

I built the dashboard with June and July, then added the held-back August file. The total went from **12,459 to 18,971**. A second refresh with the same files kept the total at **18,971**.

## 

