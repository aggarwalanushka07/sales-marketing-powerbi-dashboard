**<h2> Sales & Marketing Performance Dashboard </h2>**

End-to-end Power BI project featuring interactive dashboards, data modelling, DAX, KPI design and business intelligence across Sales, Marketing, Customers and Operations.

**<h3> Project Overview </h3>**

This project analyzes the performance of a B2B distribution business across four connected areas: overall sales health, customer behavior, marketing effectiveness and operational fulfillment. It's built on a star schema data model with 6 fact tables and 6 dimension tables and includes 20+ custom DAX measures organized into logical, presentable groups.
The goal was to go beyond just building charts — every visual on every page answers a specific business question and several genuine insights emerged from the data during the build (detailed below).

Tools used: Power BI Desktop, DAX, Data Modeling (Star Schema)

<hr>

**<h3>Data Model</h3>**
<img width="1171" height="706" alt="data model" src="https://github.com/user-attachments/assets/cf08aaff-bebd-4f6b-ba86-add0b541fda9" />

The model connects 6 fact tables (`fact_sales`, `fact_inventory`, `fact_order_process`, `fact_promotion_coverage`, `fact_campaign_spend`, `fact_sales_targets`) to 6 dimension tables (`dim_customer`, `dim_product`, `dim_geo`, `dim_date`, `dim_campaign`, `dim_order_flag`) in a standard star schema (also can be considered as galaxy schema), connected through one-to-many relationships. Working with 6 fact tables meant the model could easily have become difficult to navigate. To keep it clean and query friendly, I organized every measure into display folders by business area (`customer`, `sales`, `targets`, `marketing`, `operations`) and made sure every relationship was considered.

<hr>

**<h3> 📊Dashboard Pages </h3>**

**1. Executive Overview** *(with Interactive Demo)*

https://github.com/user-attachments/assets/25721834-f7fd-4c48-9fdd-4026823d2d62

The Executive Overview dashboard provides senior management with a high level insight of business performance by answering the following key questions:

**Business Questions Answered**
- Are we on track to hit our sales targets or falling behind?
- Which regions and channels are worth investing more in and which are underperforming?
- Are our sales spread across many products or too dependent on a few?
- Are our customers staying active or are we losing engagement over time?

**Business Decisions Supported**
- Evaluate whether sales targets are being achieved.
- Identify high performing product categories and sales channels.
- Understand which regions contribute the most revenue.
- Monitor customer activity and order volume.
- Prioritise products that drive the highest sales.

**Key Improvement Areas**
- Latin America is the lowest-performing region (78K) — worth investigating whether this is a market size issue or under-investment in sales/marketing there.
- At 95.41% target achievement, the business is close but not consistently hitting target every month — reviewing which specific months fell short could reveal a seasonal pattern worth planning around.
- Retail Partner is the lowest performing channel — worth assessing whether this reflects the channel's real potential or a lack of investment relative to Online Store and Wholesale.

<hr>

**2. Sales & Customer Analysis** *(with Interactive Demo)*

https://github.com/user-attachments/assets/65464a52-08f3-4232-a311-55eed2cab9af

This dashboard moves beyond overall performance to focus on *who* is actually driving sales—customers, segments, account managers and geographic concentration—answering the questions a sales manager or director would ask next.

**Business Questions Answered**
- Do we rely too heavily on a small number of big customers?
- Is revenue spread evenly across account managers or concentrated in just a few?
- Which customer segment should we focus on growing?
- Are there cities with enough customers to justify expanding there?

**Business Decisions Supported**
- Identify and prioritize high-value customer accounts for retention efforts.
- Allocate sales and account management resources to the most valuable customer segments.
- Evaluate account manager performance and identify coaching or workload opportunities.
- Monitor customer engagement by tracking active customer participation.
- Support regional expansion and sales planning using customer concentration by city.
- Track sales trends to identify growth opportunities and seasonal patterns.

**Key Improvement Areas**
- Mid-Market customers drive the largest share of revenue (45%) — more than Enterprise, despite Enterprise often being assumed the priority segment in B2B. This may justify shifting account management focus toward Mid-Market retention and growth.
- Sales performance varies meaningfully across account managers — the gap between the top performer (154K) and the lowest (88K) is worth investigating for coaching or territory-balance opportunities.
- Revenue is concentrated among a small group of top customers relative to the full customer base — a retention risk worth addressing if even one or two of these accounts were to churn.
  
<hr>

**3. Marketing Performance** *(with Interactive Demo)*

https://github.com/user-attachments/assets/4cb6c8e6-c402-480f-8730-6c14bd8a6eea

