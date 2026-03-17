# BPOBNP — BPO Bonus & Penalty Proposal

**Vendor Solutions · Internal · March 2026**  
Prepared by Mike Vong & Jennifer Routledge

---

## Overview

A scrollable single-page proposal site reviewing the current BPO performance-based pricing model and presenting three forward-looking structural proposals to enhance BPO accountability and merchant experience outcomes.

**BPOs Covered:** TaskUs · InTouchCX · TELUS  
**Period Reviewed:** October 2024 – March 2025 (6 months)  
**Current Structure:** ±5% Core/Retail/Plus · ±10% Core Premium

---

## Live Site

[https://mike-vong.github.io/bpobnp](https://mike-vong.github.io/bpobnp)

---

## Page Structure

### Section 1 — Historical Performance
Six-month review of KPI results vs. targets across all BPO partners. Includes:
- BPO selector (TaskUs / InTouchCX / TELUS / Overall)
- Summary stat cards: Avg Score, Bonus Months, Penalty Months, Net Outcome
- Line chart: Overall Smiley vs. Target (Oct 2024 – Mar 2025)
- Monthly KPI results table per BPO (Core LOB) with colour-coded pass/fail
- Implied Bonus/Penalty outcome table across all BPOs × LOBs
- Data constraints callout (data migration, Zendesk deletion, Beacon instability, etc.)

### Current Structure Reference
- Visual ±5% and ±10% scale bars
- Scorecard methodology summary (45-pt total, KPI scoring rules, bonus/penalty thresholds)

---

### Proposal 1 — Expand to ±10% Across All LOBs
Increase the maximum bonus/penalty for Core, Retail, and Plus from ±5% to ±10%, aligning with the existing Core Premium structure.

**KPIs Evaluated:**
- Merchant Smiley
- Average Handle Time (AHT)
- AFTR (Avoid Follow-up Ticket Rate)
- Valid Live Assist Rate
- Hours Delivery

**Interactive features:**
- Slider + manual target input per KPI
- Live score calculation (0–45 pts) against the new ±10% scale
- Configurable monthly invoice amount for projected $ adjustment

---

### Proposal 2 — Dual-Pillar Scorecard (P&Q vs. Ops Efficiency)
Split the scorecard into two equal-weighted independent pillars. Bonus requires both above threshold; penalty triggered if either falls below.

**Pillar 1 — Performance & Quality:**
- Merchant Smiley
- Communication Quality
- Resolution Quality
- AFTR
- Valid Live Assist Rate

**Pillar 2 — Operational Efficiency:**
- Average Handle Time (AHT)
- Time to Resolve (TTR)
- Tickets per Hour (TPH)
- Interval Compliance
- Hours Delivery

**Interactive features:**
- Independent pillar scoring and B&P % per pillar
- Blended payout rate and projected $ adjustment
- Slider + manual target input for all 10 KPIs

---

### Proposal 3 — Per-Interaction Incentive & Penalty
Reward or penalize each individual interaction based on adherence to 7 evaluated interaction behaviours. Threshold is 5/7.

**Interaction Reward/Penalty Matrix:**

| Score | Outcome |
|-------|---------|
| 7/7   | +$0.10 per interaction |
| 6/7   | +$0.05 per interaction |
| 5/7   | $0.00 (threshold)      |
| 3–4/7 | −$0.05 per interaction |
| ≤2/7  | −$0.10 per interaction |

**Evaluated Interaction Behaviours (7 total):**
1. Context Gathering
2. Voice & Tone
3. Alternative Positioning
4. Clarity & Precision
5. Rapport Building
6. Confident Language
7. *(+ 1 additional behaviour)*

**Interactive features:**
- Slider for total monthly interaction volume
- Sliders for % distribution across each score tier
- Net monthly incentive/penalty calculator with annualized projection

---

## Technical Notes

- Pure static HTML/CSS/JS — no build step required
- Chart.js 4.4 via CDN for the historical performance line chart
- Google Fonts: Syne (display) + DM Sans (body)
- All scoring logic runs client-side in real time
- Fully self-contained single file (`index.html`)

---

## Scoring Logic

KPI scoring uses a linear scale where:
- **Floor (0 pts)** = 75% of target
- **Ceiling (max pts)** = 125% of target

Lower-is-better KPIs (AHT, TTR) are scored inversely.

The ±10% B&P scale maps total scores (0–45) using the same thresholds as the current Core Premium structure.
