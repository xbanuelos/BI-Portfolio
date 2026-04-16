# Project 03 — Peak Hours Heatmap by City Zone

**Dataset:** Olist Brazilian E-Commerce (Kaggle)

**Domain variant:** ER Admission Heatmap — admissions by hour and day of week

**Tools:** Python, Pandas, Matplotlib, Seaborn

---

## Business Context

For platforms like Rappi and DiDi, knowing when demand peaks happen is
critical for courier allocation, staffing, and surge pricing decisions.
Missing a peak means lost revenue and poor customer experience. This project
maps order volume across hours and days of the week — nationally and by state.

---

## Business Questions & Findings

### 1. What hours have the highest order volume?
Peak hours are 13h–16h on weekdays, with Tuesday 14h as the single highest
slot (1,124 orders). A secondary peak appears at Monday 21h (1,118 orders),
suggesting two distinct buying moments: post-lunch and after-dinner browsing.

### 2. What days of the week are busiest?
Monday and Tuesday dominate the top 5 slots. Monday has the most consistent
high volume throughout the day, while Tuesday has the single highest peak moment.

**Top 5 slots nationally:**

| Day     | Hour | Orders |
|---------|------|--------|
| Tuesday | 14h  | 1,124  |
| Monday  | 21h  | 1,118  |
| Monday  | 14h  | 1,096  |
| Monday  | 16h  | 1,094  |
| Tuesday | 16h  | 1,081  |

### 3. Do peak patterns differ by state?
Yes — significantly. While all states show higher weekday volume,
the peak slot varies by region:

| State | Day      | Hour | Orders |
|-------|----------|------|--------|
| SP    | Tuesday  | 14h  | 483    |
| RJ    | Tuesday  | 14h  | 162    |
| MG    | Thursday | 16h  | 140    |
| RS    | Sunday   | 20h  | 75     |
| PR    | Monday   | 10h  | 69     |

SP and RJ share the same peak slot but SP has 3x the volume.
RS is the only state with a dominant weekend peak, suggesting a
distinct consumer profile in the south.

Across all 27 states, Monday is the dominant peak day nationally,
appearing as the top slot in 12 states. Amazonas (AM) stands out
as the only state with a late-night weekend peak (Saturday 22h).

### Additional finding — peak hours vs late delivery rate
Contrary to expectations, peak purchase hours do NOT correlate with
higher late rates. Late-night orders (0h, 19h–23h) show the highest
late rates (~8.7%), likely due to fulfillment cutoff hours pushing
those orders to next-day processing.

---

## Conclusion

Demand peaks nationally between 13h–16h on weekdays, with Tuesday 14h
as the single highest slot. Regional behavior differs meaningfully —
SP/RJ peak at lunch, MG in the evening, and the south (RS, SC) uniquely
peaks on Sunday at 20h.

For ops teams, these patterns directly inform courier scheduling, push
notification timing, and delivery date adjustments for late-night orders.

---
