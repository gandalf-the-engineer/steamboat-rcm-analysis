# STEAMBOAT ORTHO - ROUND 2 DEEP DIVE FINDINGS

## 🔬 DEEP DIVE #1: Colorado Medicare Root Cause

**The Problem:** 12.4% yield vs 30% benchmark = $588K gap

**Key Finding:** Even APPROVED Medicare claims only yield 14.4%
- This is NOT a denial problem - it's a payment problem
- CO45 (contractual) write-offs dominate the adjustment reasons
- 272 claims ($380K) still in pipeline (SUBMISSION_SUCCESS)

**Root Cause Analysis:**
- Medicare fee schedule may be significantly below billed amounts
- The 14.4% yield on APPROVED claims suggests the issue is:
  - Fee schedule mismatch (billing above Medicare rates)
  - OR systemic underpayment that needs appeal

**Critically Low Yield Medicare CPTs (<10%):**
| CPT | Description | Billed | Yield |
|-----|-------------|--------|-------|
| 27447 | Knee replacement | $181K | 9.1% |
| 22856 | Spine surgery | $82K | 5.4% |
| 29827 | Shoulder arthroscopy | $86K | 9.9% |
| 73721 | MRI lower extremity | $75K | 9.7% |
| 72148 | MRI lumbar spine | $58K | 8.5% |

**Recommendation:** Audit Medicare fee schedule alignment. If billed amounts are 
7-10x Medicare allowed amounts, the yield will always look low due to contractual 
write-offs. Consider adjusting expectations OR appealing systematic underpayments.

---

## 🔬 DEEP DIVE #2: Low Yield Provider Investigation

**Timothy Balise (8.6% yield):**
- $895K billed, $77K collected
- Top CPT: 22856 (spine surgery) at 7.6% yield
- Colorado Medicare: 3.6% yield (!!!)
- 80% of his work is APPROVED - the issue is payment, not status
- Same CPTs as John Sielatycki, but 4x lower yield

**Khristin Degli (7.1% yield):**
- $727K billed, $52K collected
- Top CPT: 27447 (knee replacement) at 3.5% yield
- Colorado Medicare: 6.8% yield
- Heavy surgery caseload with expensive procedures

**vs John Sielatycki (32.4% yield):**
- SAME CPT mix (22856, 63047, 22633)
- SAME payer mix (CO Medicare, CO Blue Shield, UMR)
- BUT 4x higher yield

**Root Cause:** NOT the procedures or payers - something in the billing/coding 
process differs between providers. Possible causes:
- Documentation differences
- Authorization handling
- Modifier usage
- Appeal follow-through

**Recommendation:** Pull 10 random claims from Balise/Degli and compare to 
Sielatycki for same CPT+payer combinations. Look for documentation, auth, 
and coding differences.

---

## 🔬 DEEP DIVE #3: Denial Pattern Analysis

**Total Denied:** 178 encounters, $490K at stake

**By Payer:**
1. Colorado Medicare: 16 enc, $92K
2. CO Blue Shield OOS: 17 enc, $80K
3. United Healthcare: 27 enc, $73K
4. UMR: 19 enc, $63K
5. CO Blue Shield: 32 enc, $57K

**Denial Categories:**
- 🟢 Contractual (CO45/CO237): Most adjustments - legitimate fee schedule
- 🟡 Auth-related: "NO AUTH" manual write-offs by Shandy Deakins
- ⚪ Other: Accidental write-offs, manual pushes

**Highest Value Denied Encounters:**
1. $34K - Medicare - CPT 22514 (spine fusion)
2. $34K - Medicare - CPT 22514 (spine fusion)
3. $30K - CO Blue Shield OOS - Complex spine
4. $28K - CO Blue Shield OOS - Complex spine

**Recommendation:** The two $34K Medicare 22514 denials should be prioritized
for appeal review. Auth-related denials need process improvement.

---

## 🔬 DEEP DIVE #4: CPT × Payer Yield Matrix

**Massive Yield Spreads Identified:**
| CPT | Best Payer | Yield | Worst Payer | Yield | Gap |
|-----|------------|-------|-------------|-------|-----|
| J7318 | United | 63% | Medicare | 12% | 51pp |
| 22633 | UMR | 50% | CO Blue OOS | 0% | 50pp |
| 64483 | UMR | 58% | Medicare | 12% | 46pp |
| 22856 | United Shared | 50% | Medicare | 5% | 45pp |
| 99204 | Cigna | 62% | Medicare | 18% | 43pp |

**Pattern:** Colorado Medicare is consistently the WORST payer for almost every 
high-value CPT. Commercial payers (UMR, Cigna, United) pay 3-5x better rates.

**Key Insight:** The same procedure can yield 5% or 50% depending on payer.
This suggests either:
- Medicare fee schedule is appropriately low (expected)
- OR commercial payers are being billed correctly while Medicare is not

---

## 🎯 CONSOLIDATED RECOMMENDATIONS

### Immediate Actions (This Week)
1. **Review 2 Medicare 22514 denials** ($68K) - appeal candidates
2. **Audit auth workflow** - Shandy Deakins' manual write-offs indicate process gap
3. **Pull Balise/Degli sample claims** - compare to Sielatycki for coding differences

### Short-term (This Month)
4. **Medicare fee schedule audit** - verify billed amounts vs allowed
5. **Payer-specific yield investigation** - why 0% on some payer×CPT combos?
6. **Documentation training** for low-yield providers

### Medium-term
7. **Re-evaluate Medicare yield expectations** - 30% may be unrealistic if fee schedule 
   dictates 15% is "correct"
8. **Build payer-specific billing rules** to avoid known denial patterns
