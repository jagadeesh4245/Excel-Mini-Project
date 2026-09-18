# Excel Mini-Project: Kaggle Dataset Analysis

**Student Name:** MANGINENI JAGADEESH  
**Batch:** D17R  
**Workbook File:** MANGINENI_JAGADEESH_KaggleMiniProject.xlsx  

---

## Task Completion Summary

### 1. Data Import
- Downloaded `trains.csv` from Kaggle (200 records).
- Imported the CSV file into Excel using Power Query (`Data > Get Data > From Text/CSV`).
- Verified that all column headers were automatically detected and mapped correctly.

### 2. Data Cleaning
- **Duplicates:** Used Power Query `Remove Duplicates` across all columns to eliminate identical records.
- **Missing Values:** Replaced `null` values with `0` or dropped blank entries using `Remove Empty`.
- **Text Standardization:** Applied `Transform > Format > Capitalize Each Word` to normalize text columns (`Category`, `City`, `State`).
- **Data Types:** Converted `Order Date` and `Ship Date` to `Date` type, and `Sales` to `Decimal Number`.

### 3. Derived Columns
Added two custom calculated columns:
1. **Full Location:** Merged city and state fields using `= [City] & ", " & [State]`.
2. **Sales Category:** Categorized transaction sizes using logic:
   `if [Sales] >= 500 then "High" else if [Sales] >= 100 then "Medium" else "Low"`

### 4. Conditional Formatting
- **Sales Category:** Applied green highlight for `"High"` and yellow for `"Medium"` sales categories.
- **Top Values:** Applied `Top 10%` conditional formatting to the `Sales` column with custom fill.
- **Locations:** Highlighted target states in the `Full Location` column using *Text that Contains*.

### 5. Pivot Table Report
- Summarized `Sum of Sales` by `Category` (Rows) and `Sales Category` (Columns).
- **Calculated Field:** Created `Estimated Tax` with formula `= Sales * 0.05`.
- Formatted all numeric values to **Currency ($ USD, 2 decimal places)**.

### 6. Chart Visualizations
- **Chart 1 (Clustered Column Chart):** Visualizes total sales by Product Category.
- **Chart 2 (3D Pie / Donut Chart):** Displays market share distribution across `Ship Mode`.
- Ensured clear axis labels, explicit chart titles, and data callout labels on both charts.

### 7. Single-Page Dashboard Layout
- Created a dedicated `Dashboard` worksheet with gridlines removed.
- Arranged the Pivot Table Summary (Top-Left), Column Chart (Top-Right), Pie Chart (Bottom-Left), and Slicers on a single screen.
- Added interactive **Slicers** (`Region` and `Category`) connected via *Report Connections* to filter both charts and tables dynamically.

### 8. Insight Summary & Recommendations
Included a narrative text block (cells `A20:H24`) on the Dashboard tab:

> **Insight Summary:**  
> Analysis of the sample transaction dataset indicates that **Furniture** generated the highest total revenue ($20,232.62), followed closely by **Technology** ($17,472.76), despite Office Supplies accounting for the largest volume of orders. High-value transactions (Sales ≥ $500) accounted for a significant portion of total revenue while representing a small percentage of overall orders.  
> **Recommendation:** Focus promotional campaigns and bundled discounts on high-margin Furniture and Technology categories while optimizing Standard Class shipping options to manage fulfillment costs effectively.
