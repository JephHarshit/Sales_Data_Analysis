# Sales Data Analysis

### Dashboard Link : https://app.powerbi.com/links/Jl_1YTqF3b?ctid=945ef104-7619-4ac0-aebb-ed348ffd933d&pbi_source=linkShare

## Problem Statement

The dashboard provides key insights into product sales, profitability, and sales trends over time. It helps in understanding the best-performing products, identifying growth opportunities, and making data-driven decisions to improve overall business performance.


### Steps Followed for Power BI Dashboard Development

# Power BI Sales Dashboard

This project involves analyzing sales transaction data using Power BI. The dashboard provides key insights into sales, profit, discount strategies, and sales trends over time.

## Steps Involved

### Step 1: Data Import & Cleaning
- Loaded the sales transaction dataset (CSV/Excel) into Power BI Desktop.
- Opened Power Query Editor to check column distribution, column quality, and column profile for data validation.
- Found missing values in the `Discount` and `Profit` columns and handled them using appropriate transformations (e.g., replacing null values with zero or interpolating missing values).

### Step 2: Creating Key Metrics
Created calculated columns and measures using DAX to derive the following:
```DAX

Total Profit = CALCULATE(SUM('Fact Table'[Profit]),ALL('Date Table 1'),USERELATIONSHIP('Date Table 2'[Date],'Fact Table'[Date (dd/mm/yyyy)]))
Quantity Sold = CALCULATE(SUM('Fact Table'[Units Sold]),ALL('Date Table 1'),USERELATIONSHIP('Date Table 2'[Date],'Fact Table'[Date (dd/mm/yyyy)]))
Sum of Net Sales = CALCULATE(SUM('Fact Table'[Net Sales   ]),ALL('Date Table 1'),USERELATIONSHIP('Date Table 2'[Date],'Fact Table'[Date (dd/mm/yyyy)]))
```

### Step 3: Creating Visuals for Business Insights
#### 1) Top & Bottom 5 Products by Sales, Profit, and Quantity Sold
- Created three clustered bar charts to show the top and bottom 5 products based on:
  - Total Sales
  - Total Profit
  - Total Quantity Sold

#### 2) Sales Trends Over Time (Daily, Monthly, Quarterly, Annually)
- Created a line chart to visualize sales trends over different time periods.
- Added a date hierarchy (Year, Quarter, Month, Day) for dynamic filtering.
- Used a slicer to let users select the desired time range for analysis.

#### 3) Relationship Between Sales & Profit
- Used a scatter plot to show the correlation between Sales and Profit.
- Each dot represents an order, helping identify whether higher sales result in higher profit or not.

#### 4) Comparing Sales/Profit/Quantity Sold Between Two Periods
- Added a date range slicer to allow users to select two different time periods.
- Used a stacked bar chart to compare Sales, Profit, and Quantity Sold across selected periods.

#### 5) Average Discount Offered in Each Discount Category
- Created a bar chart showing average discount % across different discount categories.
- Helps in understanding how discount strategies vary by product category.

#### 6) Total Number of Orders
- Displayed total orders as a KPI card using the measure:
```DAX
Quantity Sold = CALCULATE(SUM('Fact Table'[Units Sold]),ALL('Date Table 1'),USERELATIONSHIP('Date Table 2'[Date],'Fact Table'[Date (dd/mm/yyyy)]))
```

#### 7) Sales/Profit/Discount/Net Sales for Each Order (Filtered by Product/Date/Customer ID/Promotion Categories)
- Created a table visualization showing order-wise details including Product, Date, Customer ID, Sales, Profit, Discount, and Net Sales.
- Added slicers for dynamic filtering by Product, Date, Customer ID, and Promotion Category.

#### 8) Sales by Different Cities
- Created a map visualization with sales figures by city.
- Used latitude & longitude data to accurately represent sales distribution geographically.

## Technologies Used
- **Power BI Desktop** for data visualization and analysis.
- **Power Query Editor** for data transformation and cleaning.
- **DAX (Data Analysis Expressions)** for creating calculated metrics and measures.


## Key Insights from the Dashboard

### 1) Top & Bottom Performing Products
- The top-selling product is **Apple iPhone 14**, contributing **21.4M** of total sales and 281 units sold in total.
- The bottom-performing product is **Colgate Toothpaste**, contributing only **0.02M** of total sales and **Borosil Glass Set** with **203** total unit sold.
- Highest profit comes from **Apple iPhone 14**, while **Colgate Toothpaste** have the lowest profit margin.

### 2) Sales Trends Over Time
- **Peak sales** occur on **24 November 2022**.
- **Monthly sales** show fluctuations, with a significant dip in **February**, likely due to post-holiday slowdowns.
- **Daily sales trends** show spikes on **weekends**, suggesting higher consumer spending during off-work days.

### 3) Sales & Profit Relationship
- **Sales and profit are positively correlated**, but certain high-sale products have lower profit margins, indicating possible discount-driven sales.
- **Footwear category** shows **high sales but low profit**, likely due to heavy discounting.


### 4) Total Orders
- A total of **3510 orders** were placed in the given timeframe.

### 5) Order-Level Insights Using Filters
- Sales can be **filtered dynamically** by **Product Category, Date, Customer ID, and Promotion Type**, allowing for granular analysis.

### 8) Sales Distribution by City
- **Top 3 cities with the highest sales:**
  - **Kanpur (15.3%)**
  - **Delhi (12.7%)**
  - **Bangalore (10.4%)**
- **Lowest sales** recorded in smaller cities, indicating **potential areas for market expansion**.

### 9) Final Step
- The dashboard was published to Power BI Service for online access and sharing.

### Conclusion
The Salers Company Sales Dashboard provides a comprehensive view of sales performance, trends, and profitability. The insights drawn can help the company optimize product pricing, discounts, and promotional strategies while improving sales forecasting.
