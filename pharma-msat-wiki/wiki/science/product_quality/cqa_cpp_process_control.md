# CQAs, CPPs, and Process Control

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [product_quality/cqa_stability.md](cqa_stability.md) | [tech_transfer/process_characterization.md](../../../tech_transfer/process_characterization.md) | [regulatory/ich_guidelines.md](../../../regulatory/ich_guidelines.md)

---

## The Central Framework

The conceptual spine of biopharmaceutical manufacturing science is the **CQA–CPP linkage**: the mapping from process parameters to product quality attributes.

```
Material attributes + Process parameters → CQAs → Safety & Efficacy
```

If you understand this map — which parameters affect which attributes, and how strongly — you can:
- Design a process that consistently delivers acceptable product
- Identify where to place controls
- Predict the impact of deviations and process changes
- Write a rational control strategy for regulators

This framework is codified in ICH Q8 (Pharmaceutical Development) and is required for all modern biopharmaceutical CMC filings.

---

## Definitions

**Critical Quality Attribute (CQA):** A physical, chemical, biological, or microbiological property or characteristic that should be within an appropriate limit, range, or distribution to ensure the desired product quality. See: [product_quality/cqa_stability.md](cqa_stability.md)

**Critical Process Parameter (CPP):** A process parameter whose variability has an impact on a CQA and therefore should be monitored or controlled to ensure the process produces the desired quality. The key word is "critical" — not every process parameter is a CPP; only those that, when varied within the range seen in manufacturing, produce meaningful changes in CQAs.

**Key Process Parameter (KPP) / Non-Critical Process Parameter (NCPP):** Parameters that are important operationally but have been shown not to critically affect CQAs within their normal operating range. These are still controlled but with less stringent specifications.

**Process Performance Attribute (PPA):** In-process measurements that reflect process behavior but are not CQAs — e.g., cell density, viability, glucose consumption, titer. These inform process health but are not product quality attributes per se.

**Design Space:** The multidimensional combination and interaction of input variables (material attributes and process parameters) that have been demonstrated to provide assurance of quality. Working within the design space is not considered a change; moving outside requires regulatory notification or prior approval.

**Normal Operating Range (NOR) / Proven Acceptable Range (PAR):** NOR is the day-to-day operating setpoint ± control tolerance. PAR is the wider range shown by characterization studies to produce acceptable product. The PAR forms the basis of the regulatory filing.

---

## How CPPs Are Identified: Process Characterization

Process characterization is the systematic set of experiments that establishes the CPP–CQA linkage. The methodology:

1. **Risk assessment (FMEA):** For each unit operation, list all process parameters. Score each parameter for its theoretical potential to affect CQAs (severity × probability × detectability). This prioritizes which parameters to study.

2. **Screening studies (DoE):** Small-scale experimental design that simultaneously varies multiple parameters to identify which have statistically significant effects on CQAs. Fractional factorial designs are common.

3. **Characterization studies (DoE):** Focused studies on the identified significant parameters, using response surface designs (central composite, Box-Behnken) to characterize the shape of the relationship (linear? quadratic? interaction?).

4. **Worst-case confirmation:** Verify that product quality is acceptable at the edge of the PAR (worst-case combination of parameter values).

5. **Scale-down model qualification:** The small-scale model used in characterization studies must be shown to mimic the commercial-scale process. This requires characterization data comparing the two scales (typically using multiple scale-down runs alongside commercial or pilot-scale data).

See: [tech_transfer/process_characterization.md](../../../tech_transfer/process_characterization.md)

---

## Example CPP–CQA Linkages

### Upstream (Cell Culture)

| CPP | CQA affected | Direction of effect |
|---|---|---|
| Bioreactor pH | Glycosylation (sialylation), charge variants (deamidation) | Lower pH → lower sialylation, slower deamidation |
| Temperature | Glycosylation, aggregation, cell growth | Lower temp → less aggregation, altered glycans |
| Dissolved oxygen (DO) | Glycosylation (high mannose), oxidation | Low DO → more high mannose, less Gal |
| Feed composition (glucose) | Glycosylation (Gal), glycation | Higher glucose → more Gal, more glycation |
| Ammonia accumulation | Glycosylation (sialylation) | High ammonia → reduced sialylation |
| Seeding density | Cell growth trajectory, titer, impurity profile | |
| Duration / harvest time | Viability, HCP levels, fragment levels | Longer → lower viability → more HCP, protease |
| Dissolved CO2 | pH, cell physiology | Elevated CO2 → culture acidification |

### Downstream (Purification)

| CPP | CQA affected | Direction of effect |
|---|---|---|
| Protein A elution pH | Aggregate level | More acidic → more aggregation |
| Low-pH viral inactivation (pH, time) | Aggregation, fragments | Too low / too long → damage |
| CEX load pH and conductivity | Charge variant profile | Determines which variants bind and elute |
| CEX elution pH gradient | Main peak %, acidic/basic variants | Elution conditions separate charge variants |
| UF concentration step | Aggregation | Higher concentration → aggregation risk |
| Temperature (all DSP steps) | Aggregation, degradation | |

---

## The Control Strategy

The **control strategy** is the planned set of controls derived from the process understanding, designed to assure product quality. It is documented in the CMC section of the regulatory filing and is the primary deliverable of the process characterization program.

Components of a control strategy:

1. **In-process controls (IPCs):** Measurements taken during the process to confirm the process is running as expected and to catch problems before they affect the final product. Examples: bioreactor pH, DO, daily glucose/lactate, cell density/viability; column chromatography UV trace, fraction pool pH and conductivity.

2. **In-process acceptance criteria (IPAC):** Limits set on in-process measurements. Failing an IPAC triggers investigation and may lead to lot rejection. Example: harvest viability ≥70%.

3. **Process parameter controls:** Setpoints and acceptable ranges for CPPs, enforced by equipment control systems.

4. **Release testing:** Analytical testing of the final drug substance and drug product against a panel of CQA specifications. No lot is released unless all specifications pass.

5. **Specifications:** The numerical limits for each CQA (e.g., ≥95% monomer by SEC, 60–140% relative potency, ≤100 ppm HCP).

The control strategy is the regulatory commitment: the manufacturer is committing that, as long as these controls are in place and the product passes these specifications, the product is safe and effective.

---

## Continued Process Verification (CPV)

After validation, CPV is the ongoing program that monitors process performance and product quality during commercial manufacturing. Under FDA's 2011 Process Validation guidance, Stage 3 (Continued Process Verification) is mandatory.

CPV activities:
- Statistical process control (SPC) charts on CQAs and CPPs
- Trending of CQA results against historical data to detect drift
- Annual Product Reviews (APRs) that summarize CPV data
- Process capability calculation (Cpk) to quantify how well the process is performing relative to specifications

CPV is where the control strategy is tested in the real world: if a parameter trends toward its limit, MSAT must investigate and act before a deviation occurs.

---

## The QbD Spectrum

ICH Q8 describes a spectrum from **minimal approach** to **enhanced (QbD) approach**:

| Approach | Process understanding | Regulatory flexibility |
|---|---|---|
| Minimal | Fixed, approved process | Any change requires prior approval |
| Enhanced (QbD) | Design space established | Working within design space = not a change; prior approval only needed outside design space |

Most modern biopharmaceutical CMC filings fall somewhere between — they establish a design space for the critical parameters while filing the NOR as the day-to-day operating point. This gives flexibility to operate within the PAR without regulatory submission while still having a clear framework for larger changes.

MSAT engineers maintain this design space and must know which parameter changes are within the approved space and which require a change control / regulatory notification.
