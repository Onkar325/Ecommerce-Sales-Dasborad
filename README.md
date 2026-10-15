# Ecommerce-Sales-Dasborad
![E-commerce Sales Dashboard](E-commerce%20Sales.jpeg)

# 🛒 E-Commerce Sales Dashboard

An interactive **Power BI dashboard** designed to analyze e-commerce sales performance, profitability, customer behavior, product returns, and sustainability metrics.

## 📌 Project Overview

The E-Commerce Sales Dashboard transforms raw sales data into meaningful business insights through interactive visualizations and key performance indicators (KPIs).

The dashboard helps businesses understand revenue trends, identify high-performing product categories, analyze customer purchasing patterns, investigate product returns, and track sustainability performance.

## 🎯 Project Objectives

- Analyze overall sales and profitability.
- Identify the best-performing product categories.
- Understand customer behavior across age groups and genders.
- Analyze product returns and their reasons.
- Compare payment methods and shipping preferences.
- Monitor sustainability metrics, including CO₂ savings and waste reduction.
- Support data-driven business decisions through interactive visualizations.

## 📊 Dataset Description

The project uses a CSV dataset containing **5,000 orders and 22 columns**.

The dataset includes the following information:

| Category | Attributes |
|---|---|
| Order Details | Order ID, Product, Date, Category, Price, Quantity |
| Customer Details | Age, Gender, Location |
| Payment & Shipping | Payment Method, Shipping Method |
| Returns | Return Status, Return Reason, Days to Return |
| Sustainability | CO₂ Emissions, CO₂ Saved, Packaging Waste, Waste Avoided |

## 📈 Key Performance Indicators (KPIs)

The dashboard displays the following KPIs:

| KPI | Reported Value | Description |
|---|---:|---|
| Total Revenue | 11.83M | Total revenue generated from orders |
| Total Orders | 5K | Total number of orders |
| Average Order Value | 2.37K | Average revenue per order |
| Total Profit | 11.54M | Reported profit after costs |
| Return Rate | ~29% | Proportion of orders returned |
| CO₂ Saved | 5.33K kg | Reported carbon emissions saved |

*Note: These are the values reported in the project summary. The currency and KPI calculation definitions should be confirmed against the underlying dataset and Power BI measures.*

## 📉 Dashboard Visualizations

The dashboard includes the following visualizations:

1. **Revenue by Product Category** — compares revenue across Clothing, Electronics, Toys, Books, and Home Appliances.
2. **Returned Orders by Reason** — identifies the most common reasons for product returns.
3. **Revenue by Gender and Discount Tier** — compares customer spending patterns across gender and discount groups.
4. **Orders by Age Group** — analyzes purchasing activity across customer age groups.
5. **Orders by Shipping Method** — compares Standard, Express, and Next-Day delivery preferences.
6. **Orders by Payment Method** — analyzes the distribution of Wallet, Debit Card, Credit Card, and Cash on Delivery orders.
7. **Orders and Revenue by Month** — examines monthly sales trends.
8. **Revenue by Location** — compares revenue across different cities.
9. **CO₂ Offset Ratio Gauge** — visualizes sustainability performance.

## 💡 Key Business Insights

### 1. Product Category Performance
Clothing is the leading revenue-generating category, followed by Electronics, Toys, Books, and Home Appliances.

### 2. Product Returns
Defective products are the most common reason for returns, suggesting an opportunity to improve quality control and product inspections.

### 3. Return Rate
The reported return rate is approximately 29%. Further analysis could identify the products, categories, and customer segments contributing most to returns.

### 4. Customer Purchasing Behavior
Customers aged 35–64 account for the highest order activity, while the 65+ age group has the lowest.

### 5. Shipping Preferences
Next-Day delivery is the most preferred shipping option, indicating that delivery speed may be important to customers.

### 6. Payment Methods
Orders are distributed relatively evenly across Wallet, Debit Card, Credit Card, and Cash on Delivery.

