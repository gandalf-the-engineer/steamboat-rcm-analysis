# ROUND 4 FINDINGS — Actionable Revenue Gaps

## 🔬 4A: LYNN SLOAN vs SIELATYCKI COMPARISON

### Summary
| Metric | Lynn Sloan | Sielatycki | Gap |
|--------|------------|------------|-----|
| Overall Yield | 22.8% | 32.4% | -9.6pp |
| Total Billed | $974K | $1.86M | — |
| Total Paid | $222K | $603K | — |

### ROOT CAUSE: Payer Mix (NOT Performance)
Lynn Sloan's lower yield is driven by **payer mix**, not billing issues:

| Payer | Sloan % | Siel % | Sloan Yield | Siel Yield |
|-------|---------|--------|-------------|------------|
| Colorado Medicare | **48.4%** | 27.2% | 14.3% | 12.0% |
| CO Blue Shield | 13.8% | 17.6% | 34.2% | 45.5% |
| UMR | 7.1% | 10.1% | 46.7% | 63.2% |

**Key Insight:** Sloan has **48% Medicare** vs Sielatycki's **27%**. Medicare pays ~14% while commercial payers pay 35-65%. Her payer mix drags down overall yield.

### CPT Comparison
Sloan does pain management (64xxx codes) — Sielatycki doesn't do these at all:
- 64483: $205K, 20.4% yield — Sloan only
- 64493: $91K, 18.0% yield — Sloan only
- 64635: $72K, 22.6% yield — Sloan only

**Conclusion:** Different specialty, different payer mix. NOT a billing error.

---

## 🔬 4B: MODIFIER 22 DEEP DIVE ($76K, 4.4% yield)

### Status Breakdown
| Payer | Status | Count | Billed | Paid |
|-------|--------|-------|--------|------|
| Cigna | SUBMISSION_SUCCESS | 3 | $23,450 | $0 |
| CO Blue OOS | APPROVED | 1 | $8,458 | $3,367 |
| CO Blue OOS | SUBMISSION_SUCCESS | 2 | $13,300 | $0 |
| Medicare | APPROVED | 2 | $11,080 | $0 |
| Medicare | DENIED | 1 | $8,458 | $0 |
| UMR | SUBMISSION_SUCCESS | 2 | $11,080 | $0 |

### Key Findings
1. **58% still in pipeline** (7 of 12) — too early to judge
2. **Medicare paying $0** even on APPROVED claims — fee schedule doesn't cover mod 22 premium
3. **Only CO Blue Shield OOS paid** ($3,367 on $8,458 = 40%)
4. **One denied claim** (Medicare $8,458)

### Assessment
⚠️ **Documentation issue likely:** Medicare is approving but paying $0, suggesting the documentation supports medical necessity but not the "increased complexity" requirement. Commercial payers may be more lenient.

**Recommendation:** Review op notes for the 4 adjudicated claims. Do they explicitly document why the procedure was more complex than typical?

---

## 🔬 4C: MODIFIER 59 DEEP DIVE ($226K, 17.7% yield)

### By CPT Code
| CPT | Count | Billed | Paid | Yield |
|-----|-------|--------|------|-------|
| 22856 | 4 | $33,832 | $6,014 | 17.8% |
| 22551 | 3 | $26,484 | $7,097 | 26.8% |
| 22845 | 5 | $18,805 | $1,866 | 🔴 9.9% |
| 63047 | 3 | $17,205 | $3,556 | 20.7% |
| 25210 | 3 | $7,683 | $571 | 🔴 7.4% |
| 26055 | 2 | $6,148 | $0 | 🔴 0.0% |
| 27769 | 1 | $3,950 | $0 | 🔴 0.0% |

### Low Yield Mod 59 — XE/XS/XP/XU Candidates
These CPTs are getting bundled even with Mod 59:
- **22845** (spinal fusion): 9.9% yield — try XS (separate structure)
- **25210** (wrist): 7.4% yield — try XE (separate encounter)
- **26055** (finger): 0% yield — try XP (separate practitioner)
- **27769** (ankle): 0% yield — try XS

**Recommendation:** CMS replaced Mod 59 with X-modifiers (XE, XS, XP, XU) in 2015. Many payers now prefer these more specific modifiers. Consider updating coding practice.

---

## 🔬 4D: MISSING PROCEDURES ANALYSIS (2,887 encounters)

### Trend — GETTING WORSE ⚠️
| Month | Missing | Total | % Missing |
|-------|---------|-------|-----------|
| Nov 2025 | 195 | 1,056 | 18.5% |
| Dec 2025 | 464 | 3,581 | 13.0% |
| Jan 2026 | 636 | 2,943 | 21.6% |
| Feb 2026 | 640 | 2,666 | 24.0% |
| Mar 2026 | **952** | 2,067 | **46.1%** |

**March has 46% missing procedures!** This is a critical operational issue.

### By Provider
| Provider | Count | % of Total |
|----------|-------|------------|
| Mri Mri Johnston | 447 | 15.5% |
| Alejandro Miranda | 222 | 7.7% |
| David Ward | 214 | 7.4% |
| Alexander Meininger | 212 | 7.3% |
| Patrick Johnston | 201 | 7.0% |

**Note:** "Mri Mri Johnston" appears to be MRI facility billing, not a provider issue.

### By Facility
| Facility | Count | % |
|----------|-------|---|
| Main Clinic | 1,958 | 67.8% |
| MRI SOSI | 447 | 15.5% |
| FRASER | 194 | 6.7% |
| Rock Springs | 116 | 4.0% |

### Root Cause Hypothesis
The March spike (46%) suggests a **system or workflow change**. Possible causes:
1. New EHR integration issue
2. Changed charge capture process
3. Staff training gap
4. Billing software update

**Recommendation:** Investigate what changed in March. This is costing significant revenue.
