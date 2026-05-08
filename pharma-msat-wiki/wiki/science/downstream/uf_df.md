# Ultrafiltration & Diafiltration (UF/DF)

**Backlinks:** [downstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [downstream/drug_substance_to_patient.md](drug_substance_to_patient.md) | [product_quality/cqa_stability.md](../../product_quality/cqa_stability.md)

---

## Purpose of UF/DF

Ultrafiltration/Diafiltration (UF/DF) is the final purification-adjacent step in downstream processing. Its two functions:

1. **Concentration (Ultrafiltration):** Increase the protein concentration from the dilute polishing pool (~1–5 g/L typical after chromatography) to the target drug substance concentration (typically 10–50 g/L; up to 200 g/L for subcutaneous products requiring small injection volumes).

2. **Buffer exchange (Diafiltration):** Replace the purification buffer (high-salt, non-physiological pH) with the formulation buffer suited for long-term drug substance stability (typically 20–25 mM histidine pH 5.5–6.0, with excipients).

UF/DF is the step that directly determines the final drug substance formulation environment. Getting the buffer composition and protein concentration right at this step is critical for drug substance stability during frozen storage.

---

## Membrane Filtration Principles

### Tangential Flow Filtration (TFF)

UF/DF uses **tangential flow filtration (TFF)**, also called cross-flow filtration, rather than dead-end filtration.

In dead-end filtration, feed flows perpendicular to the membrane, and particles/molecules accumulate on the membrane surface (filter cake) until the membrane clogs. This works for cell removal (depth filtration, harvest) but is impractical for concentration because the protein would concentrate on the membrane surface, reducing flux to near-zero.

In TFF, feed flows **across (parallel to)** the membrane surface at high velocity, creating a shear force that continuously sweeps the membrane surface and prevents concentration polarization. A fraction of the fluid permeates through the membrane (the permeate or filtrate); the remainder (the retentate) is recirculated back to the feed tank. Protein (too large for the membrane) is retained in the retentate and concentrates over time; small molecules (buffer components, salts, small impurities) permeate freely.

### Ultrafiltration Membranes

Membrane pore size is characterized by the **molecular weight cut-off (MWCO)**: the molecular weight at which 90% of a solute is retained. For mAb concentration (MW ~150 kDa), the standard MWCO is **30 kDa**. This retains the mAb (150 kDa) while allowing buffer components and small molecules to permeate.

Some aggregates or very large species may be partially retained even more than the monomer; some fragmented species may permeate. UF/DF can therefore have a modest effect on aggregate levels (large aggregates concentrate further; cannot be removed).

**Membrane materials:** Regenerated cellulose (Millipore Pellicon) or polyethersulfone (PES, Sartorius Hydrosart). Regenerated cellulose has lower non-specific protein binding; PES has higher flux but more adsorption.

**Membrane configurations:** Flat-sheet cassettes (Pellicon, Sartocon) or hollow fibers. Cassettes are standard for manufacturing scale.

---

## UF/DF Process Steps

### Step 1: Concentration (UF)

The polishing pool (or the last chromatography pool, after AEX or HIC) is pumped into the TFF system. The retentate is recirculated at high cross-flow rate while the permeate is collected as waste (containing buffer salts and small impurities). The protein concentration in the retentate increases continuously.

**End point:** A target concentration (e.g., 50 g/L) or a target retentate volume.

### Step 2: Diafiltration (DF)

After concentration, formulation buffer is added to the retentate at the same rate as permeate is removed, maintaining constant volume. Each diafiltration volume (DV) added replaces the buffer composition by approximately 1/e (63%). After 5–7 DV, >99% of the original buffer components have been washed out and replaced with formulation buffer.

```
Fraction of original buffer remaining = e^(-n)
```
where n = number of diafiltration volumes. After 7 DV: e^(-7) = 0.0009 → <0.1% of original buffer remains.

### Step 3: Final Concentration (UF)

After diafiltration, the drug substance is concentrated to the final target concentration. Excipients may be added at this stage if they were not in the diafiltration buffer (e.g., a polysorbate 80 spike).

### Step 4: Hold and Flush

A hold step to equilibrate before proceeding to drug substance filtration and filling. A final membrane flush with formulation buffer is used to recover product from the hold-up volume in the system (important for yield accounting).

---

## Key Parameters and CPPs

| Parameter | Effect |
|---|---|
| Transmembrane pressure (TMP) | Controls flux rate; too high → membrane compression, fouling → reduced flux, risk of product damage |
| Cross-flow rate (CFR) | Sweeps membrane surface; inadequate CFR → concentration polarization → fouling |
| Temperature | Higher temp → lower viscosity → higher flux; also affects aggregation |
| Final protein concentration | Higher concentration → higher aggregation risk; viscosity increases steeply |
| Number of diafiltration volumes | Determines residual buffer component levels; more DV → cleaner exchange |
| Formulation buffer composition | pH, ionic strength affect protein solubility and aggregation tendency under UF conditions |

---

## Aggregation Risk During UF/DF

High protein concentration during UF is the biggest product quality risk of this step. As concentration increases:
- Local protein-protein interactions increase
- Viscosity increases rapidly (often >20 cP above 100–150 g/L)
- Shear forces during recirculation can induce aggregation

Mitigation strategies:
- Formulation optimization (excipients that prevent aggregation: sucrose, trehalose, histidine, surfactant)
- Controlled TMP and CFR to avoid excessive shear
- Temperature control (lower temperatures are generally more stabilizing, but lower flux)
- Adding surfactant (polysorbate) before or during concentration step

For highly concentrated products (>150 g/L, subcutaneous injection), the UF/DF process is a major development challenge that requires extensive formulation and process screening.

---

## Yield and Membrane Performance

Yield is the fraction of input protein recovered in the final retentate after the flush. Losses occur from:
- Membrane hold-up volume (protein adsorbed to or retained in membrane)
- Protein transmission through the membrane (some product permeates, especially for small aggregation fragments or if the membrane is damaged)
- Adsorption to system surfaces

Typical UF/DF step yield: 90–98%.

**Membrane integrity test (pre- and post-use):** Diffusion or bubble point test to confirm membrane integrity. A failed membrane (damaged pores) would allow protein to permeate and reduce step yield while also reducing the retentate concentration.

**Membrane reuse:** Unlike viral filtration membranes (always single-use), UF/DF membranes can be reused across multiple campaigns after cleaning and sanitization with NaOH. The number of reuse cycles must be validated (membrane reuse lifetime study).

---

## Osmolality and Formulation

The final drug substance formulation must achieve:
- Target osmolality (isotonic ~285 mOsm/kg for IV; hypertonic acceptable for SC)
- Target pH (confirmed after all excipient additions)
- Target protein concentration
- Target excipient concentrations

After UF/DF, the drug substance is tested for these parameters as part of in-process and release testing. The formulation buffer composition and the precision of the diafiltration process directly determine whether these targets are achieved.
