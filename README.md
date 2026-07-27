**Sales & Marketing Performance Dashboard:**

End-to-end Power BI project featuring interactive dashboards, data modelling, DAX, KPI design and business intelligence across Sales, Marketing, Customers and Operations.

**Project Overview**

This project analyzes the performance of a B2B distribution business across four connected areas: overall sales health, customer behavior, marketing effectiveness and operational fulfillment. It's built on a star schema data model with 6 fact tables and 6 dimension tables and includes 20+ custom DAX measures organized into logical, presentable groups.
The goal was to go beyond just building charts — every visual on every page answers a specific business question and several genuine insights emerged from the data during the build (detailed below).

Tools used: Power BI Desktop, DAX, Data Modeling (Star Schema)

**Data Model:**
<img width="1171" height="706" alt="data model" src="https://github.com/user-attachments/assets/cf08aaff-bebd-4f6b-ba86-add0b541fda9" />

The model connects 6 fact tables (`fact_sales`, `fact_inventory`, `fact_order_process`, `fact_promotion_coverage`, `fact_campaign_spend`, `fact_sales_targets`) to 6 dimension tables (`dim_customer`, `dim_product`, `dim_geo`, `dim_date`, `dim_campaign`, `dim_order_flag`) in a standard star schema (also can be considered as galaxy schema), connected through one-to-many relationships. Working with 6 fact tables meant the model could easily have become difficult to navigate. To keep it clean and query friendly, I organized every measure into display folders by business area (`customer`, `sales`, `targets`, `marketing`, `operations`) and made sure every relationship was considered.

**📊Dashboard Pages**

**1. Executive Overview** *(with Interactive Demo)*

https://github.com/user-attachments/assets/25721834-f7fd-4c48-9fdd-4026823d2d62

The Executive Overview dashboard provides senior management with a high level insight of business performance by answering the following key questions:

**Business Questions Answered**
- Are we achieving our sales targets each month?
- How is overall sales performance changing over time?
- How many orders have been placed and how many customers are actively purchasing?
- Which product categories generate the highest sales?
- Which customer regions contribute the most revenue?
- Which sales channels perform the best?
- Which products are our top revenue drivers?
- How close are we to meeting our overall revenue target?

**Business Decisions Supported**
- Evaluate whether sales targets are being achieved.
- Identify high performing product categories and sales channels.
- Understand which regions contribute the most revenue.
- Monitor customer activity and order volume.
- Prioritise products that drive the highest sales.

**2. Sales & Customer Analysis** *(with Interactive Demo)*

<img width="2075" height="1200" alt="Enterprise Sales   Marketing Analytics Dashboard_page-0002" src="https://github.com/user-attachments/assets/76592250-d6da-4921-8237-cab4e840b90b" />

This dashboard moves beyond overall performance to focus on *who* is actually driving sales—customers, segments, account managers and geographic concentration—answering the questions a sales manager or director would ask next.

**Business Questions Answered**
- How are sales changing over time?
- Who are our highest-value customers by sales?
- How does revenue break down across customer segments (Enterprise, Mid-Market, SMB)?
- Which account managers are generating the most revenue?
- What is the average order value and average sales per customer?
- How much product quantity has been sold?
- What percentage of our customer base is actively purchasing?
- In which cities is our customer base most concentrated?

**Business Decisions Supported**
- Identify and prioritize high-value customer accounts for retention efforts.
- Allocate sales and account management resources to the most valuable customer segments.
- Evaluate account manager performance and identify coaching or workload opportunities.
- Monitor customer engagement by tracking active customer participation.
- Support regional expansion and sales planning using customer concentration by city.
- Track sales trends to identify growth opportunities and seasonal patterns.

**3. Marketing Performance** *(with Interactive Demo)*

<img width="2075" height="1200" alt="Enterprise Sales   Marketing Analytics Dashboard_page-0003" src="https://github.com/user-attachments/assets/dfd42e2d-756e-479c-8812-0b29a585cfe5" />


This dashboard connects marketing activity to business outcomes—not just how much was spent or how many people saw an ad but whether that investment translated into revenue, answering the questions a marketing lead would ask about efficiency and return.

**Business Questions Answered**
- How much are we spending on marketing and how is spend trending over time?
- What is our overall Click-Through Rate (CTR)?
- How efficiently is our marketing investment converting into sales (ROAS)?
- What is our average cost per order acquired through marketing?
- How do clicks and impressions compare across individual campaigns?
- Which channels receive the most marketing investment?
- Which campaigns deliver the best return on ad spend?

**Business Decisions Supported**
- Reallocate budget toward high-ROAS campaigns and away from underperforming ones.
- Evaluate whether channel-level investment aligns with channel-level results.
- Identify campaigns worth repeating or scaling based on past performance.
- Monitor cost efficiency (Cost per Order) to detect spend inefficiencies early.
- Use CTR insights to evaluate campaign engagement and targeting effectiveness.

**4. Inventory & Operations** *(with Interactive Demo)*

<img width="2075" height="1200" alt="Enterprise Sales   Marketing Analytics Dashboard_page-0004" src="https://github.com/user-attachments/assets/d1a627e3-04a0-46fc-b408-803f422c2e98" />

This dashboard shifts from revenue to reliability; tracking how efficiently orders move from purchase to delivery and whether inventory levels are aligned with actual demand, answering the questions an operations or supply chain lead would ask.

**Business Questions Answered**
- How many units do we currently hold in inventory?
- How long does it take, on average, for an order to go from purchase to delivery?
- What percentage of orders are delivered on time?
- How efficiently is inventory converting into actual sales (Sell-Through Rate)?
- Which products carry the most inventory?
- How are orders distributed across priority levels (Express vs. Standard)?
- At which stage of the order process—ordering, shipping, or delivery—do delays occur?
- Is inventory aligned with demand at the category level, or are we overstocked or understocked?

**Business Decisions Supported**
- Identify products at risk of overstocking or understocking based on sell-through rate.
- Pinpoint which stage of the fulfillment process requires process improvement.
- Evaluate whether express orders are actually being fulfilled faster than standard ones.
- Support inventory planning and purchasing decisions at the category level.
- Balance inventory levels with customer demand to improve stock availability.
- Set realistic customer delivery expectations using historical delivery performance.
