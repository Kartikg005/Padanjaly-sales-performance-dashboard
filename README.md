# Jagadha by Padanjaly: Sales Analysis (Power BI)

An end-to-end sales analysis of **Jagadha by Padanjali Ayurvedic Private Limited (Padanjaly)**, an Ayurvedic provider specialising in burns, scars and non-healing wounds. The project covers the company profile, a dataset review, data cleaning in Power Query, and an exploratory sales dashboard built in Power BI, followed by insights and recommendations.

## Project Overview

| Item | Details |
| --- | --- |
| **Data source** | WooCommerce orders export |
| **Period** | January 2023 to May 2026 |
| **Size** | 690 orders, 72 columns |
| **Tools** | Power BI, Power Query, DAX |
| **Output** | Interactive dashboard and written analysis report |

## Business Questions

- Which products drive the most revenue?
- Do customers buy single jars or full treatment courses?
- How seasonal are sales?
- How do customers pay, and how reliable is the checkout flow?
- How much revenue comes from overseas orders?
- Is the order-status data trustworthy?

## Data Preparation

The raw data was left untouched. All cleaning was done on a separate copy in Power Query, so every step is repeatable.

- **Types and dates:** corrected data types and split order and paid date-times into separate date and time columns.
- **Currency:** the dataset mixes USD and INR, so each USD order was converted to rupees at the exchange rate of its order date.
- **Products:** split the packed line-item text into name, SKU, quantity and total, and decoded special codes.
- **Locations:** checked billing and shipping city, state and country against postcodes and saved them as new verified columns.
- **Nulls and zeros kept on purpose:** a blank paid date means unpaid, a blank item 2 means a single-product order, and zero tax and discount columns confirm no tax or discounts.
- **Customers:** flagged guest orders (`customer_id = 0`) with a `customer_type` column and removed 2 duplicates.

## Dashboard

The Power BI dashboard has five KPI cards and four visuals:

- Monthly revenue line chart
- Top 10 products bar chart
- Order status donut chart
- Payment method donut chart

| KPI | Value |
| --- | --- |
| Total Orders | 690 |
| Total Sales (INR orders) | ₹1.35M |
| Total Sales (USD orders) | $13.45K (about ₹1.2M converted) |
| Average Sales per Order | ₹3.66K |
| Total Products Sold | 1.08K (about 1.6 units per order) |

> Overall sales come to roughly ₹2.5M. The converted USD figure is an estimate and should be confirmed with a converted-total card in Power BI.


## Key Insights

1. **Agnijith drives about half of sales.** Agnijith 90 g earns ₹1.26M of the ₹2.51M in the top 10 (50%). Including its multi-packs, the Agnijith range reaches about 79%.
2. **Customers buy treatment courses.** The 2, 3 and 5-packs bring in about 29% of top 10 sales, and buying is driven by need rather than discounts.
3. **Sales are seasonal.** April to July and October are the strongest periods. October is the peak month (₹0.31M), and November falls about 55% below it.
4. **Payments are almost entirely online.** Razorpay handles 684 orders (99.13%) and cash on delivery only 6 (0.87%).
5. **41% of orders are still "processing".** 285 of 690 orders are likely outdated statuses rather than real delays.
6. **Overseas orders are a large share of revenue.** USD orders make up about 46% of estimated total sales.

## Recommendations

- Protect Agnijith stock and build doctor-linked course packs with refill reminders.
- Cross-sell Agnihari, Kasmeerini and Kadambini to raise units per order.
- Plan stock and campaigns around the April to July and October peaks.
- Fix the order-status workflow so "processing" reflects real delays.
- Keep Razorpay reliable and track overseas sales by country.

## Suggested Dashboard Improvements

- Merge product-name variants (for example "Agnihari, 90gms" and "Agnihari 90gms").
- Relabel the top 10 chart to make clear whether it shows sales value or quantity.
- Align the Average Sales per Order definition with its DAX note.
- Add a year slicer and a guest vs registered customer view.


*Adjust the folders above to match your actual repository.*

## How to Use

1. Clone this repository.
2. Open the `.pbix` file in Power BI Desktop.
3. If the data source path breaks, update it under **Transform data → Data source settings**.
4. Read the full report in the `report/` folder for the complete analysis.

## Notes and Limitations

- Company claims (testing, recognition, licences, leadership) come from the company presentation and are not independently verified, so they are treated as background only.
- Monthly totals add each month across years: January to May include 2026 (four years) while June to December cover three years.
- Retail sales in the UAE are outside this dataset.

## Author

**Kartik**
Aspiring Data Analyst | Python, SQL, Power BI, Excel
[LinkedIn](www.linkedin.com/in/kartik-gv)

## Sources

- Padanjali Ayurvedic (P) Ltd. About page: https://www.padanjaly.com/about-us/
- Padanjali Ayurvedic (P) Ltd. Home page: https://www.padanjaly.com/
