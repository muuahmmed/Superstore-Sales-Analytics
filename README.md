# Superstore Sales Analytics

An end-to-end Excel analytics project built on a real-world retail dataset containing **9,994 orders** across **4 years** and **4 regions** in the United States.

---

## Dashboard Preview

### Executive Summary
![Executive Summary](https://raw.githubusercontent.com/muuahmmed/Superstore-Sales-Analytics/main/screens/Executive%20Summary.jpg)

### Product Performance Deep-Dive
![Product Analysis](https://raw.githubusercontent.com/muuahmmed/Superstore-Sales-Analytics/main/screens/Product%20Analysis.jpg)

### Customer & Logistics Insights
![Customer Insights](https://raw.githubusercontent.com/muuahmmed/Superstore-Sales-Analytics/main/screens/Customer%20Insights.jpg)

### Profitability Deep-Dive
![Profitability Analysis](https://raw.githubusercontent.com/muuahmmed/Superstore-Sales-Analytics/main/screens/PROFITABILITY%20ANALYSIS.jpg)

---

## The Data Problem

The raw dataset had a corrupted `Ship Date` column — dates were encoded using `0` as a delimiter instead of `/` or `-`, turning `November 11, 2016` into the number `1101102016`. Values appeared in 8, 9, or 10-digit formats depending on whether the month and day were single or double digits.

This was resolved in **Power Query** using custom parsing logic that strips the year from the last 4 digits, identifies the first zero as the month/day separator, and reconstructs a valid date — all without breaking any of the 9,994 rows.

---

## Data Model

Built in **Power Pivot** with 4 connected tables:

| Table | Description |
|---|---|
| `Orders` | Core transaction data — sales, profit, discount, quantity |
| `Return` | Returned orders with a Yes/blank flag |
| `People` | Regional sales managers mapped to regions |
| `Shipping Cost` | Shipping cost by ship mode |

**DAX Measures created:**

- Total Sales / Total Profit / Total COGS
- Profit Margin %
- Total Discount Value
- Profit per Order / Profit per Customer / AVG Profit
- Total Orders / Total Customers / Total Quantity
- Avg Ship Duration
- Returned Sales (with blank → "No" transformation)
- Profit % by Category

---

## Dashboard — 4 Pages

### Page 1 — Executive Summary
- KPIs: $2.3M Sales · $286K Profit · 29.1% Margin · 9,994 Orders · 37,873 Units
- Monthly Sales Trend (Line Chart)
- Sales by Category (Bar Chart)
- Top 5 States by Sales (Bar Chart)
- Ship Mode Contribution (Column Chart)

### Page 2 — Product Performance Deep-Dive
- KPIs: Top Category · Most Sold Sub-Category · Top Quantity · Profit per Order
- Sales vs Profit by Sub-Category (Combo Chart) — reveals that **Tables generate negative profit** despite strong revenue
- Top 10 Products by Sales (Bar Chart)
- Profit by Region (Donut Chart)
- Slicers: Region · Category · Segment

### Page 3 — Customer & Logistics Insights
- Top 10 Customers by Sales (Bar Chart)
- Segment Sales by Category (Stacked Bar Chart)
- Sales and Quantity by Date (Bar Chart with timeline slicers)
- AVG Ship Days per Ship Mode (Pie Chart)
- Top 5 Cities by Sales (Bar Chart)
- Sales by Regional Manager (Pie Chart)

### Page 4 — Profitability Deep-Dive
- KPIs: Total COGS · Total Discount · Returned Sales · Profit Margin %
- Top 10 States by Profit (Bar Chart)
- Most Loyal Customers — order frequency ranking (Bar Chart)
- Profit by Segment (Donut Chart)
- Discount vs Profit % by Category (Clustered Bar Chart)
- Returns Analysis: $180K returned · 7.8% of total sales (Donut Chart)

---

## Key Insights

- **Technology** leads all categories with **$836K** in sales and the highest profit margin
- **Tables** is the only sub-category generating **negative profit** (-$15K) despite $83K in sales
- **New York** is the top city at **$256K** in sales; **California** leads in state-level profit at **$76K**
- **William Brown** is the most loyal customer with **37 orders**
- **Standard Class** handles **60%** of all shipments (5,968 orders)
- **Consumer segment** drives **47%** of total revenue ($1.16M)
- **Furniture** carries the highest discount load relative to its profit return
- Returned orders account for **$180K** — roughly **7.8%** of total sales

---

## Tools Used

| Tool | Purpose |
|---|---|
| Power Query | Data cleaning · Date parsing · Null handling |
| Power Pivot | Data modeling · Table relationships |
| DAX | Custom measures and KPI calculations |
| Pivot Tables | Aggregation and summarization |
| Excel Charts | Data visualization across 4 dashboard pages |
| GETPIVOTDATA | Dynamic KPI card values |

---

## Project Structure

```
Superstore-Sales-Analytics/
├── README.md
├── data/
│   └── Project.xlsx
└── screens/
    ├── Executive Summary.jpg
    ├── Product Analysis.jpg
    ├── Customer Insights.jpg
    └── PROFITABILITY ANALYSIS.jpg
```

---

## Author

**Mohammed Magdy Ahmed**  
Data Analyst · Cairo, Egypt  
[LinkedIn](https://www.linkedin.com/in/mohammed-magdy-b8a37a1a8/) · [GitHub](https://github.com/muuahmmed)
