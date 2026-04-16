# Project 02 — Delivery Time Analysis

**Dataset:** Olist Brazilian E-Commerce (Kaggle)

**Domain variant:** Lab Result Turnaround Time — delays by department and sample type

**Tools:** Python, Pandas, Matplotlib, Seaborn

---

## Business Context

Late deliveries directly impact customer satisfaction, refund rates, and
seller reputation on platforms like Rappi and MercadoLibre. This project
identifies where, when, and why deliveries fail to meet estimated dates —
providing actionable segmentation by state, product category, seller origin,
and seasonality.

**Limitation:** The dataset does not include carrier/logistics provider
information, so delays cannot be attributed to specific shipping companies.

---

## Business Questions & Findings

### 1. What percentage of orders arrive late?
8.1% of delivered orders arrived after the estimated date (7,826 out of ~96k).
An additional 5.2% had abnormally long delivery times (beyond Q3 + 1.5×IQR),
with extreme cases reaching 209 days.

### 2. Which customer states have the highest late delivery rates?
The segment average across states is ~11%, already above the global 8.1%,
meaning late deliveries are geographically concentrated. Worst performers:

| State | Late Rate |
|-------|-----------|
| AL    | 23.9%     |
| MA    | 19.7%     |
| PI    | 16.0%     |
| CE    | 15.3%     |

Best performers: RO (2.9%), AM (4.1%), PR (5.0%).
The northeast concentration suggests a last-mile infrastructure gap,
not a product or seller issue.

### 3. Which product categories are most prone to late deliveries?
The segment average (~7.5%) is below the global 8.1%, meaning most
categories actually outperform the overall average. True outliers:

| Category                      | Late Rate |
|-------------------------------|-----------|
| audio                         | 12.7%     |
| fashion_underwear_e_moda_praia| 12.6%     |
| artigos_de_natal              | 12.0%     |

Christmas products are expected given seasonal demand spikes.
Audio and beachwear suggest supply chain issues specific to those seller networks.

### 4. Which seller states generate the most delays?
Segment average for seller states is ~6.5%, below the global 8.1%.
MA is the only true outlier at 23.6% — nearly 4x its segment average.
SP sellers (8.5%) are slightly above average but within normal range
given their volume. MA-based sellers represent an isolated operational
risk worth a dedicated audit.

### 5. Are there seasonal patterns?
Segment average across months is ~6.5%, confirming most months perform
better than the global average. Two clear anomaly clusters:

- **November 2017 (13.8%)** — Black Friday demand spike
- **Q1 2018 (Jan 15.7%, Feb 20.5%, Mar peak)** — sustained 3-month
  deterioration suggesting post-holiday carrier backlog

---

## Overall Recommendation

The delivery problem is concentrated in three dimensions: northeast customer
states (AL, MA, PI), MA-based sellers, and Q1 + November months. Addressing
these three nodes specifically — rather than overhauling the entire operation —
could resolve the majority of late delivery complaints at minimal cost.

---