This dashboard connects marketing activity to business outcomes—not just how much was spent or how many people saw an ad but whether that investment translated into revenue, answering the questions a marketing lead would ask about efficiency and return.

**Business Questions Answered**
- Is our marketing spend actually paying off, or are some campaigns losing money?
- Should we move budget away from campaigns or channels that aren't working?
- Are we spending too much to win each order compared to what it's worth?
- Is customer engagement (CTR) improving or dropping across campaigns?

**Business Decisions Supported**
- Reallocate budget toward high-ROAS campaigns and away from underperforming ones.
- Evaluate whether channel-level investment aligns with channel-level results.
- Identify campaigns worth repeating or scaling based on past performance.
- Monitor cost efficiency (Cost per Order) to detect spend inefficiencies early.
- Use CTR insights to evaluate campaign engagement and targeting effectiveness.
  
**Key Improvement Areas**
- Spring Launch delivered a 5.09x ROAS while Black Friday returned only 0.37x despite comparable spend — suggesting budget could be reallocated toward proven high performing campaigns rather than assumed high traffic periods.
- Paid Search and Social receive the largest share of marketing spend (28K and 27K) but spend alone doesn't confirm effectiveness — worth cross checking channel spend against actual ROAS to see if investment matches results.
- Clicks and impressions both decline sharply from Spring Launch through Black Friday — a downward trend worth investigating, especially since it doesn't fully explain why ROAS also dropped for the lowest spending campaigns.
  
<hr>

**4. Inventory & Operations** *(with Interactive Demo)*

https://github.com/user-attachments/assets/26f19661-9212-44be-ac4e-a35492520fca

This dashboard shifts from revenue to reliability; tracking how efficiently orders move from purchase to delivery and whether inventory levels are aligned with actual demand, answering the questions an operations or supply chain lead would ask.

**Business Questions Answered**
- Where are we losing the most time in getting orders delivered?
- Are we reliably meeting delivery expectations or is that a risk?
- Are we stuck with too much stock in some categories and not enough in others?
- Are high priority orders actually getting delivered faster or just labelled that way?

**Business Decisions Supported**
- Identify products at risk of overstocking or understocking based on sell-through rate.
- Pinpoint which stage of the fulfillment process requires process improvement.
- Evaluate whether express orders are actually being fulfilled faster than standard ones.
- Support inventory planning and purchasing decisions at the category level.
- Balance inventory levels with customer demand to improve stock availability.
- Set realistic customer delivery expectations using historical delivery performance.

**Key Improvement Areas**
- Apparel holds the highest inventory levels but shows comparatively lower sales while Electronics sells the most despite carrying less stock — a possible sign of overstocking in Apparel and understocking in Electronics that's worth reviewing with the buying team.
- The order-to-delivery timeline shows ship-to-delivery (5.7 days) taking over twice as long as order-to-ship (2.8 days) — suggesting the shipping/carrier stage, not internal order processing, is the bigger bottleneck to address first.
- Standard orders make up the majority of order volume (57.5%) over Express (42.5%) — worth confirming whether Express orders are actually being fulfilled meaningfully faster, to ensure the priority label reflects real service differentiation.

<hr>

**<h3>DAX Highlights</h3>**

A sample of measures built for this project (see dax_measures.md for the full list, organized by page):

- Sales vs Target % = DIVIDE([Total Sales], [Total Target Revenue])
- ROAS = DIVIDE([total_sales], [total_spend])
- sell_through_rate = DIVIDE([total_quantity_sold], [units_in_inventory])
- sales_by_bill_region = CALCULATE( [total_sales], USERELATIONSHIP(fact_sales[bill_to_city_key], dim_geo[geo_key]))

Measures are organized into display folders (customer, sales, targets, marketing, operations) inside the model for clarity and reusability.

<hr>

**<h3>Skills Demonstrated</h3>**
- **Data Modelling:** Star schema design, fact & dimension tables, inactive relationships, `USERELATIONSHIP()`
- **DAX:** KPI creation, aggregations, ratios, percentages, business calculations, context-aware measures
- **Power BI:** Interactive dashboards, slicers, cross-filtering, KPI cards and clean report layouts
- **Data Visualisation:** Choosing the right chart for the data, dashboard design and clear storytelling
- **Problem Solving:** Fixed relationship and filter issues to make sure reports showed accurate numbers
- **Business Intelligence:** Turned business needs into working dashboards for leadership, sales, marketing and operations

<hr>

**<h3>Repository Contents</h3>**
| File | Description |
|---|---|
| `dashboard.pbix` | Full Power BI file (interactive) |
| `dax_measures.md` | Complete DAX reference, organized by page |
| `data_model_diagram.png` | Star schema relationship diagram |
