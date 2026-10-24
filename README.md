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

Padanjaly Geographical Sales Performance Dashboard

📊 Project Overview

This project analyzes Padanjaly's geographical sales performance using Power BI Desktop and a cleaned WooCommerce order-export dataset. The dashboard explores sales and order distribution across countries, states/regions, and cities to identify leading markets, underperforming locations, and growth opportunities.

The analysis covers 269 cities, 73 states or regions, and 24 countries. India is the main market, with Kerala contributing the highest order volume. A small number of high-value international orders also contribute significantly to sales. fileciteturn0file0L4-L10

🎯 Project Objectives

Analyze sales by country, state/region, and city.

Identify high- and low-performing geographical locations.

Compare sales value with order volume.

Highlight regional growth opportunities.

Provide actionable recommendations for marketing and sales planning.

🛠️ Tools & Technologies

Power BI Desktop — dashboard creation and visualization

DAX — KPI measures and calculations

Power Query — data cleaning and preparation

Excel — source order-export data

📌 Dashboard KPIs

KPI

Description

Reported Value

Total Countries

Unique countries represented in the cleaned order data

24

Total States

Unique states or regions represented in the cleaned order data

73

Total Cities

Unique cities represented in the cleaned order data

269

Top Country Sales

Sales value for the leading country

₹1.35M

These values are reported in the project analysis. fileciteturn0file0L8-L16

📈 Dashboard Visuals

The report uses four main visuals:

Sales by Country — Filled Map
Shows the geographical distribution of sales by country.

Top 10 States by Sales — Treemap
Compares sales value across the leading states/regions.

Top 10 Cities by Orders — Clustered Column Chart
Highlights cities with the highest order counts.

Top 10 States by Orders — Clustered Bar Chart
Compares order volume across the leading states/regions.

The visuals use sales and order measures with Top N filtering where applicable. fileciteturn0file0L63-L69

🔍 Key Business Insights

Sales by Country (map)

Sales come from a small set of countries, and India is the main one. The Top Country Sales card shows ₹1.35M for the leading country, out of 24 countries in total.
The US, UK, Australia and Singapore also have sales, so the overseas business is spread across several markets. Those markets could be grown with targeted campaigns.

Top 10 States by Sales (treemap)

Kerala leads with ₹363K, but Singapore comes second with ₹211K from only 4 orders. That is about ₹53K per order, against roughly ₹1.5K per order in Kerala.
England (₹138K), Georgia (₹57K) and Texas (₹53K) also make the top 10 with only a handful of orders each. A few large overseas orders are worth more than many small local ones, so international bulk or high-value orders deserve attention.

Top 10 Cities by Orders

Bengaluru leads with 57 orders, followed by Hyderabad (33), Thiruvananthapuram (28) and Thrissur (27). Metro cities and Kerala towns drive most of the order volume.
Order counts drop quickly after the top few cities, from 57 to 14 across the top 10. Cities such as Pune, Delhi and Ernakulam, with 14 to 17 orders each, are good targets for delivery and marketing improvements.

Top 10 States by Orders

Kerala has 235 orders, more than three times the next state (Maharashtra, 73), so the business depends heavily on one state.
Maharashtra (73), Tamil Nadu (70) and Karnataka (68) form a close second tier. States from Gujarat down (17 to 14 orders) are far behind, which is the largest growth gap.

🧮 DAX Measures

The report documents the following KPI logic. Update the table and column names if they differ in your Power BI model.

Total Countries

Total Countries =
DISTINCTCOUNT(
    'padanjaly-order export cleaned'[billing_country_clean]
)

Total States

Total States =
DISTINCTCOUNT(
    'padanjaly-order export cleaned'[billing_state_clean]
)

Total Cities

Total Cities =
DISTINCTCOUNT(
    'padanjaly-order export cleaned'[billing_city_clean]
)

Top Country Sales

This measure assumes that a [Total sales] measure already exists.

Top Country Sales =
MAXX(
    VALUES(
        'padanjaly-order export cleaned'[billing_country_clean]
    ),
    CALCULATE([Total sales])
)


📝 Conclusion

Padanjaly has a strong sales and order base in Kerala, supported by order activity in major Indian cities and a smaller number of high-value overseas transactions. The key opportunities are to broaden domestic reach, strengthen mid-tier locations, and turn international high-value orders into repeatable business.


## Author

**Kartik**
Aspiring Data Analyst | Python, SQL, Power BI, Excel
[LinkedIn](www.linkedin.com/in/kartik-gv)

## Sources

- Padanjali Ayurvedic (P) Ltd. About page: https://www.padanjaly.com/about-us/
- Padanjali Ayurvedic (P) Ltd. Home page: https://www.padanjaly.com/
