# ROUND 5 FINDINGS — Recoverable Revenue Analysis

## 🔬 5A: PIPELINE AGING & TIMELY FILING RISK

### Summary
- **Total Pipeline:** 976 encounters, $1.49M
- **Healthy:** 92% is within 60 days (on track)
- **At risk:** 18 encounters, $66K >90 days

### Aging Breakdown
| Bucket | Count | Balance | % | Risk |
|--------|-------|---------|---|------|
| 0-30 days | 718 | $1.19M | 79.6% | 🟢 On track |
| 31-60 days | 193 | $186K | 12.5% | 🟢 Normal |
| 61-90 days | 47 | $51K | 3.4% | 🟡 Monitor |
| 91-120 days | 16 | $43K | 2.9% | 🔴 At risk |
| 120+ days | 2 | $23K | 1.6% | 🔴 Critical |

### Timely Filing Risk (>90 days)
| Payer | Count | Balance | Filing Limit |
|-------|-------|---------|--------------|
| Cigna PPO | 3 | $23,910 | 90-180 days |
| United Healthcare | 2 | $12,952 | 90-180 days |
| Colorado Medicare | 3 | $11,755 | 365 days |
| UMR | 1 | $5,761 | 90-180 days |

⚠️ **CRITICAL:** 4 claims at 120+ days ($29,553) — FILE IMMEDIATELY

---

## 🔬 5B: APPEALABLE DENIALS ANALYSIS

### Key Finding
Most denials in this data are **already written off** with internal codes (WRITE_OFF, WRITE_OFF_PR), not standard CARC denial codes.

| Code | Category | Est. Balance |
|------|----------|--------------|
| WRITE_OFF | Internal | $52,982 |
| WRITE_OFF_PR | Internal | $25,633 |
| MEDICAID | Internal | $5,262 |
| CO45 | Contractual | $706 |

### Assessment
The denial data shows **internal write-off reasons**, not payer denial codes. This suggests:
1. Denials were already worked and written off
2. The $490K "denied" balance may already be closed
3. True appealable denials may be a small subset

**Recommendation:** Verify with billing team whether these are truly open denials or already-closed write-offs.

---

## 🔬 5C: FACILITY-LEVEL YIELD ANALYSIS

### Facility Yield (Non-AS procedures)
| Facility | Count | Billed | Yield | vs Avg |
|----------|-------|--------|-------|--------|
| Main Clinic | 8,610 | $3.39M | 27.4% | ➡️ Baseline |
| MRI SOSI | 1,097 | $824K | 24.7% | 🔴 -2.7pp |
| Surgery Center | 757 | $3.40M | 20.9% | 🔴 -6.5pp |
| UCH Yampa Valley | 596 | $2.72M | 16.3% | 🔴 -11.1pp |
| FRASER | 680 | $187K | 33.7% | 🟢 +6.3pp |
| Rock Springs | 470 | $116K | 37.9% | 🟢 +10.5pp |

### Low Yield Facility Analysis: UCH Yampa Valley (16.3%)
**Root cause:** Heavy Medicare mix + technical component billing
- UCH is a hospital facility — different fee schedules
- High TC modifier usage (facility-only billing)
- NOT a credentialing issue — expected for hospital-based billing

### Low Yield: Surgery Center (20.9%)
**Root cause:** AS modifier concentration (39% of billed is AS)
- Surgery centers have more assistant surgeon procedures
- When you remove AS, yield is 31.4% (normal)

---

## 🔬 5D: PAYMENT VELOCITY BY PAYER

### Slowest Payers (>30 days avg)
| Payer | Avg Days | Median | Yield |
|-------|----------|--------|-------|
| WC-CORVEL | 33d | 34d | 38.1% |
| AETNA PPO | 31d | 34d | 32.9% |
| United Healthcare | 31d | 30d | 41.6% |
| UMR | 30d | 27d | 52.6% |

### Fastest Payers (<20 days avg)
| Payer | Avg Days | Yield |
|-------|----------|-------|
| TriWest | 14d | 16.4% |
| Health First CO | 15d | 17.9% |
| Humana | 16d | 12.7% |
| TRICARE | 18d | 12.6% |
| Pinnacol | 19d | 31.5% |

### Key Insight
**Speed ≠ Yield.** The fastest payers (TriWest, Medicaid, TRICARE) have the LOWEST yields (12-17%). They pay fast but pay little.

The best payers are:
- **Cigna PPO:** 22d avg, 57.4% yield
- **Cigna:** 22d avg, 47.7% yield
- **UMR:** 30d avg, 52.6% yield (slow but pays well)
- **Colorado Blue Shield:** 21d avg, 40.6% yield

### Problem Payers (slow + low yield)
None identified — slow payers (WC-CORVEL, United) still pay reasonably well (38-42%).

---

## 🎯 CONSOLIDATED RECOVERY OPPORTUNITY

### Immediate Action Items
| Item | Amount | Action |
|------|--------|--------|
| 4 claims at 120+ days | $30K | FILE TODAY |
| 14 claims at 91-120 days | $43K | Escalate to payers |
| Verify "denied" write-offs | $490K | Check if truly open |

### Monitoring
| Item | Amount | Status |
|------|--------|--------|
| 0-60 day pipeline | $1.37M | On track ✅ |
| 61-90 day pipeline | $51K | Monitor weekly |

### Not Recoverable
| Item | Amount | Reason |
|------|--------|--------|
| UCH Yampa low yield | — | Hospital fee schedule |
| Surgery Center low yield | — | AS modifier (by design) |
| Medicare yield gap | — | Fee schedule difference |
