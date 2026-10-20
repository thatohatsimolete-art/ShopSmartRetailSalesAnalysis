# Week 1 — ShopSmart Retail Sales Analysis (Mission 01)

**Intern:** Kgothatso Molete  |  **Track:** Data Analytics, AnalystLab Africa  |  **Tools:** Microsoft Excel

## Files
| File | Purpose |
|---|---|
| `ShopSmart_Analysis.xlsx` | Main workbook: cleaned data (Excel Tables), formulas, lookups, 12 PivotTables, charts, interactive dashboard, business answers |
| `Executive_Dashboard.pdf` | Static one-page dashboard (all filters set to "All") |
| `Business_Report.pdf` | One-page report: 3 findings, 3 recommendations, 1 risk, 1 opportunity |
| `Data_Understanding.pdf` | Part 1 one-page explanation with ER diagram (also inside the workbook) |
| `Business_Report.docx`, `Data_Understanding.docx`, `Executive_Dashboard.docx` | Word versions of the same documents |

## Where each part lives in the workbook
| Part | Sheet(s) |
|---|---|
| 1 Data Understanding | `Data_Understanding` |
| 2 Data Cleaning | `Cleaning_Log` + data sheets (Excel Tables `tblOrders`, `tblCustomers`, ...) |
| 3 Formulas | `Formulas` |
| 4 Lookups | `Lookups`, plus green-header columns on `Orders` |
| 5 Pivot Tables | `Pivot_Tables` (12 PivotTables); same results as formulas on `Analysis` |
| 6 Charts | `Charts` |
| 7 Dashboard | `Dashboard` (7 drop-down filters: Year, Month, Region, Store, Category, Membership, Order Status) |
| 8 Business Questions | `Business_Answers` |
| 9 Recommendations | `Business_Report.pdf` |

## Key assumptions
- Revenue = sum of the recorded `Line_Total`, all order statuses included (use the dashboard Order Status filter for Completed-only).
- Currency assumed to be Naira (₦); the files do not state one.
- "Membership Level" = `Customers.Customer_Segment`.
- Supplier link is inferred: `Supplier_Name = Brand & " Supplies"`.
- Return rate = orders with at least one return / total orders.

## Headline results
Revenue ₦7.58bn · 50,000 orders · 5,000 customers · AOV ₦151.5K · return rate 4.9% · inventory ₦3.17bn.
Top product: Home Item 400 · best store: ShopSmart Lagos (STR015) · top category: Beauty · best month: December · best region: South (driven by store count).

## Data-quality issues (details in `Cleaning_Log`)
1. Discount is subtracted as a flat amount although it looks like a % (possible ~₦756M / 10% overstatement).
2. Only ~33% of order value is Completed (33.7% Cancelled, 33.3% Pending).
3. Returns table: 1,252 returns dated before the order; only 815 link to Completed orders.
4. Inventory covers one store per product; 10.3% of orders predate customer registration.

## Limitations
- Dashboard uses drop-down filters (not slicers) so it recalculates on every Excel version; slicers can be added to the PivotTables.
- Pivot items list alphabetically; sort by value in Excel. Pivots 9, 10, 12 are pre-filtered to Top 10 / Bottom 10 / Top 15.
- Charts are linked to the formula-driven `Analysis` tables, not to PivotTables.
- The workbook is large (about 28 MB) because it holds 50,000 rows with live lookup formulas. Allow a minute to open and recalculate.
