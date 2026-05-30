# DreamCraft Sales Analytics

Snowflake Data Warehouse and Power BI Sales Analytics Dashboard built using the DreamCraft dataset.

---

## Project Overview

This project demonstrates an end-to-end Business Intelligence workflow using Snowflake and Power BI.

The data was loaded into Snowflake, cleaned and transformed using SQL, enriched with calculated metrics, analyzed through views and stored procedures, and finally visualized in interactive Power BI dashboards.

The project focuses on sales performance, customer insights, product profitability, and geographic sales distribution.

---

## Technologies Used

- Snowflake Cloud Data Warehouse
- SQL
- Power BI

---

## Project Workflow

### 1. Data Warehousing

Created and managed the following tables in Snowflake:

- Customers
- Employees
- Offices
- Orders
- OrderDetails
- Payments
- Products
- ProductLines

### 2. Data Cleaning

Handled missing values by replacing NULL values with appropriate defaults.

Examples:

- State → 'NA'
- Comments → 'NA'
- Reportsto → 0
- SalesRepEmployeeNumber → 0
- ShippedDate → 0

### 3. Feature Engineering

Created additional business metrics:

#### Markup Percentage

```sql
((MSRP - BUYPRICE) / BUYPRICE) * 100
```

#### Total Cost

```sql
QUANTITYORDERED * PRICEEACH
```

### 4. Views

Created analytical views:

#### Sale_Details

Provides order-level sales information by joining:

- Customers
- Orders
- OrderDetails

#### High_Value_Customers

Provides customer payment insights.

### 5. Stored Procedures

#### GET_MARKUP_HIGHER()

Returns the number of products whose markup percentage exceeds a specified threshold.

#### GET_HIGHCREDIT_CUSTOMER()

Returns customers whose credit limit exceeds a specified value.


---

# Dashboard 1: Sales Performance Overview

### Key Metrics

- Total Revenue
- Average Markup Percentage

### Visualizations

- Revenue by Month (Line Chart)
- Top 10 Customers (Bar Chart)
- Customer Distribution by Country (Treemap)
- Product Line Profitability Overview (Clustered Column Chart)
- Average Markup Percentage (Gauge Chart)

### Insights

- Revenue peaks significantly during the final months of the year.
- USA contributes the largest customer base.
- Classic Cars generate the highest profitability.
- Average product markup remains close to 89%.

---

# Dashboard 2: Sales Insights

### Key Metrics

- Customer Count
- Order Count

### Visualizations

- Product Count by Product Line
- Customer Country Distribution (Map)
- Order Status Distribution (Donut Chart)
- Orders by Year (Pie Chart)

### Insights

- Most orders were successfully shipped.
- Classic Cars and Vintage Cars dominate the product portfolio.
- Customers are distributed across North America, Europe, Asia, and Oceania.
- Order volume increased over the analyzed years.

---

## Repository Structure

```text
DreamCraft-Sales-Analytics
│
├── SQL
│   ├── tables.sql
│   ├── Data_cleaning.sql
│   ├── Feature_Engineering.sql
│   ├── Views.sql
│   ├── StoredProcedure.sql
│   └── stageExport.sql
│
├── dashboards
│   ├── Sales Performance.png
│   └── Sales Insights.png
│
├── dreamcraft.pbit
│
└── README.md
```

---

## Dashboard Screenshots

### Sales Performance Overview

<img width="876" height="492" alt="image" src="https://github.com/user-attachments/assets/a60dbe33-56cd-4f55-bd2b-b22cd7c3f679" />


### Sales Insights

<img width="1173" height="659" alt="image" src="https://github.com/user-attachments/assets/772a1967-f173-41ad-9d34-a4b7016de350" />


