# DAX Measures Reference

All measures used across the 4 dashboard pages, organized by display folder as they appear in the Power BI model (`_measures` table).

---

## 📁 customer

```dax
base_customers = COUNT(dim_customer[customer_id])

total_active_customers = DISTINCTCOUNT(fact_sales[customer_id])

avg_sales_per_customer = DIVIDE([total_sales], [total_active_customers])

active_customer_rate = DIVIDE([total_active_customers], [base_customers])

customer_count_by_city = DISTINCTCOUNT(fact_sales[customer_id])
```

> `customer_count_by_city` intentionally references `fact_sales[customer_id]` rather than `dim_customer[customer_id]` — this ensures the measure responds correctly to Year/Month slicers, since `dim_customer` only connects to `dim_date` through `fact_sales`.

---

## 📁 sales

```dax
total_sales = SUM(fact_sales[line_total])

total_orders = DISTINCTCOUNT(fact_sales[order_id])

total_quantity_sold = SUM(fact_sales[quantity])

avg_order_value = DIVIDE([total_sales], [total_orders])

sales_by_bill_region =
CALCULATE(
    [total_sales],
    USERELATIONSHIP(fact_sales[bill_to_city_key], dim_geo[geo_key])
)
```

> `sales_by_bill_region` activates the inactive bill-to relationship for this specific measure, since the model's active relationship to `dim_geo` runs through ship-to city by default.

---

## 📁 targets

```dax
total_target_revenue = SUM(fact_sales_targets[target_revenue])

target_achievement_% = DIVIDE([total_sales], [total_target_revenue])
```

---

## 📁 marketing

```dax
total_spend = SUM(fact_campaign_spend[spend])

CTR =
DIVIDE(
    SUM(fact_campaign_spend[clicks]),
    SUM(fact_campaign_spend[impressions]),
    0
)

ROAS = DIVIDE([total_sales], [total_spend])

Cost_per_Order = DIVIDE([total_spend], [total_orders])
```

---

## 📁 operations

```dax
units_in_inventory = SUM(fact_inventory[units])

avg_order_to_ship_days =
AVERAGEX(
    fact_order_process,
    DATEDIFF(fact_order_process[order_date], fact_order_process[ship_date], DAY)
)

avg_ship_to_delivery_days =
AVERAGEX(
    fact_order_process,
    DATEDIFF(fact_order_process[ship_date], fact_order_process[delivery_date], DAY)
)

avg_order_to_delivery_days =
AVERAGEX(
    fact_order_process,
    DATEDIFF(fact_order_process[order_date], fact_order_process[delivery_date], DAY)
)

on_time_delivery_rate =
DIVIDE(
    CALCULATE(COUNTROWS(fact_order_process), fact_order_process[delivery_date] <= fact_order_process[pay_date]),
    COUNTROWS(fact_order_process)
)

sell_through_rate = DIVIDE([total_quantity_sold], [units_in_inventory])
```

> `on_time_delivery_rate` uses `pay_date` as a stand-in deadline, since the model doesn't include an explicit SLA/promised-delivery-date field.

---

## Design notes

- Every measure is placed in a **Display Folder** matching its business area, keeping the Fields pane organized and easy to navigate even with 20+ measures.
- Measures that need to respond to date-based slicers always reference the **fact table**, not the dimension table alone — dimensions only connect to `dim_date` through a fact table, so referencing them directly breaks filter propagation.
- `USERELATIONSHIP` is used deliberately in `sales_by_bill_region` to activate a specific inactive relationship without disturbing the model's default active relationship elsewhere.
