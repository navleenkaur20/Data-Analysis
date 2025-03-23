# E-commerce Sales Analysis Report

## Dataset Overview

This project analyzes a retail dataset derived from a sample Superstore. It provides insights into customer behavior, product performance, and time-based trends in sales and profits.

The dataset contains the following important columns:
- `Order Date`, `Ship Date`: Dates related to when orders were placed and shipped.
- `Sales`, `Profit`: Financial metrics used to assess performance.
- `Category`, `Sub-Category`: Classification of products sold.
- `Segment`: Type of customer (Consumer, Corporate, Home Office).
- `Region`, `City`, `Country`: Geographical information about orders.
- `Customer ID`, `Product Name`: Information identifying customers and products.

### Descriptive Statistics Summary

| Metric     | Sales      | Quantity | Discount | Profit     |
|------------|------------|----------|----------|------------|
| Mean       | 229.86     | 3.79     | 0.16     | 28.66      |
| Minimum    | 0.44       | 1        | 0.00     | -6599.98   |
| Maximum    | 22638.48   | 14       | 0.80     | 8399.98    |

These figures suggest that while the average profit is positive, there are significant losses in certain transactions.

---

## Time-Based Feature Engineering

Additional columns were created from the original `Order Date` column to facilitate temporal analysis:
- **Order Month**: Extracted month of the order.
- **Order Year**: Extracted year of the order.
- **Order Day of Week**: Day of the week the order was placed.

These features help identify seasonal trends and weekly sales patterns.

---

## Monthly Sales Analysis

Sales were aggregated on a monthly basis. It was observed that:
- **November** had the highest sales.
- Q4 (October to December) typically sees higher sales, indicating potential seasonality or holiday-related buying behavior.

Code used:
```python
sales_by_month = df.groupby('Order Month')['Sales'].sum().reset_index()
```

---

## Sales Analysis by Category

Sales were grouped by product categories:
- **Technology** generated the highest proportion of sales.
- **Furniture** and **Office Supplies** had comparable shares.

Category breakdown:
| Category         | Sales Percentage |
|------------------|------------------|
| Technology       | 36.4%            |
| Furniture        | 32.3%            |
| Office Supplies  | 31.3%            |

This suggests Technology products are key drivers of revenue.

---

## Sales Analysis by Sub-Category

Sales by sub-category were sorted in descending order. Top performers:
1. Phones
2. Chairs
3. Storage

These sub-categories contributed the most to overall revenue. Poor performers included categories like Envelopes and Fasteners.

```python
sales_by_subcategory = df.groupby('Sub-Category')['Sales'].sum().reset_index()
sales_by_subcategory = sales_by_subcategory.sort_values(by='Sales', ascending=False)
```

---

## Monthly Profit Analysis

Monthly profits follow a similar trend to monthly sales. Key observations:
- Peak profit was seen in **November**, consistent with the sales trend.
- There is a general rise in profits toward the end of the year.

---

## Profit Analysis by Category

Profit contributions by category differ from sales:
- **Technology** was responsible for over 50% of profits.
- **Office Supplies** also contributed significantly.
- **Furniture** had the lowest profit contribution (under 7%).

This indicates that higher sales in a category do not always translate into higher profits.

---

## Profit Analysis by Sub-Category

Sub-categories were sorted by total profit. Top contributors:
1. Copiers
2. Phones
3. Accessories

Sub-categories with **negative profits** include:
- Tables
- Bookcases
- Supplies

These represent potential loss leaders or inefficient product lines.

---

## Customer Segment Analysis

Sales and profits were analyzed across customer segments:
- **Consumer** segment had the highest sales and profit.
- **Corporate** and **Home Office** followed in descending order.

A sales-to-profit ratio was calculated to assess efficiency:

| Segment       | Sales-to-Profit Ratio |
|---------------|------------------------|
| Consumer      | 8.66                   |
| Corporate     | 7.68                   |
| Home Office   | 7.13                   |

Lower ratios are preferred as they imply higher profitability per unit of sales.

Code used:
```python
sales_profit_by_segment['Sales_to_Profit_Ratio'] = sales_profit_by_segment['Sales'] / sales_profit_by_segment['Profit']
```

---

## Key Insights

- The **Technology** category performs best in both sales and profit.
- **Consumer** is the most lucrative segment.
- Several sub-categories (e.g., Tables, Bookcases) consistently incur losses and may need pricing or cost structure review.
- Seasonal trends are evident, especially in **Q4**, likely due to holiday shopping.

This analysis can guide strategic decisions in inventory planning, marketing, and customer targeting.