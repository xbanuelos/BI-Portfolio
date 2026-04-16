# Project 01 — Order Funnel Analysis

**Dataset:** Olist Brazilian E-Commerce (Kaggle)
**Domain variant:** Patient Visit Funnel — appointment scheduling → attendance → follow-up
**Tools:** Python, Pandas, Matplotlib

---

## Business Context

In e-commerce platforms like Rappi or MercadoLibre, understanding how orders
move through each stage of the lifecycle is critical for identifying operational
bottlenecks. This project maps the Olist order funnel from purchase to delivery
and quantifies where orders are lost at each step.

---

## Funnel Stages

```
Purchased → Approved → Delivered to Carrier → Delivered to Customer
```

---

## Key Findings

- **Overall conversion:** 96.9% of orders completed the full funnel
- **Biggest drop-off:** The step from `approved → delivered to carrier`
  loses 1,623 orders — the largest single point of failure in the funnel
- **Root cause hypothesis:** The bottleneck sits in logistics handoff,
  not in payment approval — suggesting a carrier pickup or warehouse
  processing issue rather than a payment gateway problem
- **Data quality:** 8 orders were marked as `delivered` with no recorded
  delivery timestamp — flagged as data entry inconsistencies and excluded
  from analysis

---

## Conclusion

The Olist order funnel is robust at 96.9% overall conversion, but the
logistics handoff between approval and carrier pickup represents the
single largest opportunity for improvement. Addressing this step could
recover over 1,600 orders per cycle.

---

## Files

```
project_01_order_funnel/
├── order_funnel.ipynb
└── outputs/
    └── order_funnel_3charts.png
```
