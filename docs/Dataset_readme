# 📊 Supplier Recommender Dataset (Textile Sector)

Synthetic dataset designed for supplier recommendation in a textile supply chain. It combines:
- **Supplier master data (side information)**
- **Event–supplier interactions** (shortlisting, participation, awards, ratings)

Supports:
- Collaborative filtering
- Content-based methods
- Hybrid recommenders

---

## 🔑 Event Definition
An **event** represents a procurement process (e.g., RFQ/tender) where:
- Suppliers are shortlisted
- Some participate and submit offers
- One or more may be awarded

Each event includes:
- Buyer info (ID, country)
- Item category
- Complexity & criticality
- Budget and date

Generates interactions such as:
- Shortlisted
- Participated
- Awarded
- Rated

---

## 📑 Dataset Structure (Sheets)

- **SUPPLIERS** → Supplier profiles + performance metrics (500 suppliers)
- **EVENTS** → Procurement metadata (2,200 events)
- **INTERACTIONS** → Event–supplier interactions
- **ITEMS** → Product taxonomy (complexity & criticality)
- **CRITERIA** → Data dictionary
- **README** → Usage and ML guidance

---

## 🏭 SUPPLIERS (Key Features)

Contains supplier characteristics and aggregated KPIs:
- Profile: region, tier, product focus, certifications
- Operations: capacity, lead time, price index
- Performance:
  - defect rate
  - on-time delivery
  - sustainability, innovation, responsiveness
  - financial risk
- Interaction-derived metrics:
  - `avg_rating` → avg stakeholder score (1–5)
  - `avg_offer_price_index` → avg quoted price vs market
  - `avg_offer_lead_time` → avg quoted lead time
- Outcomes:
  - `n_events`, `n_awards`
- Label:
  - `performance_band` → POOR / AVERAGE / GOOD / RANDOM

⚠️ Note:
- Some metrics exist even without awards (profile-based, ex-ante)
- Others require participation (interaction-based, ex-post)

---

## 📅 EVENTS

Metadata for procurement processes:
- buyer, country
- item category
- complexity & criticality (1–5)
- budget
- date (2022–2024)

---

## 🤝 INTERACTIONS

Core of recommendation modeling:
- Links suppliers ↔ events
- Includes:
  - shortlisted, participated, awarded
  - offer price & lead time
  - stakeholder ratings (1–5)
  - utility score (internal decision signal)
  - post-award outcomes (delay, quality)

---

## 🧵 ITEMS

Category reference:
- item category
- complexity (1–5)
- criticality (1–5)

---

## 📘 README (ML Usage)

Supports:
- **Classification** → awarded or not
- **Regression** → stakeholder_rating
- **Ranking** → utility_score

Features:
- Explicit feedback → ratings
- Implicit feedback → participation, awards
- Cold-start → ~10% suppliers with no interactions
- Temporal splits:
  - Train: 2022–2023
  - Validation: 2024 H1
  - Test: 2024 H2

---

## ✅ Recommender Use Cases

- Collaborative filtering → INTERACTIONS
- Content-based → SUPPLIERS
- Hybrid models → combine both
- Temporal evaluation → realistic simulation

---

# 📝 Key Concepts

## A) Alignment with Ireland Paper
Dataset matches and extends the paper:
- Event–supplier framework ✔
- Interaction matrix ✔ (richer than binary)
- Event + supplier metadata ✔ (more complete)
- Cold-start explicitly modeled ✔
- Supports advanced models (FM, hybrid) ✔

---

## B) Ex-ante vs Ex-post Data

- **Ex-ante (profile)** → known before award  
  (price, lead time, certifications)
- **Ex-post (observed)** → only after delivery  
  (delay, quality)

👉 Explains why suppliers with no awards still have data.

---

## C) Key Metrics

- **avg_rating** → avg stakeholder rating (from participation)
- **avg_offer_price_index** → avg quoted price vs market
- **avg_offer_lead_time** → avg quoted delivery time

---

## D) performance_band

Derived supplier label:
- Based on composite KPI (quality, delivery, risk, price, sustainability)
- Split into:
  - POOR (bottom 33%)
  - AVERAGE (middle 33%)
  - GOOD (top 33%)
  - RANDOM (~7% noise)

---

## E) Matrices for Recommender Systems

- **P (interaction matrix)** → from INTERACTIONS  
  - e.g., participated = 1, else 0
  - can include ratings, awards, utility

- **X (feature matrix)** → from EVENTS  
  - buyer, country, category, complexity, budget, time

➕ Supplier features can also be added → hybrid models

---

# 🧠 Supplier Clusters (Latent Profiles)

Clusters define realistic trade-offs:

- **FAST_CHEAP** → low cost, fast, lower quality
- **PREMIUM_SUSTAIN** → high quality & sustainability, expensive
- **BALANCED** → no extremes
- **LEGACY_UNRELIABLE** → outdated, risky, poor performance
- **NICHE_SPECIALTY** → specialized, high quality, lower capacity
- **NOISY** → high variability

⚠️ Note:
- **NOISY (cluster)** ≠ **RANDOM (label)**

---

## 🎯 Why Clusters Matter

- Create realistic trade-offs
- Introduce heterogeneity
- Enable robust evaluation
- Generate correlations across KPIs
- Improve learning for ML models

---

## ✅ Final Summary

This dataset:
- Models real procurement dynamics (events + suppliers + interactions)
- Combines **behavioral data + rich metadata**
- Supports **cold-start and hybrid recommendation**
- Enables **classification, regression, and ranking tasks**
- Provides **realistic supplier heterogeneity via clusters**

👉 Suitable for building and benchmarking modern recommender systems in supply chain contexts.
