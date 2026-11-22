# Online Sales Performance Dashboard – India Region

A Power BI project analysing online sales across Indian states and cities for the year **2018**. The dashboard tracks sales, profit, quantity and orders, and breaks them down by category, sub-category, city and state.

## Project Contents

| File | Description |
|------|-------------|
| `Online Sales Dashboard.pbix` | Power BI report file (data model + dashboard visuals) |
| `Orders.csv` | Order-level data: who ordered, when and where |
| `Details.csv` | Line-item data: amount, profit, quantity, product and payment mode |

## Dataset Overview

### Orders.csv (500 rows)

| Column | Description |
|--------|-------------|
| `Order ID` | Unique order identifier (e.g. `B-26055`) |
| `Order Date` | Order date, format `DD-MM-YYYY` (01-01-2018 to 31-12-2018) |
| `CustomerName` | Customer name |
| `State` | State of delivery (19 states) |
| `City` | City of delivery (25 cities) |

### Details.csv (1,500 rows)

| Column | Description |
|--------|-------------|
| `Order ID` | Links to `Orders.csv` (one order has multiple line items) |
| `Amount` | Sales amount of the line item |
| `Profit` | Profit of the line item (can be negative) |
| `Quantity` | Units sold |
| `Category` | Clothing, Electronics, Furniture |
| `Sub-Category` | 17 sub-categories (e.g. Bookcases, Saree, Chairs, Printers) |
| `PaymentMode` | COD, Credit Card, Debit Card, EMI, UPI |

### Relationship

`Orders.Order ID` (1) → (many) `Details.Order ID`

## Overall Numbers

| Metric | Value |
|--------|-------|
| Total orders | 500 |
| Line items | 1,500 |
| Total sales | 437,771 |
| Total profit | 36,963 |
| Total quantity | 5,615 |

## Dashboard Features

- **KPI cards:** Total Sales, Total Profit, Total Quantity, Total Orders
- **State slicer:** filter the entire dashboard by state
- **Total Sales by Sub-Category:** bar chart
- **Total Sales by Category:** donut chart
- **Profit by Sub-Category:** pie chart
- **Total Sales by City:** line chart

### Example view: Gujarat

| Metric | Value |
|--------|-------|
| Total Sales | 21,371 |
| Total Profit | 3,001 |
| Total Quantity | 328 |
| Total Orders | 27 |
| Cities | Ahmedabad, Surat |

## How to Use

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Open `Online Sales Dashboard.pbix`.
3. If prompted, refresh the data and point it to `Orders.csv` and `Details.csv`.
4. Use the **State** slicer to explore each state.

## Data Notes

- Dates are in `DD-MM-YYYY` format; set the locale accordingly when loading.
- Profit contains negative values (loss-making items), so check margins by sub-category.
- The state value `Kerala` has a trailing space in `Orders.csv`; trim it to avoid duplicate or mismatched groups.
- No missing values were found in either file.
