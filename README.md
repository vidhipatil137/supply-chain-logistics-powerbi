# Supply Chain and Logistics Performance Dashboard

An interactive Power BI dashboard that shows where deliveries go wrong in a supply chain and what that means for sales and profit.

Built by **Vidhi Patil** using Power BI and the DataCo Smart Supply Chain dataset.

![Overview](images/overview.png)

## What this project is about

A company can sell a lot and still lose customers if orders arrive late. I wanted to build one dashboard that puts delivery performance, sales, profit, regions and products in the same place, so it is easy to see what is actually causing late deliveries.

The dashboard answers questions like:

- How many orders are delivered on time, and how many are late?
- Which shipping mode is the least reliable?
- Does the region of the customer change how often orders are late?
- Which products and categories make the most profit?
- How much profit comes from orders that were delivered late?

## Dashboard pages

**1. Overview**
Total sales, total orders, on-time delivery %, late delivery %, total profit, and how each one changed compared to last year. Also has the monthly sales trend, delivery status split, late % by shipping mode, top products by profit and orders by market.

**2. Delivery**
Average scheduled days vs average actual days, average delay on late orders, and cancel rate. Shows late % for each shipping mode, a region by shipping mode heatmap, and delivery status by quarter.

**3. Geography**
Sales by country on a map, the top 10 countries by sales, and the regions with the highest late %.

**4. Product and profit**
Total profit, profit margin, profit on late orders and average order value. Shows profit by category, sales vs profit by category, sales by department and the top 10 products.

Every page has filters for Year, Market, Shipping Mode and Customer Segment, plus a reset button and a navigation menu.

## Key numbers

| Metric | Value |
| --- | --- |
| Total sales | about $37M |
| Total orders | about 66K |
| Total profit | about $4M |
| Profit margin | 10.8% |
| Average order value | $559 |
| Late delivery % | 57.3% |
| On-time delivery % | 42.69% |
| Cancel rate | 4.3% |
| Average scheduled days | 2.93 |
| Average actual days | 3.5 |
| Average delay on late orders | 1.6 days |

## What I found

**Shipping mode is the real problem, not the region.**
Late % by shipping mode:

| Shipping mode | Late % |
| --- | --- |
| First Class | 100% |
| Second Class | 80.0% |
| Same Day | 48.4% |
| Standard Class | 39.8% |

First Class is the fastest and most expensive option, but in this data every First Class order was late. Standard Class, the slowest option, was late the least.

**Region barely matters.**
Late % is almost the same everywhere. The highest regions are Central Africa (60.0%), East Africa (59.1%) and South USA (58.8%), and the others are close behind at 58% to 58.5%. This tells me the delay comes from how orders are shipped, not from where they go.

**Orders take longer than promised.**
Orders are scheduled for 2.93 days on average but take 3.5 days. Late orders are about 1.6 days late.

**A big part of profit comes from late orders.**
About $2.1M of the $4M profit comes from orders that were delivered late. If those customers stop ordering, a lot of profit is at risk.

**Sales are concentrated in a few countries.**
The United States leads with about $4.9M in sales, followed by France ($2.9M), Mexico ($2.6M), Germany ($2.1M) and Australia ($1.7M).

**Products.**
Fishing is the most profitable category (about $0.76M profit). Fan Shop is the biggest department by sales (about $17M).

## Suggestions based on the data

These are my own takeaways from the dashboard, not something the dataset states.

- Look at the First Class promise. Its scheduled time is 1 day, but it is late every time, so either the promise or the process needs to change.
- Since late % is similar in every region, fixing shipping mode performance should help everywhere at once.
- Keep an eye on profit from late orders, because that is the profit most at risk.

## How late delivery % is calculated

Late delivery % is calculated on orders that were **not cancelled**. Cancelled orders are left out because they were never delivered. On-time delivery % is the rest (on time plus advance shipping). This is why the late % card shows 57.3%, while the delivery status donut chart, which includes cancelled orders, shows a slightly lower share for late delivery.

## Data

- Source: DataCo Smart Supply Chain dataset (Kaggle), about 180,000 order lines covering around 66,000 orders.
- The CSV file is about 96 MB, so I did not upload it here. Please download it from Kaggle.
- The data model has a fact table (`Fact_Orders`) and a date table (`Dim_Date`), with DAX measures kept in a separate `_Measures` table.

## How to open this project

1. Download `SupplyChain_Dashboard.pbix` from this repository.
2. Download the DataCo dataset from Kaggle and save it on your computer.
3. Open the .pbix file in Power BI Desktop.
4. If Power BI asks for the data, go to **Transform data > Data source settings** and point it to the CSV file you downloaded.
5. Click **Refresh**.

## Tools used

- Power BI Desktop
- DAX for measures
- Data modelling (fact and date tables)

## Screenshots

| Overview | Delivery |
| --- | --- |
| ![Overview](images/overview.png) | ![Delivery](images/delivery.png) |

| Geography | Product and profit |
| --- | --- |
| ![Geography](images/geography.png) | ![Product and profit](images/product-and-profit.png) |

## Connect

If you have feedback or ideas to improve this dashboard, feel free to reach out on LinkedIn.
