# Tableau-Project
# 🚲 Adventure Works Sales Analytics: Tableau Dashboard

An interactive Tableau dashboard that turns Adventure Works sales data into clear insights on revenue, production cost, profit, seasonality, and top products, customers and regions. It covers **$29.4M in sales** across 5 years and 10 sales regions.



## 🎯 Business Problem

Sales, product, customer and territory data live in separate tables, which makes it hard to see the big picture. Decision-makers want to know:

- How much revenue and profit are we making, and what is our profit margin?
- How do sales change by year, quarter and month?
- Which products, customers and regions perform best?

## ✅ Goal of the Dashboard

To combine the data into one model and build a **Sales Performance Dashboard** that:

- Tracks sales, production cost, profit and profit margin
- Shows yearly trends and monthly seasonality
- Ranks the top 5 products, customers and regions
- Lets users click a product to filter the related views (dashboard action)

---

## 🛠️ Tech Stack

- 📊 **Tableau Desktop / Tableau Public**: visualization and dashboard design
- 🔗 **Data Connection**: Excel source with the sales tables combined using a **Union**, then joined to the dimension tables
- 🧮 **Calculated Fields**: date parts, full name, sales amount, production cost, profit and profit margin
- 🎚️ **Filters & Dashboard Actions**: interactive filtering across sheets
- 📈 **Mark types used**: bar, line and pie

## 🗂️ Data Model

| Table | Type | Contents |
|---|---|---|
| Sales (Union of two tables) | Fact | Combined sales order lines |
| `DimProduct` | Dimension | Product names and costs |
| `DimProdCategory` / `DimProdSubCategory` | Dimension | Product hierarchy |
| `Dimcustomer` | Dimension | Customer details |
| `DimDate` | Dimension | Calendar table |
| `DimSalesTerritory` | Dimension | Sales regions and countries |

## 🧮 Key Calculated Fields

```
Customer Full Name = TRIM([FirstName] + " " + IFNULL([MiddleName] + " ", "") + [LastName])
Order Date         = DATE(DATEPARSE("yyyyMMdd", STR([OrderDateKey])))
Sales Amount       = [Unit price] * [OrderQuantity] * (1 - [UnitPriceDiscountPct])
Production Cost    = [Unit Cost] * SUM([OrderQuantity])
Profit             = SUM([Sales Amount]) - [Production Cost]
```

Other calculated fields: year, month number, month name, quarter, year-month, weekday, financial month and financial quarter.

---

## 📊 Dashboard Walkthrough

The workbook has **15 worksheets** feeding one **Sales Performance Dashboard**:

- **KPI sheets**: Sales Amount, Production Cost, Profit and Profit Margin
- **Year Wise Sales**: sales growth by year
- **Sales Amount vs Production Cost**: revenue against cost by year
- **Month Wise Sales**: seasonality across the calendar year
- **Quarter-wise Sales Amount** (pie chart): share of sales by quarter
- **Top 5 Product / Customer / Region Sales**: ranked bar charts

## 💡 Key Insights

- **Total sales: $29.36M** with a production cost of **$17.28M**, giving a profit of **$12.08M** and a **41.1% profit margin**.
- **2013 was the peak year** at **$16.35M**. 2010 and 2014 contain only partial data.
- **Q4 is the strongest quarter** with about 31% of sales, and **December is the top month** at $3.21M.
- **Australia is the #1 region** with $9.06M (about 31% of sales).
- **All top 5 products are Mountain-200 bikes**, and sales are spread widely across customers, with no single buyer above about $43K.

## 📈 Business Impact

- **Planning:** build inventory and staffing around the Q4 peak.
- **Product focus:** the Mountain-200 series carries the business.
- **Market focus:** Australia and the US West are the main revenue drivers.

---

## 📁 Repository Files

- `Tableau_Project.twbx`: Tableau packaged workbook
- `dashboard.png`: dashboard preview

## 🧠 Skills Demonstrated

Data blending (union and joins) • Calculated fields • Dashboard actions • Data visualization • KPI design • Business storytelling

## 📊 Dashboard Image



**🔗 Live Dashboard:** [View on Tableau Public](https://github.com/srs97023-rgb/Tableau-Project/blob/main/TABLEAU_%20PROJECT_ADVENTURE%20WORKS.twbx)

![Tableau Sales Performance Dashboard](https://github.com/srs97023-rgb/Tableau-Project/blob/main/Tableau_Dashboard_image.jpg)

---
