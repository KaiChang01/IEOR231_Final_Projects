# Viral Clearance

**Backlinks:** [downstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [downstream/chromatography_mab_purification.md](chromatography_mab_purification.md) | [regulatory/ich_guidelines.md](../../../regulatory/ich_guidelines.md)

---

## Why Viral Safety is Non-Negotiable

Biopharmaceuticals are produced in living cells. Living cells can harbor viruses. The cell culture medium may contain animal-derived components (serum, trypsin, other supplements) that can introduce adventitious viral contaminants. Even CHO cells can carry endogenous retrovirus-like particles (ERVPs), which while non-pathogenic, represent a viral particle burden in the culture.

The consequences of a viral contamination event in manufacturing range from serious (product recall, patient harm) to catastrophic (manufacturing site shutdown). ICH Q5A requires that manufacturers demonstrate their downstream process can reliably remove or inactivate viruses to a level that ensures patient safety, even in the worst-case scenario of an undetected introduction of virus into the culture.

**The regulatory logic:** You cannot guarantee that the upstream process will always be perfectly sterile and free of adventitious agents. Therefore, the downstream process must provide a defined safety margin, quantified as log reduction factor (LRF).

---

## ICH Q5A and the Regulatory Framework

ICH Q5A ("Viral Safety Evaluation of Biotechnology Products Derived from Cell Lines of Human or Animal Origin") is the governing guideline. It requires:

1. **Cell line testing:** The production cell line must be tested for the presence of endogenous viruses and retrovirus-like particles. CHO cells have an established profile.
2. **Raw material testing:** Animal-derived raw materials must be tested and/or virus-inactivated (e.g., gamma irradiation of serum).
3. **Adventitious agent testing:** Bulk harvest and in-process samples are tested for adventitious viral contamination.
4. **Viral clearance validation:** The downstream process must be validated to demonstrate quantitative removal/inactivation of model viruses.

---

## Viral Clearance Validation

### Model Viruses

Because the actual adventitious viruses of concern cannot be used in validation studies (for safety reasons), **model viruses** are used. These are selected to be:
- Relevant models for specific virus classes of concern
- Worst-case models in terms of resistance to inactivation/clearance

The standard panel includes:

| Virus | Properties | What it models |
|---|---|---|
| MuLV (murine leukemia virus) | Enveloped, retrovirus, ~100 nm | Retrovirus-like particles endogenous to CHO cells |
| PRV (pseudorabies virus) | Enveloped, large, ~180 nm | Large enveloped viruses |
| MMV (minute virus of mice) | Non-enveloped, parvovirus, ~20 nm | Small non-enveloped viruses (worst-case for filtration) |
| Reo-3 (reovirus) | Non-enveloped, dsRNA, ~75 nm | Non-enveloped viruses |
| X-MuLV (xenotropic MuLV) | Enveloped retrovirus | Retrovirus-like particles |

The panel must include at least one small, non-enveloped, hard-to-kill virus (typically parvovirus MMV) and at least one retrovirus model.

### Log Reduction Factor (LRF)

```
LRF = log10 (virus load in input) - log10 (virus load in output)
```

A 4-log reduction means the virus level was reduced 10,000-fold. Regulatory guidance suggests that a combined LRF of ≥12 logs for retroviruses and ≥18 logs for non-enveloped viruses is considered adequate for patient safety (though specific requirements depend on the product and regulatory authority).

### Study Design

Viral clearance validation is performed at small scale (scale-down models of each unit operation) by spiking a known concentration of model virus into the process stream and measuring the titer in the output. The reduction factor is calculated for each step.

The studies are performed by specialized contract labs (e.g., Virusure, BioReliance, Charles River Laboratories) under biosafety level 2 (BSL-2) conditions.

---

## The Two Standard Viral Clearance Steps

The platform for mAb DSP includes two orthogonal viral clearance steps, positioned to cover both enveloped and non-enveloped viruses:

### Step 1: Low-pH Viral Inactivation

**Mechanism:** Enveloped viruses are inactivated by exposure to low pH. The acid disrupts the viral lipid envelope, irreversibly destroying the virus.

**Operation:**
- The Protein A eluate (already at low pH from the acetate/citrate elution buffer) is adjusted to pH 3.3–3.8
- Hold for a minimum time at this pH (typically ≥30–60 minutes at 15–25°C)
- After the hold, the pH is neutralized (typically to pH 5.0–6.0) before the next step

**Viruses inactivated:** All enveloped viruses — retroviruses (MuLV, X-MuLV, XMRV), herpesviruses (PRV), rhabdoviruses, etc.

**Viruses NOT inactivated:** Non-enveloped viruses (MMV, Reo-3). Non-enveloped viruses lack a lipid membrane and are not affected by pH treatment.

**Key CPPs:**
- pH (must be maintained below the inactivation threshold)
- Duration of hold (minimum time must be exceeded)
- Temperature (affects inactivation rate)
- Conductivity (can affect pH meter calibration accuracy)
- Product concentration (concentrated product can buffer the pH)

**Risk for product:** Low-pH conditions can cause mAb aggregation and deamidation. The conditions (pH × time) must be minimized to inactivate virus without damaging the product. This is why process characterization of this step studies the trade-off between viral inactivation (requires lower pH or longer time) and product quality (tolerates less).

### Step 2: Viral Filtration (Nanofiltration)

**Mechanism:** Physical size exclusion. A membrane with pore size of ~20 nm (Planova 20N, Viresolve Pro) or 15 nm (Planova 15N) retains virus particles while allowing the mAb (diameter ~10–15 nm for the unfolded form; ~10–14 nm Stokes diameter) to pass through.

**Operation:**
- Drug substance stream is filtered through a single-use nanofiltration membrane
- Viruses are retained on the membrane (upstream side)
- Filtered product continues to the next step
- Filters are used once (single-use); no reuse or sanitization

**Viruses removed:** Both enveloped and non-enveloped viruses, including parvovirus MMV (20 nm). This step provides the critical clearance for small non-enveloped viruses that are resistant to pH treatment.

**Key CPPs:**
- Transmembrane pressure (TMP)
- Flux rate (too high → membrane fouling → reduced flow and LRF)
- Maximum volume filtered per membrane area (validated capacity)
- Product concentration (high concentration → fouling)
- Temperature

**Orthogonality with low-pH inactivation:** These two steps work by completely different mechanisms — one is chemical inactivation of the viral envelope, the other is physical size exclusion. A virus would have to be simultaneously resistant to low pH (unlikely for enveloped viruses) AND small enough to pass through a 20 nm membrane (impossible for most viruses). This orthogonality is why the combination provides robust safety margins.

---

## Additional Viral Clearance From Other Steps

Chromatography steps also contribute to viral clearance, though they are not relied upon as the primary clearance steps:

- **Protein A chromatography:** LRF of 2–3 logs for retroviruses (binding conditions favor retention of some virus; low-pH elution and NaOH sanitization also contribute)
- **AEX flow-through:** Viruses (negatively charged) bind to the positively charged AEX resin; LRF of 3–4 logs for many viruses

These are counted in the total viral clearance package but provide redundancy, not primary clearance. The regulatory strategy requires at least two robust, validated clearance steps.

---

## Viral Testing in Manufacturing

In addition to process-level viral clearance, in-process and final testing confirms absence of detectable virus:

- **Bulk harvest testing:** Tested for adventitious viral contamination before downstream processing begins
- **Cell culture end-of-production testing:** End-of-production cells tested for retrovirus, adventitious agents
- **Drug substance testing:** Final BDS is sometimes tested for bioburden/adventitious agents (product-specific)

These tests are the detection layer; viral clearance validation is the prevention layer. Both are required.
