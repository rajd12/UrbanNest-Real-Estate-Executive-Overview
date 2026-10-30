# 🏙️ UrbanNest | Real Estate Executive Overview

An interactive **Power BI** dashboard that gives UrbanNest's leadership a single-page view of property inventory, lead pipeline, sales performance and revenue across Indian cities.

![Dashboard Preview](images/dashboard.png)

---

## 📌 Project Overview

UrbanNest is a (fictional) real estate company operating across seven major Indian cities. Its sales and marketing data sits in separate tables: properties, leads and sales. This makes it hard to answer simple executive questions:

- How much revenue are we generating, and where does it come from?
- Which property types sell best?
- How healthy is the lead pipeline, and where are we losing leads?
- Is revenue seasonal?

This project cleans and models the data, then presents it in a one-page executive dashboard with slicers for **Year**, **City** and **Property Type**.

## 🎯 Objectives

1. Track headline KPIs (inventory, leads, sales, revenue, conversion) at a glance.
2. Identify top-performing cities and property categories.
3. Analyse the lead funnel and spot where leads drop off.
4. Understand monthly revenue trends and seasonality.
5. Let stakeholders slice the data by year, city and property type.

---

## 📊 Dashboard KPIs

| KPI | Value |
|---|---|
| Total Properties | 3.0K |
| Total Leads | 20K |
| Sold Properties | 1K |
| Total Sales (transactions) | 3K |
| Total Revenue | 62bn |
| Lead Conversion Rate | 6.16% |

## 🧩 Visuals Included

| Visual | Type | Purpose |
|---|---|---|
| KPI cards | Cards | Headline business metrics |
| Total Revenue by Month | Line chart | Revenue trend and seasonality |
| Total Leads by Lead_Status | Funnel chart | Pipeline health and drop-off |
| Total Sales by Property_Type | Donut chart | Sales mix across property categories |
| Total Revenue by City | Column chart | Geographic revenue distribution |
| Year / City / Property_Type | Slicers | Interactive filtering of every visual |

---

## 🔍 Key Insights

### 1. Revenue is heavily concentrated in Pune
- Pune generates about **25bn of the 62bn total (~40%)**, more than Mumbai and Bangalore combined (9bn each).
- The top three cities (Pune, Mumbai, Bangalore) contribute about **43bn (~69%)** of revenue.
- Hyderabad and Chennai add 6bn each, while Noida (4bn) and Gurgaon (3bn) are the smallest markets, together only ~11% of revenue.

### 2. Apartments dominate the sales mix
- **Apartments account for ~47.7% of sales**, almost half of all transactions.
- The rest of the mix: Plot (12.4%), Villa (10.1%), Office (9.9%), Row House (8.4%), Shop (7.6%) and Commercial Plot (3.9%).
- Residential types (Apartment, Plot, Villa, Row House) make up roughly **78–79%** of sales. The three commercial types together make up about **21%**.

### 3. The lead pipeline has a low conversion rate
- Of **20K leads, only ~1K (6.16%) convert**.
- **Lost leads are about 3K (~15%)**, which is three times the number of converted leads.
- **Site Visit is the largest stage (~4K leads)**, so many leads reach a visit but do not progress. Qualified (3K) and Contacted (3K) also hold large volumes.
- About 2K leads each sit in Negotiation and Booked, so these are the nearest-term revenue opportunities.

### 4. Revenue is fairly steady but seasonal
- Monthly revenue mostly stays between **~4.6bn and ~5.7bn**.
- Peaks appear around **March, May, August, October and December**.
- **April and July are soft months** (~4.6–4.7bn).
- **November is the lowest point (~4bn)**, roughly 25–30% below the peaks, followed by a sharp recovery in December.

### 5. Inventory sell-through is low
- With about **3.0K properties and ~1K sold**, roughly **one-third of inventory has been sold**.

> Values on the dashboard are rounded (K/bn), so the percentages above are approximate.

---

## 💡 Recommendations

- **Protect and replicate Pune's success.** Study what drives Pune (pricing, inventory, marketing) and apply it to Mumbai and Bangalore.
- **Grow the smaller markets** such as Noida and Gurgaon with targeted campaigns, or review whether the inventory there fits demand.
- **Fix the Site Visit drop-off.** Improve follow-up after visits with faster callbacks, better sales scripts and limited-time offers.
- **Re-engage lost leads.** Even a small recovery of the ~3K lost leads would add meaningful revenue.
- **Plan around seasonality.** Run launches or promotions before the April, July and November dips.
- **Rebalance the portfolio.** Apartments carry the business, so test demand for villas, row houses and commercial inventory before expanding them.

---

## 🛠️ Tools & Skills Used

- **Power BI Desktop**: report design, visuals, slicers, formatting
- **Power Query**: data cleaning, type handling, error handling, derived category columns
- **DAX**: KPI measures and calculated columns
- **Data modelling**: relationships between properties, leads and sales tables
- **Dashboard design**: KPI cards, funnel, donut, line and column charts with consistent theme

## 🧮 Example DAX Measures

> Illustrative only. Adjust table and column names to match your model.

```DAX
Total Properties = DISTINCTCOUNT(Properties[Property_ID])

Total Leads = COUNTROWS(Leads)

Sold Properties = DISTINCTCOUNT(Sales[Property_ID])

Total Sales = COUNTROWS(Sales)

Total Revenue = SUM(Sales[Sale_Price])

Lead Conversion Rate =
DIVIDE(
    CALCULATE(COUNTROWS(Leads), Leads[Lead_Status] = "Converted"),
    [Total Leads]
)
```

## 🔄 Data Preparation Steps

1. Imported the property, lead and sales datasets into Power BI.
2. Cleaned the data in Power Query: fixed data types, removed or replaced errors, and handled blanks.
3. Created derived category columns (for example price and area categories).
4. Built relationships between the tables.
5. Wrote DAX measures for the KPIs.
6. Designed the dashboard layout and added Year, City and Property_Type slicers.

---

## 📁 Repository Structure

```
UrbanNest-Real-Estate-Dashboard/
│
├── UrbanNest_Real_Estate.pbix     # Power BI report file
├── data/                          # Source datasets (CSV/Excel)
├── images/
│   └── dashboard.png              # Dashboard screenshot
└── README.md
```

## ▶️ How to Use

1. Clone or download this repository.
2. Open `UrbanNest_Real_Estate.pbix` in **Power BI Desktop**.
3. Use the **Year**, **City** and **Property_Type** slicers to explore the data.
4. Click any chart element (for example a city bar or a funnel stage) to cross-filter the other visuals.


## 👤 Author

Raj Dahiwadkar
Data Analyst

- GitHub: [github.com/rajd12](https://github.com/rajd12)
- LinkedIn: [linkedin.com/in/rajdahiwadkar](https://www.linkedin.com/in/rajdahiwadkar)

---

⭐ If you found this project useful, consider giving the repo a star.
