# Process Characterization

**Backlinks:** [_index.md](../_index.md) | [tech_transfer/overview.md](overview.md)  
**Related:** [tech_transfer/phases.md](phases.md) | [tech_transfer/scale_up.md](scale_up.md) | [regulatory/ich_guidelines.md](../regulatory/ich_guidelines.md)

---

## Definition

Process characterization is the systematic scientific study that establishes the relationship between process inputs (parameters, materials) and process outputs (product quality attributes). It is the scientific foundation for everything MSAT does — tech transfer, process validation, change control, deviation investigation.

The goal of process characterization is to answer: *Which process parameters matter, how much do they matter, and within what range can they safely vary?*

---

## The Parameter Classification Framework

Process characterization classifies every process parameter into one of three categories:

**Critical Process Parameter (CPP)**  
A parameter whose variation *directly impacts a Critical Quality Attribute (CQA)* and therefore must be tightly controlled. CPPs require defined and validated control ranges. Example: pH in a bioreactor cell culture step impacts glycosylation, which is a CQA.

**Key Process Parameter (KPP)**  
A parameter that is important to monitor and control, but whose variation does not directly impact a CQA within the studied range. KPPs still have defined targets and ranges. Example: agitation speed during a mixing step — important for uniformity but not directly linked to a quality attribute within the normal range.

**Non-Key Process Parameter (NKPP)**  
A parameter demonstrated to have no meaningful impact on product quality within the studied range. Still monitored but not formally controlled to a tight range.

This classification drives everything: CPPs get tighter controls, more monitoring, and are the focus of validation; NKPPs get minimal attention.

---

## CQA — The Target

Process characterization starts with identifying Critical Quality Attributes (CQAs). These are product attributes whose variation has a demonstrated or potential impact on patient safety and/or efficacy:

- Potency / activity
- Purity (related substances, degradation products)
- Identity (correct molecular structure)
- Physical form (e.g., crystal polymorph, particle size)
- Sterility / bioburden
- For biologics: glycosylation pattern, aggregation, charge variants

The CQAs are typically defined by Process Development / R&D based on clinical and analytical data, then inherited by MSAT for commercial manufacturing.

---

## Operating Ranges

For each CPP (and often KPPs), process characterization establishes two ranges:

**Normal Operating Range (NOR)**  
The range within which the parameter is routinely controlled during commercial manufacturing. This is the day-to-day target range. Narrow enough to ensure consistent quality.

**Proven Acceptable Range (PAR)**  
The broader range demonstrated (via experiments) to produce acceptable product quality. This is the regulatory boundary — you can operate anywhere in the PAR without a regulatory change, but the NOR is where you typically operate.

```
|------PAR------|
    |--NOR--|
         ↑
      target
```

If a parameter drifts outside the NOR but stays within the PAR during manufacturing, it's an atypical event that triggers an investigation, but product may still be releasable. Outside the PAR, the batch is at risk.

---

## Study Design

Process characterization studies use **Design of Experiments (DOE)** — structured experimental designs that efficiently explore the relationship between multiple parameters simultaneously.

**Why DOE instead of one-factor-at-a-time (OFAT)?**  
OFAT varies one parameter while holding all others constant. This doesn't reveal interactions — where two parameters together affect quality in a way that neither does alone. DOE designs (factorial, central composite, Box-Behnken) reveal both main effects and interactions with far fewer experiments.

**Typical workflow:**

1. **Risk assessment (FMEA)** — List all process parameters. Use Failure Mode and Effects Analysis or Ishikawa diagrams to score each parameter on risk: probability of variation × severity of impact on CQAs. High-risk parameters are prioritized for characterization.

2. **Screening study** — Run a fractional factorial DOE to screen a large number of parameters and identify which ones have significant effects on CQAs. Low-screening parameters are confirmed as NKPPs.

3. **Characterization study** — Run a more detailed DOE on the significant parameters to define the CPP–CQA relationship quantitatively. Establishes the shape of the response surface and the boundaries of the PAR.

4. **Confirmatory runs** — Verify that operation at the NOR consistently meets all CQA specifications.

---

## Outputs of Process Characterization

A complete process characterization study produces:

- **CPP/KPP/NKPP classification table** — Parameter-by-parameter classification with scientific justification
- **NOR and PAR for each CPP** — The control ranges, with experimental data supporting them
- **Process characterization report** — Full documentation of the study design, methods, results, and conclusions. This becomes part of the TTP.
- **Regulatory filing inputs** — Data supporting the process description and control strategy in the CMC section

---

## Process Characterization vs. Process Development

These two terms are sometimes confused:

- **Process Development** (done by R&D) — Figure out *how* to make the product at all. What steps, what materials, approximately what conditions.
- **Process Characterization** (done by MSAT or later-stage R&D) — Rigorously quantify *why* the process works, define the boundaries of acceptable operation, and build the scientific justification for validation and regulatory filing.

In practice, process characterization studies begin during late-stage development (Phase 2/3 for biologics) and are completed before PPQ. At the time of tech transfer, the sending site's characterization data is in the TTP, and the receiving site may need to confirm or supplement it at their scale.
