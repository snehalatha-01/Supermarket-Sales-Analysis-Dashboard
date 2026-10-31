# Supermarket-Sales-Analysis-Dashboard
Two interactive Excel dashboards (Supermart Grocery Sales and Supermarket Sales Analysis) that turn raw retail data into filterable KPIs, charts and insights on sales, profit, categories, outlets and discounts. Built with formula-driven Excel (SUMIFS, COUNTIFS, INDEX/MATCH, dropdown filters) and no macros.
# Excel Sales Dashboards: Supermart Grocery & Supermarket Sales Analysis



| Dashboard | Dataset | Records | File |
|---|---|---|---|
| Supermart Grocery Sales Dashboard | Supermart Grocery Sales - Retail Analytics Dataset | 9,994 orders | `Supermart_Grocery_Sales_Dashboard.xlsx` |
| Supermarket Sales Analysis Dashboard | BlinkIT Grocery Data | 8,523 records | `Supermarket_Sales_Analysis_Dashboard.xlsx` |

---

## 1. Supermart Grocery Sales Dashboard

**Business question:** Which products, categories, discounts and locations drive sales and profit?

**Interactive filters:** Year, Region, Category (dropdowns on the Dashboard sheet).

**KPIs:** Total Sales, Total Profit, Profit Margin, Total Orders, Average Order Value, Average Discount.

| Objective | What is covered |
|---|---|
| 1. Overall sales performance | Total sales and profit, category share of sales, monthly trend, yearly sales and profit, sales by region |
| 2. Product performance | Sales vs profit by sub-category, top 5 sub-categories, watchlist of high-sales / below-average-margin sub-categories |
| 3. Profit and discount | Profit by category and region, sales/profit/margin by discount band, discount vs profit correlation |
| 4. Geographic performance | Top 10 cities, watchlist of high-sales / below-average-margin cities, state view |

**Headline findings (full dataset)**
- Total sales Rs. 14,956,982 and profit Rs. 3,747,121 (25.1% margin).
- Sales grew from about Rs. 2.98M (2015) to about Rs. 4.98M (2018).
- The seven categories are evenly balanced (13.6% to 15.2% of sales each).
- West and East are the leading regions; North has a single order.
- Discount has no meaningful relationship with profit (correlation about 0); margin stays near 25% in every discount band.
- All orders are in Tamil Nadu, so cities and regions are the useful geographic levels.

---

## 2. Supermarket Sales Analysis Dashboard

**Business question:** How do product categories and outlets perform, and how is sales distributed?

**Interactive filters:** Outlet Type, Outlet Location, Item Type.

**KPIs:** Total Sales, Average Sales per Record, Average Item Visibility, Records, Average Rating, Top-4 Category Share.

| Objective | What is covered |
|---|---|
| 1. Overall sales performance | Total sales, average sales per record, average visibility, sales by outlet size and location |
| 2. Category and sales comparison | Top 4 categories vs the rest, highest and lowest category, sales by outlet type and item type |
| 3. Outlet performance and relationships | Low Fat vs Regular sales per outlet, visibility vs sales, category share by outlet type (heat map) |
| 4. Statistical analysis | Mean, median, min, max, standard deviation, quartiles, IQR and z-score outliers, histogram, highest/lowest 5 records, average sales by category / outlet type / location |

**Headline findings (full dataset)**
- Total sales 1,201,681 across 8,523 records; average sales per record 140.99.
- The top 4 categories (Fruits and Vegetables, Snack Foods, Household, Frozen Foods) contribute 50.6% of sales. Seafood is the lowest category.
- Average sales per record is nearly identical across outlet types and location tiers; differences in totals come from record volume.
- Visibility vs sales correlation is about -0.001 (no relationship).
- No record falls outside the 1.5 x IQR fences; 14 records lie beyond +/-2 standard deviations (threshold is editable).

---

## Workbook structure

Both workbooks use the same layout:

| Sheet | Purpose |
|---|---|
| `Dashboard` | KPI cards, filters, charts and key insights |
| `Analysis` | Calculation tables that feed the charts (live formulas) |
| `Data` | Source data plus helper columns (formulas) |
| `Lists` | Dropdown options for the filters |
| `Notes` | Assumptions and data-cleaning notes |

Everything is formula-driven (`SUMIFS`, `COUNTIFS`, `AVERAGEIFS`, `INDEX/MATCH`, `LARGE/SMALL`, `QUARTILE`, `CORREL`). Changing a dropdown recalculates the KPIs and charts. No macros are used.

## How to use

1. Download the `.xlsx` file(s) and open in Microsoft Excel (or LibreOffice Calc).
2. Use the yellow dropdown cells in row 4 of the `Dashboard` sheet to filter.
3. Details of each calculation are on the `Analysis` sheet.

## Assumptions and data notes

**Supermart**
- The `Order Date` column mixes two formats. Values with `/` are read as month/day/year; values with `-` are read as day-month-year. If the dash dates are actually month-day-year, the monthly trend would change (yearly totals would not).
- The dataset has no product/SKU field, so Sub-Category is used as the product level.
- "High sales, low profit" means sales above the median of the group and margin below the overall margin.
- Currency is not stated in the source; Rs. is assumed because all locations are in Tamil Nadu.

**BlinkIT / Supermarket**
- `Item Fat Content` had five spellings (Low Fat, low fat, LF, Regular, reg); they are standardised to Low Fat / Regular.
- 526 records have zero Item Visibility, which is likely missing data. They are kept in totals and shown as a separate band; the correlation is also reported without them.
- `Item Weight` has 1,463 blanks; it is not used in any analysis.
- Summary statistics use the full dataset and ignore the dropdown filters.
- Sales currency/units are not stated in the source.

## Repository contents

```
.
|-- README.md
|-- Supermart_Grocery_Sales_Dashboard.xlsx
|-- Supermarket_Sales_Analysis_Dashboard.xlsx
|-- data/          (optional: original datasets)

```

## Tools

Microsoft Excel (formulas, charts, data validation, conditional formatting)
