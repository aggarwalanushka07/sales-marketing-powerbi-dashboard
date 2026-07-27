**Sales & Marketing Performance Dashboard:**

End-to-end Power BI project featuring interactive dashboards, data modelling, DAX, KPI design and business intelligence across Sales, Marketing, Customers and Operations.

**📌Project Overview**

This project analyzes the performance of a B2B distribution business across four connected areas: overall sales health, customer behavior, marketing effectiveness and operational fulfillment. It's built on a star schema data model with 6 fact tables and 6 dimension tables and includes 20+ custom DAX measures organized into logical, presentable groups.
The goal was to go beyond just building charts — every visual on every page answers a specific business question and several genuine insights emerged from the data during the build (detailed below).

Tools used: Power BI Desktop, DAX, Data Modeling (Star Schema)

<img width="1171" height="706" alt="data model" src="https://github.com/user-attachments/assets/cf08aaff-bebd-4f6b-ba86-add0b541fda9" />

The model connects 6 fact tables (`fact_sales`, `fact_inventory`, `fact_order_process`, `fact_promotion_coverage`, `fact_campaign_spend`, `fact_sales_targets`) to 6 dimension tables (`dim_customer`, `dim_product`, `dim_geo`, `dim_date`, `dim_campaign`, `dim_order_flag`) in a standard star schema (also can be considered as galaxy schema), connected through one-to-many relationships. Working with 6 fact tables meant the model could easily have become difficult to navigate. To keep it clean and query friendly, I organized every measure into display folders by business area (`customer`, `sales`, `targets`, `marketing`, `operations`) and made sure every relationship was considered.

**📊Dashboard Pages**

1. Executive Overview

https://github.com/user-attachments/assets/25721834-f7fd-4c48-9fdd-4026823d2d62

The Executive Overview dashboard provides senior management with a high level insight of business performance by answering the following key questions:

**❓Business Questions Answered**
- Are we achieving our sales targets each month?
- What is our overall sales performance?
- How many orders have been placed and how many customers are actively purchasing?
- Which product categories generate the highest sales?
- Which customer regions contribute the most revenue?
- Which sales channels perform the best?
- Which products are our top revenue drivers?
- How close are we to meeting our overall revenue target?

**✅ Business Decisions Supported**
- Evaluate whether sales targets are being achieved.
- Identify high performing product categories and sales channels.
- Understand which regions contribute the most revenue.
- Monitor customer activity and order volume.
- Prioritize products driving the highest sales.

