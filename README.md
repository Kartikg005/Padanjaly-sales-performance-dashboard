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

# Padanjaly Geographical Sales Performance Dashboard

## Project Overview

This project analyzes Padanjaly's geographical sales performance using Power BI Desktop and a cleaned WooCommerce order export. The dashboard explores sales and order distribution across countries, states/regions, and cities, helping identify strong markets, growth opportunities, and delivery patterns.

The analysis covers 690 orders across 269 cities, 73 states or regions, and 24 countries. India is the main market, with Kerala leading domestic order volume. Although international orders represent a smaller share of order volume, they contribute a substantial share of total order value.

## Dashboard KPIs

Total Cities: 269

Total States/Regions: 73

Total Countries: 24

Top Country Sales: ₹1.35M

## Dashboard Visuals

The single-page dashboard contains six visuals:

Sales by Country — Filled map showing sales distribution by country.

Sales by State/Region — Treemap highlighting the top 10 locations by sales.

Top 10 Cities by Orders — Clustered column chart comparing order volume.

Top 10 States by Orders — Clustered bar chart comparing order volume.

Billing City vs Shipping City — Donut chart showing whether the billing and shipping cities match.

India vs International Orders — Pie chart comparing domestic and international order counts.

## Key Insights

Kerala is the leading state, with 235 orders, followed by Maharashtra (73), Tamil Nadu (70), and Karnataka (68).

Bengaluru leads city-level order volume with 57 orders, followed by Hyderabad (33), Thiruvananthapuram (28), and Thrissur (27).

Billing and shipping cities match for 98.84% of orders (682 of 690), indicating strong location alignment.

Domestic orders account for 88.3% of order volume (609 orders), while international orders account for 11.7% (81 orders).

International orders contribute 46.5% of total order value. Their average order value is approximately ₹14,488, compared with ₹2,218 for domestic orders.

Sales are concentrated in Kerala, creating an opportunity to expand in other Indian states and develop international markets.

## Recommendations

Expand domestic marketing in Maharashtra, Tamil Nadu, Karnataka, and Telangana to reduce dependence on Kerala.

Develop high-value international markets through targeted campaigns and repeat-purchase initiatives.

Improve promotions and delivery performance in mid-tier cities such as Pune, Delhi, and Ernakulam.

Track international revenue, average order value, and repeat purchases by country.

Periodically review the small number of orders where billing and shipping cities differ.

## Business Conclusion

Padanjaly has a strong domestic base in Kerala, while international orders represent a significant revenue opportunity despite their lower volume. Expanding into additional Indian states and building repeatable international sales channels are the key opportunities identified by this dashboard.

## Sources

- Padanjali Ayurvedic (P) Ltd. About page: https://www.padanjaly.com/about-us/
- Padanjali Ayurvedic (P) Ltd. Home page: https://www.padanjaly.com/


# Product Performance & Demand Analysis | Power BI

## 📌 Project Overview

The **Product Performance & Demand Analysis Dashboard** is an interactive business intelligence project developed using Microsoft Power BI. It analyzes product-level sales performance, customer demand, revenue contribution, and monthly revenue trends to identify top-performing and low-performing products.

The dashboard provides actionable insights to support data-driven decision-making, improve product performance, and optimize sales strategies.

## 🎯 Project Objectives

* Analyze product-wise sales quantity and revenue.
* Identify top-performing and low-performing products.
* Evaluate revenue contribution across different products.
* Track annual revenue trends and identify changes in performance.
* Understand the relationship between sales volume and revenue.
* Provide actionable recommendations for improving business performance.

## 🛠️ Tools & Technologies

* **Microsoft Power BI Desktop** — Dashboard development and data visualization.
* **DAX (Data Analysis Expressions)** — KPI calculations and analytical measures.
* **Microsoft Excel** — Source data and data preparation.

## 📈 Key Performance Indicators (KPIs)

| KPI                             |                    Result |
| ------------------------------- | ------------------------: |
| Total Products                  |                        11 |
| Total Quantity Sold             | Approximately 1.08K units |
| Top Revenue-Generating Product  |           Agnijith 90 gms |
| Top-Selling Product by Quantity |           Agnijith 90 gms |

## 📊 Dashboard Visualizations

The dashboard combines KPI cards, comparison charts, a revenue trend chart, and an automated insights panel.

### 1. Products by Quantity Sold

* Compares the number of units sold across products.
* Identifies products with the highest and lowest demand.
* Highlights differences in demand across individual products and multipacks.

### 2. Product Revenue Analysis

* Compares revenue generated by individual products.
* Identifies the products contributing most to overall revenue.
* Highlights the revenue contribution of multipack products.

### 3. Monthly Revenue Trend

* Tracks revenue performance over time.
* Identifies periods of growth and decline.
* Supports the evaluation of changes in sales performance.

### 4. Revenue vs. Quantity Sold

* Examines the relationship between sales volume and revenue.
* Identifies high-volume, high-revenue products.
* Highlights products with relatively high sales volume but lower revenue.

### 5. KPI Cards

* Total Products
* Total Quantity Sold
* Top Product by Revenue
* Top Product by Quantity

## 🔍 Key Business Insights

1. **Top-Performing Product:** Agnijith 90 gms leads the product range with 508 units sold and approximately ₹1.24 million in revenue.

2. **Strong Customer Demand:** Agnihari 90gms ranks second in quantity sold, with 252 units.

3. **Total Product Sales:** The business offers 11 products, with approximately 1,080 units sold across the product range.

4. **Revenue Growth:** Revenue increased from ₹0.30 million in 2023 to ₹0.97 million in 2025.

5. **Revenue Decline:** Revenue decreased to ₹0.65 million in 2026, approximately 33% below the 2025 peak. The reporting period should be checked to determine whether 2026 represents a full year.

6. **Low-Demand Products:** Agnihari 10 Pack recorded only 1 unit sold, while Agnihari 5 Pack recorded 5 units, indicating opportunities to review demand and product positioning.


## 🧮 DAX Measures

The following DAX measures were used to calculate key performance indicators.

### Total Quantity Sold

```dax
Total Quantity Sold =
SUM('Book12'[Quantity])
```

### Total Products

```dax
Total Products =
DISTINCTCOUNT('Book12'[Product_name])
```

### Top Product by Revenue

```dax
Top Product =
CONCATENATEX(
    TOPN(
        1,
        VALUES(products[Product_name]),
        [Total Revenue (products)],
        DESC
    ),
    products[Product_name],
    ", "
)
```

### Top Product by Quantity

```dax
Top Quantity Product =
MAXX(
    TOPN(
        1,
        VALUES(products[Product_name]),
        [Total Quantity Sold],
        DESC
    ),
    products[Product_name]
)


*The filenames above illustrate a suggested repository structure. Include the dataset and Power BI file only if you intend to share them in your repository.*

## 🏁 Conclusion

The Product Performance & Demand Analysis Dashboard demonstrates how Power BI can transform sales data into meaningful business insights.

The analysis identifies Agnijith 90 gms as the leading product, highlights revenue growth through 2025, and reveals a decline in 2026 that requires further investigation. The findings support better inventory planning, product promotion, and revenue management.

**This project demonstrates practical skills in data visualization, DAX calculations, KPI development, business intelligence, and data-driven decision-making.**

## 👨‍💻 Skills Demonstrated

* Data Analysis
* Microsoft Power BI
* DAX Measures
* KPI Development
* Data Visualization
* Sales Performance Analysis
* Business Intelligence
* Insight Generation
* Business Recommendations


## Author

**Kartik**
Aspiring Data Analyst
[LinkedIn](www.linkedin.com/in/kartik-gv)

