# 🔋 EV Sales Dashboard — Power BI

> An interactive Power BI dashboard analysing global Electric Vehicle (EV) sales trends across countries, powertrain categories, and years — built to uncover growth patterns and year-over-year performance in the rapidly evolving EV market.

---

## 📊 Dashboard Preview

![EV Sales Dashboard](ev_dashboard_preview.png)

> 💡 **To interact with the dashboard:** Download `EVSales.pbix` and open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).

---

## 📌 Project Overview

The global electric vehicle market has been one of the fastest-growing sectors in the automotive industry. This dashboard was built to make sense of that growth — tracking how EV sales have evolved across different regions, powertrain types, and time periods. Rather than just presenting raw numbers, the dashboard is designed to answer real questions: Which countries are leading adoption? Is growth accelerating or slowing down? How does this year compare to last?

The result is a single-page interactive report that lets you slice and explore the data from multiple angles without writing a single line of code.

---

## 📂 Dataset

| Field | Description |
|---|---|
| `year` | Year of EV sales record |
| `region_country` | Country or region of sale |
| `powertrain` | EV type — BEV, PHEV, HEV, FCEV etc. |
| `Total EV Sales` | Total number of EVs sold |
| `EV Sales Previous Year` | Previous year's sales figure for comparison |
| `EV YoY Growth %` | Year-over-year percentage growth in sales |

> **Source:** Sheet1 (embedded in the DataModel within the .pbix file)

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard design and data modelling |
| **Power Query** | Data transformation and cleaning |
| **DAX (Data Analysis Expressions)** | Calculated measures — YoY Growth %, Previous Year Sales |
| **Excel / CSV** | Source data format |

---

## 📐 Dashboard Structure

The dashboard is built on a single page — **EV Sales** — with a clean purple-themed layout designed for quick scanning and deep exploration.

### 🔢 KPI Cards (Top Row)
Three metric cards give an immediate snapshot of performance at a glance:

- **Total EV Sales** — Aggregate EV units sold for the selected filter combination
- **EV Sales Previous Year** — Prior year's baseline for direct comparison
- **EV YoY Growth %** — Percentage change from the previous year, calculated via DAX

These cards update dynamically as slicers are applied — making it easy to instantly see how any country or powertrain type is trending.

### 🎛️ Slicers / Filters (Left Panel)
Three interactive filters control what the entire dashboard displays:

- **Country / Region** — Dropdown slicer to select one or multiple countries
- **Year** — Range slider (Between mode) to select a specific year window
- **Categories (Powertrain)** — Multi-select filter for EV type: BEV, PHEV, HEV, FCEV etc.

All visuals on the page respond to these slicers simultaneously — so any combination of filters instantly updates every chart and KPI card.

### 📈 Line Chart (Top Right)
**Total EV Sales over Time**
- X-axis: Year
- Y-axis: Total EV Sales
- Shows the overall trajectory of EV adoption across the selected time period
- Markers enabled on each data point for precise reading
- Reveals acceleration phases, dips, and inflection points in adoption

### 📊 Combo Chart — Column + Line (Bottom Right)
**EV Sales by Country / Region**
- X-axis: Country / Region
- Y-axis: Total EV Sales
- Stacked column with line overlay for multi-dimensional comparison
- Allows side-by-side regional benchmarking — immediately shows which markets dominate

### 🍩 Donut Chart (Bottom Left)
**Sales Distribution by Powertrain Category**
- Segments: Each EV powertrain type (BEV, PHEV, HEV, FCEV etc.)
- Values: Total EV Sales per category
- Legend positioned on the right
- Shows the share of each technology type — useful for understanding which EV segment is driving overall growth

---

## 📐 DAX Measures Used

```dax
-- Year-over-Year Growth Percentage
EV YoY Growth % =
DIVIDE(
    [Total EV Sales] - [EV Sales Previous Year],
    [EV Sales Previous Year],
    0
) * 100

-- Previous Year Sales
EV Sales Previous Year =
CALCULATE(
    [Total EV Sales],
    SAMEPERIODLASTYEAR('Sheet1'[year])
)
```

These measures power the KPI cards and allow the dashboard to dynamically compare any filtered selection against its prior-year equivalent.

---

## 💡 Key Insights the Dashboard Reveals

- **Which countries lead global EV adoption** and by how large a margin compared to the rest
- **How YoY growth has changed** — whether the market is still accelerating or beginning to mature
- **Which powertrain type dominates** — BEV vs PHEV vs HEV vs FCEV market share breakdown
- **Year-range comparisons** — using the year slider to isolate specific periods (e.g. pre vs post-pandemic)
- **Regional performance benchmarking** — filtering by country to compare adoption pace across markets

---

## 🗂️ Project Structure

```
EV-Sales-PowerBI-Dashboard/
│
├── EVSales.pbix                  # Power BI report file (open in Power BI Desktop)
├── ev_dashboard_preview.png      # Dashboard screenshot for preview
└── README.md                     # Project documentation
```

---

## ▶️ How to Open and Use

**Step 1 — Download Power BI Desktop (free):**
```
https://powerbi.microsoft.com/desktop/
```

**Step 2 — Clone or download this repository:**
```bash
git clone https://github.com/Sky-paras/EV-Sales-PowerBI-Dashboard.git
```

**Step 3 — Open the file:**
```
Double-click EVSales.pbix
→ Opens directly in Power BI Desktop
```

**Step 4 — Interact:**
```
→ Use the Country/Region dropdown to filter by market
→ Drag the Year slider to select a time range
→ Click powertrain categories to isolate specific EV types
→ Hover over charts for exact values
→ Click a country bar to cross-filter all other visuals
```

---

## 🎨 Design Choices

- **Purple gradient theme** — chosen to give the dashboard a modern, tech-forward feel appropriate for an EV/clean energy topic
- **Single page layout** — keeps all insights visible at once without navigation overhead
- **KPI cards at the top** — follows the standard F-pattern reading flow; most important numbers seen first
- **Donut + Combo chart combination** — donut for composition (what type), combo chart for magnitude (how much and where)
- **Bold axis labels** — improves readability for presentation and screen-sharing scenarios

---

## 🙌 Acknowledgements

- Data sourced from publicly available EV sales records
- Built as part of a Data Analytics portfolio project
- Developed using **Power BI Desktop** with custom DAX measures

---

## 📬 Connect

If you'd like to discuss the dashboard design, suggest improvements, or collaborate on a data project — feel free to reach out.

> ⭐ If this project was useful or interesting, a star on GitHub helps others find it too.