### 7. Sustainability
The dashboard reports 5.33K kg of CO₂ saved and a CO₂ offset ratio of 0.42, highlighting an opportunity to improve sustainability performance.

### 8. Monthly and Geographic Trends
Monthly sales remain relatively steady, with a slight decline from October to December. Revenue is also distributed relatively evenly across cities.

## 🛠️ Tools and Technologies

- **Microsoft Power BI** — interactive dashboards and data visualization.
- **Power Query** — data cleaning and transformation.
- **DAX (Data Analysis Expressions)** — KPI calculations and analytical measures.
- **CSV Dataset** — source data for analysis.
- **Business Intelligence** — identifying trends and generating actionable insights.

## 🧮 KPI Calculation Examples

The following are illustrative DAX measures. Adjust the table and column names to match the actual dataset.

**Total Revenue**
```dax
Total Revenue =
SUMX(
    Sales,
    Sales[Price] * Sales[Quantity]
)
```

**Total Orders**
```dax
Total Orders =
DISTINCTCOUNT(Sales[Order ID])
```

**Average Order Value**
```dax
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders],
    0
)
```

**Return Rate**

The following measure assumes that `Return Status` contains the value `"Returned"` and each order is counted once.

```dax
Returned Orders =
CALCULATE(
    DISTINCTCOUNT(Sales[Order ID]),
    Sales[Return Status] = "Returned"
)
```

```dax
Return Rate =
DIVIDE(
    [Returned Orders],
    [Total Orders],
    0
)
```

**CO₂ Offset Ratio**

Use this illustrative measure if the dataset contains CO₂ Saved and CO₂ Emissions columns.

```dax
CO2 Offset Ratio =
DIVIDE(
    SUM(Sales[CO2 Saved]),
    SUM(Sales[CO2 Emissions]),
    0
)
```

*Important: Confirm whether the source columns represent order-level values or unique totals before using these measures. The exact implementation may differ from the original dashboard.*

## 🚀 Future Improvements

- Add year-over-year and month-over-month comparisons.
- Develop predictive models to identify orders with a high return risk.
- Create drill-through pages for individual product categories.
- Add customer segmentation and purchasing behavior analysis.
- Investigate defective products and return patterns in greater detail.
- Introduce more detailed sustainability metrics and trend analysis.
- Improve interactive filtering and dashboard navigation.

## 📁 Suggested Repository Structure

Organize your GitHub repository as follows, adapting the filenames to match the files you actually have:

```text
Ecommerce-Sales-Dashboard/
│
├── README.md
├── data/
│   └── ecommerce_sales.csv
├── dashboard/
│   └── Ecommerce_Sales_Dashboard.pbix
├── screenshots/
│   └── dashboard_overview.png
└── docs/
    └── project_documentation.pdf
```

## ▶️ How to Use the Project

1. Clone or download this GitHub repository.
2. Open the `.pbix` dashboard file using Microsoft Power BI Desktop.
3. If required, update the dataset path in Power Query.
4. Refresh the dataset.
5. Explore the dashboard using the available filters and visualizations.

## 👨‍💻 Skills Demonstrated

- Data cleaning and transformation
- Data modeling and DAX calculations
- KPI development
- Interactive dashboard design
- Exploratory data analysis
- Business intelligence and analytical thinking
- Data-driven decision-making

## 📌 Conclusion

The E-Commerce Sales Dashboard demonstrates how Power BI can transform raw e-commerce data into an interactive business intelligence solution. By combining sales, profitability, customer behavior, product returns, and sustainability metrics, the project provides a consolidated view of business performance and highlights areas for further investigation and improvement.

---

**Project:** E-Commerce Sales Dashboard  
**Domain:** Data Analytics / Business Intelligence  
**Primary Tool:** Microsoft Power BI  
**Repository:** Ecommerce-Sales-Dashboard
