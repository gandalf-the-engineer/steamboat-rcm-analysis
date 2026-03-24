# Steamboat Ortho — Iterations 2-6 Findings

## 🔬 ITERATION #2: DENIAL DEEP DIVE ($490K)

### Summary
- **Total Denied:** 178 encounters, $490K at stake
- **Most adjustment codes are contractual** (CO45, CO237) — not true denials

### Top Denial Codes
| Code | Description | Count |
|------|-------------|-------|
| CO45 | Charges exceed contracted fee | Most common |
| CO237 | Legislated fee reduction | Common |

### Denials by Payer
| Payer | Count | Balance |
|-------|-------|---------|
| Colorado Medicare | 16 | $91,860 |
| CO Blue Shield OOS | 17 | $80,467 |
| United Healthcare | 27 | $73,165 |
| UMR | 19 | $63,156 |
| CO Blue Shield | 32 | $57,347 |

### Top 5 Highest-Value Denied Claims
1. $34,198 — Colorado Medicare — John Sielatycki (enc:15522549)
2. $33,898 — Colorado Medicare — Timothy Balise (enc:15535681)
3. $29,568 — CO Blue Shield OOS — John Sielatycki (enc:13888364)
4. $28,007 — CO Blue Shield OOS — Jason Mckown (enc:13888766)
5. $20,454 — Health First CO — John Sielatycki (enc:14737521)

### Assessment
Most "denials" are actually **contractual adjustments** (CO45/CO237) — Medicare/Medicaid paying contracted rates, not billing errors. True appealable denials are a small subset.

---

## 🔬 ITERATION #3: AR AGING ANALYSIS

### Summary
- **Total Pipeline + Denied:** 1,154 encounters, $2.05M AR
- **64% of AR is 0-30 days** — healthy, recent claims
- **Only 9.4% is >90 days** ($192K)

### Aging Buckets
| Bucket | Count | Balance | % |
|--------|-------|---------|---|
| 0-30 days | 746 | $1,318K | 64.2% |
| 31-60 days | 237 | $298K | 14.5% |
| 61-90 days | 99 | $245K | 11.9% |
| 91-120 days | 58 | $147K | 7.2% |
| 120+ days | 14 | $45K | 2.2% |

### Stale Claims Alert
- **65 claims >60 days in SUBMISSION_SUCCESS:** $118K at risk
- These should have paid by now — investigate

### Oldest High-Value Claims (>$5K, >90 days)
1. 126 days, $6,300 — WC-CORVEL — DENIED
2. 123 days, $12,287 — Cigna PPO — SUBMISSION_SUCCESS
3. 123 days, $11,200 — Cigna PPO — SUBMISSION_SUCCESS
4. 120 days, $5,761 — UMR — SUBMISSION_SUCCESS
5. 111 days, $10,198 — Colorado Medicare — SUBMISSION_SUCCESS

---

## 🔬 ITERATION #4: PAYMENT VARIANCE ANALYSIS

### High Variance CPTs (same CPT, different payer yields)
These CPTs show 20-60pp yield difference depending on payer:

| CPT | Min Yield | Max Yield | Spread | Billed |
|-----|-----------|-----------|--------|--------|
| 99213 | 19% | 52% | 33pp | $694K |
| 99214 | 19% | 50% | 31pp | $407K |
| 73721 | 10% | 31% | 22pp | $328K |
| 64483 | 14% | 35% | 21pp | $205K |
| 72148 | 9% | 69% | 61pp | $84K |

### Potential Underpayments (yield < CPT average)
These payer×CPT combos pay significantly below average:

| CPT | Payer | Yield | Avg | Gap | Billed |
|-----|-------|-------|-----|-----|--------|
| 72148 | Colorado Medicare | 8.5% | 39.9% | 31pp | $58K |
| 99204 | Colorado Medicare | 18.4% | 42.1% | 24pp | $59K |
| 99213 | Colorado Medicare | 19.0% | 39.2% | 20pp | $224K |
| 99214 | Colorado Medicare | 19.3% | 39.7% | 20pp | $141K |

**Note:** These are Medicare fee schedule gaps, not underpayments to appeal.

---

## 🔬 ITERATION #5: PROCEDURE-LEVEL PROFITABILITY

