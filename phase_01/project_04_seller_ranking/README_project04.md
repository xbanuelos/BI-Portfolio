# Project 04 — Seller Ranking Algorithm

**Dataset:** Olist Brazilian E-Commerce (Kaggle)

**Domain variant:** Clinic/Hospital Ranking — wait time, satisfaction, volume, cost

**Tools:** Python, Pandas, Matplotlib, scikit-learn (MinMaxScaler)

---

## Business Context

Platforms like Rappi and MercadoLibre use composite scores to rank sellers
and restaurants — ranking directly affects visibility and revenue. A single-metric
ranking (e.g. reviews only) is easily gamed and ignores operational performance.
This project builds a fair, multi-metric weighted ranking for Olist sellers.

---

## Methodology

**Step 1 — Define metrics**

| Metric              | Represents     | Direction       |
|---------------------|----------------|-----------------|
| avg_review_score    | Quality        | Higher = better |
| order_volume        | Popularity     | Higher = better |
| on_time_rate        | Reliability    | Higher = better |
| avg_freight_value   | Cost efficiency| Lower = better  |

**Step 2 — Normalize** all metrics to 0–1 using MinMaxScaler.
Freight value is inverted after normalization (1 - value) so that
lower freight = higher score.

**Step 3 — Apply weights**

| Metric            | Weight |
|-------------------|--------|
| avg_review_score  | 35%    |
| on_time_rate      | 30%    |
| order_volume      | 20%    |
| avg_freight_value | 15%    |

**Step 4 — Sensitivity test** with a Rappi-style weight scheme
that prioritizes speed (on_time_rate → 50%).

---

## Business Questions & Findings

### 1. Which sellers perform best and what defines a good seller?
The top seller scores 0.950 out of 1.0, excelling across all 4 metrics
simultaneously. No single metric defines a great seller — the best ones
combine high review scores, strong on-time rates, solid volume, and
competitive freight costs.

### 2. How sensitive is the ranking to different business priorities?
The ranking is highly stable. The top 5 sellers remain unchanged across
both weight schemes (quality-focused vs reliability-focused). Minor shifts
appear from rank 6 onward, confirming that the best sellers are genuinely
well-rounded, not specialists in one metric.

### Bottom performers
The worst seller scores 0.264 — less than 3x the top performer. A sharp
performance cliff appears in the last 9 sellers, making them first
candidates for platform review or removal.

---

## Conclusion

A composite scoring model is more fair and robust than ranking by a single
metric like reviews or volume alone. The 4-metric weighted model identifies
sellers that deliver consistent value across quality, reliability, popularity,
and cost — which is exactly what a platform like Rappi or MeLi needs to
maintain customer trust at scale.

---


