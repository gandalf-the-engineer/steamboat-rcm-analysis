# STEAMBOAT ORTHO - ROUND 3+ FINDINGS

## 🔬 ROUND 3: MODIFIER ANALYSIS (CRITICAL FINDING)

### ⚡ KEY DISCOVERY: AS Modifier Explains "Low Yield" Providers

**AS (Assistant Surgeon) Modifier Impact:**
- AS modifier pays ~16% of primary surgeon rate (by design)
- This is NOT a billing error — it's how assistant surgeon billing works

**Provider Analysis WITH Modifier Context:**

| Provider | Overall Yield | Non-AS Yield | AS % of Work | Role |
|----------|--------------|--------------|--------------|------|
| John Sielatycki | 32.4% | 32.4% | 0.0% | Primary Surgeon |
| Timothy Balise | 8.6% | **37.5%** | **88.1%** | Assistant Surgeon |
| Khristin Degli | 7.1% | **21.6%** | **79.5%** | Assistant Surgeon |
| Jason Mckown | 8.8% | **24.8%** | **73.9%** | Assistant Surgeon |
| Michael Hickey | 10.7% | 24.6% | 66.9% | Mostly Assistant |

**CONCLUSION:** Balise, Degli, Mckown, and Hickey are NOT underperforming.
They are assistant surgeons — their low overall yield is **expected and appropriate**.

When excluding AS procedures:
- Balise actually yields **37.5%** (above average!)
- Degli yields **21.6%** (reasonable)
- The "problem" we identified in Round 2 was actually the ROLE, not the performance

---

### Other Modifier Insights

**Low Yield Modifiers (Potential Issues):**
| Modifier | Description | Yield | Billed | Potential Issue |
|----------|-------------|-------|--------|-----------------|
| 22 | Increased Services | 4.4% | $76K | Documentation may not support |
| 80 | Assistant Surgeon | 2.3% | $25K | Similar to AS — role-based |
| TC | Technical Component | 11.2% | $143K | Facility portion often reduced |
| 59 | Distinct Service | 17.7% | $226K | Bundling/unbundling scrutiny |

**High Yield Modifiers:**
| Modifier | Description | Yield | Billed |
|----------|-------------|-------|--------|
| JZ | No Wastage | 63.3% | $90K |
| 24 | Unrelated E/M | 50.6% | $12K |
| F6 | Finger modifier | 50.1% | $25K |
| 95 | Synchronous Telemedicine | 41.2% | $51K |

---

## 🔬 ROUND 4: ADJUSTED PROVIDER VIEW

**Actual Concerns (Non-AS yield <25%, minimal AS work):**
- Lynn Sloan: 22.8% yield, $974K billed (0% AS)
- Alejandro Miranda: 24.4% yield, $783K billed (0% AS)
- Jay Thompson: 24.9% yield, $670K billed (0% AS)
- David Ward: 23.2% yield, $238K billed (0% AS)

These providers do primarily non-AS work but yield below the 28-32% benchmark.
Worth investigating, though yields are not critically low.

---

## 🔬 ROUND 5: FACILITY ANALYSIS

| Facility | Overall Yield | Non-AS Yield | AS % | Billed |
|----------|--------------|--------------|------|--------|
| Steamboat Surgery Center | 20.9% | 31.4% | 39.0% | $3.4M |
| Steamboat Springs Ortho Main | 27.4% | 27.6% | 0.7% | $3.4M |
| UCH Yampa Valley Medical | 16.3% | 22.8% | 31.7% | $2.7M |
| MRI SOSI | 24.7% | 24.7% | 0.0% | $824K |
| Aspen Mountain Medical | 33.8% | 47.1% | 32.2% | $476K |

**Note:** UCH Yampa Valley Medical Center OP has 68.6% AS work — this is an outpatient
facility primarily billing assistant surgeon services.

---

## 🔬 ROUND 6: PIPELINE ANALYSIS

**SUBMISSION_SUCCESS (Pipeline):** 976 encounters, $1.49M

**By Timing:**
| Month | Encounters | Billed |
|-------|------------|--------|
| 2025-11 | 5 | $30K |
| 2025-12 | 20 | $49K |
| 2026-01 | 56 | $52K |
| 2026-02 | 297 | $317K |
| 2026-03 | 598 | $1.04M |

Most pipeline is recent (March 2026) — expected as claims take time to process.

**Pipeline by Payer:**
- Colorado Medicare: 272 enc, $380K (28% of pipeline)
- Colorado Blue Shield: 171 enc, $243K
- United Healthcare: 125 enc, $198K

---

## 🔬 ROUND 7: PAYMENT ANALYSIS

**Insurance Payments:** $3.26M across 11,880 records
- Posting lag: Mean 1.1 days (excellent)
- Top payer: CO Blue Shield $712K

**Patient Payments:** $1.09M
- Smart Pay: $582K (53%)
- Stripe Card: $436K (40%)
- Check/Cash: $72K (7%)

---

## 🎯 REVISED RECOMMENDATIONS

### Previous Issues Resolved:
1. ~~Colorado Medicare low yield~~ → Expected (fee schedule difference)
2. ~~Low yield providers (Balise/Degli)~~ → They're assistant surgeons (expected)

### Actual Action Items:
1. **Modifier 22 claims ($76K, 4.4% yield)** — Review documentation for "increased services"
2. **Modifier 59 claims ($226K, 17.7%)** — Check for bundling/unbundling issues
3. **Lynn Sloan investigation** — Primary surgeon with 22.8% yield, no AS excuse
4. **UCH Yampa Valley OP (7.4% yield)** — High AS%, but even non-AS is only 17.7%
5. **178 denied claims ($490K)** — Still worth working appeals

### Metrics to Reframe:
- Don't compare assistant surgeons to primary surgeons
- Report yields EXCLUDING AS modifier for fair comparison
- AS modifier work is a REVENUE STREAM, not a problem
