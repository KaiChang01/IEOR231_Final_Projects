# Critical Quality Attributes & Stability

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [product_quality/product_related_impurities.md](product_related_impurities.md) | [product_quality/cqa_cpp_process_control.md](cqa_cpp_process_control.md) | [tech_transfer/process_characterization.md](../../../tech_transfer/process_characterization.md) | [regulatory/ich_guidelines.md](../../../regulatory/ich_guidelines.md)

---

## What is a Critical Quality Attribute?

A **Critical Quality Attribute (CQA)** is a physical, chemical, biological, or microbiological property or characteristic that should be within an appropriate limit, range, or distribution to ensure the desired product quality.

The definition is from ICH Q8(R2) and is the foundational concept that connects manufacturing science to regulatory strategy. The two-part test for CQA designation:

1. **Criticality:** The attribute has the potential, if outside its acceptable range, to affect the safety or efficacy of the product
2. **Measurability:** The attribute can be quantified by an analytical method with appropriate accuracy and precision

A CQA is not just any measurable attribute — it is one that is linked to patient outcomes. This linkage may be direct (potency assay measures the attribute that kills tumor cells) or indirect (aggregation level is linked to immunogenicity risk, which affects patient safety).

---

## CQA Categories for Monoclonal Antibodies

### 1. Potency / Biological Activity

The single most important CQA. Regulatory agencies require that every lot of drug substance be released against a potency specification that is directly linked to the MoA.

Types of potency assays:
- **Binding assay (ELISA or SPR):** measures affinity/avidity for the target antigen. Rapid and precise, but measures binding rather than biological function.
- **Cell-based bioassay:** measures the biological response of living cells to the antibody (e.g., cell killing, proliferation inhibition, cytokine release). Slow, variable, expensive, but captures the functional consequence most directly.
- **Reporter gene assay:** engineered cell line with a luciferase reporter linked to the pathway activated by the mAb. Higher throughput than cell-based, better precision.

Specifications: typically set as % relative potency vs. a reference standard (e.g., 60–140% relative potency).

### 2. Purity

**Size-based purity (% monomer):** Measured by SEC-HPLC. Specification typically ≥95% or ≥98% monomer. Residual aggregates are the key impurity tracked.

**Charge-based purity (% main peak):** Measured by icIEF. Specification varies by molecule; may be ≥70–80% main peak. Deamidation and C-terminal Lys variants are the dominant contributors.

**SDS-PAGE purity:** Reduced and non-reduced gel electrophoresis to detect fragments and misassembled forms. CE-SDS is the more quantitative modern format.

### 3. Identity

Confirmation that the protein is the intended molecule:
- Peptide map (primary structure confirmation, PTM identification)
- Intact mass (molecular weight)
- Isoelectric point (icIEF pI value)
- N-terminal sequencing (Edman degradation — historical) or MS-based

### 4. Glycosylation

For ADCC-dependent mAbs: fucosylation%, high mannose%. For all mAbs: site occupancy (% aglycosylated). See [protein_structure/glycosylation.md](../protein_structure/glycosylation.md).

### 5. Safety Attributes

- Sterility (USP <71>)
- Endotoxin / bacterial endotoxins test (BET / LAL assay)
- Residual host cell proteins (HCP ELISA, ng HCP per mg drug substance)
- Residual host cell DNA (qPCR, ng DNA per dose)
- Residual Protein A (ELISA)
- Adventitious agents / viral clearance (safety testing from manufacturing process)

### 6. Quantity

- Protein concentration (A280 UV absorbance using extinction coefficient)
- Fill volume (for drug product)

---

## Stability of Biopharmaceuticals

Stability is not a single CQA but a collection of attributes that change over time. ICH Q5C governs stability testing for biotechnology products.

### Degradation Pathways

**Chemical degradation:**
- Deamidation (Asn → Asp/isoAsp) — primary driver of acidic variant accumulation; accelerated by heat, pH >6
- Oxidation (Met, Trp) — driven by reactive oxygen species, light, metal ions; accelerated by heat, peroxide
- Glycation (Lys + glucose) — can occur in sugar-containing formulations
- Hydrolysis (hinge peptide bonds) — fragmentation; driven by acid, heat

**Physical degradation:**
- Aggregation — irreversible loss of monomer; driven by temperature, freeze-thaw, shear, concentration, pH near pI
- Subvisible and visible particle formation — a consequence of aggregation at higher severity
- Adsorption to surfaces (vials, tubing, syringes) — loss of drug; especially at low concentrations

### Formulation Strategy for Stability

The formulation (drug substance and drug product buffer) is designed to minimize degradation:

| Challenge | Formulation response |
|---|---|
| Aggregation | Surfactant (polysorbate 20 or 80), stabilizing sugars (sucrose, trehalose), controlled protein concentration |
| Oxidation | Avoid metal ions; headspace nitrogen; consider methionine as sacrificial antioxidant |
| Deamidation | pH 5–6 formulation (lower pH slows deamidation) |
| Freeze-thaw stress | Cryoprotectants (sucrose, trehalose); controlled freezing rate |
| pH-mediated degradation | Buffering agents (histidine, citrate, acetate) |

The typical mAb formulation is: 20–25 mM histidine buffer, pH 5.5–6.0, with 5–10% sucrose or trehalose, and 0.02–0.04% polysorbate 80.

### Stability Study Design (ICH Q5C)

| Study type | Temperature | Duration | Purpose |
|---|---|---|---|
| Long-term | 2–8°C | 24–36 months | Set shelf life |
| Accelerated | 25°C / 40°C | 3–6 months | Predict long-term, inform formulation |
| Stress | 40–50°C, cycles, light | Weeks | Identify degradation pathways |
| Freeze-thaw | Cycling −80°C ↔ room temp | Multiple cycles | Assess freeze-thaw robustness |
| In-use | Simulated clinical use | Hours | Set in-use stability claims |

---

## CQA Criticality Assessment: Risk-Based Approach

Not all attributes are equally critical. A formal criticality assessment assigns a risk level to each attribute based on:

- **Severity:** How harmful is it if the attribute is out of specification? (patient safety, efficacy loss)
- **Probability:** How likely is it that the attribute will go out of specification given normal process variability?
- **Detectability:** Will out-of-specification lots be detected before release?

This is documented in a **risk assessment matrix** (sometimes a Failure Mode and Effects Analysis, FMEA) and is reviewed by regulators as part of the CMC package.

| Risk level | CQA designation | Control strategy |
|---|---|---|
| High severity + high probability | CQA with tight specification | In-process controls + release testing |
| High severity + low probability | CQA with specification | Release testing |
| Low severity | Non-CQA attribute | Monitor, may not specify |

This framework is described in ICH Q9 (Quality Risk Management). See: [regulatory/ich_guidelines.md](../../../regulatory/ich_guidelines.md)