### Most Profitable CPTs (Excluding AS modifier)

**By Total Revenue:**
| CPT | Count | Paid | Yield |
|-----|-------|------|-------|
| 99213 (E/M) | 2,328 | $222K | 32.0% |
| 99214 (E/M) | 959 | $133K | 32.6% |
| 22856 (Spine) | 35 | $120K | 42.3% |
| 99203 (New pt) | 773 | $84K | 30.3% |
| 99204 (New pt) | 418 | $82K | 35.8% |

**Highest Yield (>40%):**
| CPT | Yield | Paid |
|-----|-------|------|
| 22858 | 48.2% | $30K |
| 29888 | 43.4% | $62K |
| 64721 | 43.1% | $34K |
| 22856 | 42.3% | $120K |
| 64718 | 39.3% | $43K |

### Low Yield CPTs (<15%) — Investigate
| CPT | Yield | Billed |
|-----|-------|--------|
| J1010 | 8.5% | $37K |
| 0232T | 2.0% | $36K |
| J0702 | 11.0% | $20K |

**Note:** J-codes are drugs — yield is expected to be lower due to manufacturer rebates and ASP-based pricing.

### Best CPT×Payer Combos
| CPT | Payer | Paid | Yield |
|-----|-------|------|-------|
| J3111 | Medicare | $30K | 93.2% |
| 99204 | CO Blue Shield | $19K | 56.4% |
| 99214 | UMR | $15K | 48.9% |
| 99213 | Cigna | $14K | 48.7% |
| 99213 | UMR | $22K | 47.6% |

---

## 🔬 ITERATION #6: TIME-SERIES / TREND ANALYSIS

### Monthly Collections Trend
| Month | Encounters | Billed | Collected | Yield |
|-------|------------|--------|-----------|-------|
| Nov 2025 | 1,056 | $1.12M | $340K | 📈 30.3% |
| Dec 2025 | 3,581 | $4.43M | $1.36M | 📈 30.6% |
| Jan 2026 | 2,943 | $2.43M | $443K | 📉 18.3% |
| Feb 2026 | 2,666 | $2.45M | $452K | 📉 18.5% |
| Mar 2026 | 2,067 | $1.43M | $63K | 📉 4.4% |

### ⚠️ CRITICAL INSIGHT: Payment Lag
The March 2026 4.4% yield is **NOT a problem** — it's **payment lag**:
- Claims billed in March haven't been paid yet
- Payment receipts by check date show money still flowing ($477K in March)
- Jan/Feb lower yield is also partially payment lag

### Payer Yield Trends
**Colorado Medicare:** Stable at ~13-15% (fee schedule)
**Colorado Blue Shield:** Dropped from 44% → 25% (more recent claims unpaid)
**United Healthcare:** Dropped from 47% → 13% (payment lag on recent claims)

### Status Trend — Key Observation
| Status | Nov | Dec | Jan | Feb | Mar |
|--------|-----|-----|-----|-----|-----|
| APPROVED | 648 | 2,389 | 1,755 | 1,325 | 229 |
| SUBMISSION_SUCCESS | 5 | 20 | 56 | 297 | 598 |
| MISSING_PROCEDURES | 195 | 464 | 636 | 640 | 952 |

**March encounters are still in pipeline** — SUBMISSION_SUCCESS (598) and MISSING_PROCEDURES (952) will convert to APPROVED as payments come in.

---

## 🎯 CONSOLIDATED ACTION ITEMS

### High Priority
1. **Work 65 stale claims (>60 days SUBMISSION_SUCCESS):** $118K — should have paid by now
2. **Top 5 denied claims ($146K total):** Review for appeal eligibility
3. **MISSING_PROCEDURES backlog (952 encounters):** What's blocking submission?

### Medium Priority
4. **Cigna PPO claims 123 days old ($23K):** Why stuck?
5. **WC-CORVEL denied claims:** Workers comp — may need additional documentation
6. **J1010 low yield (8.5%):** Is pricing correct?

### Monitoring
7. **Jan/Feb yield will improve** as payments catch up
8. **March pipeline ($1.04M)** — normal, just new

### NOT Actionable
- Medicare yield gaps — fee schedule, not billing error
- Contractual adjustments (CO45/CO237) — not true denials
