# Manufacturing Overview

**Backlinks:** [_index.md](../_index.md) | [msat/overview.md](../msat/overview.md)  
**Related:** [manufacturing/unit_operations.md](unit_operations.md) | [manufacturing/gmp_basics.md](gmp_basics.md) | [scheduling/overview.md](../scheduling/overview.md)

---

## The Structure of Pharmaceutical Manufacturing

Pharmaceutical manufacturing transforms raw materials into drug products that can be dispensed to patients. At the highest level, the manufacturing chain looks like:

```
Raw Materials & Excipients
        ↓
Drug Substance Manufacturing
(API synthesis or biologic production)
        ↓
Drug Product Manufacturing
(formulation, filling, finishing)
        ↓
Packaging & Labeling
        ↓
Quality Release
        ↓
Distribution
```

MSAT is primarily concerned with Drug Substance and Drug Product Manufacturing — the process steps where the product's quality attributes are determined.

---

## Drug Substance vs. Drug Product

**Drug Substance (API)**  
The active pharmaceutical ingredient — the molecule with therapeutic activity. Manufactured through chemical synthesis (small molecules) or biological production (biologics). Often manufactured at a separate facility from the drug product.

**Drug Product**  
The finished dosage form — tablet, capsule, injectable solution, inhaler, etc. Combines the API with excipients (inactive ingredients) and places it in a form suitable for administration. May be manufactured at the same facility as the drug substance or a separate one.

For MSAT purposes, the process ownership is usually split: one MSAT team handles drug substance, another handles drug product, with a handoff point at the API.

---

## Types of Drug Products by Dosage Form

| Dosage Form | Description | Key manufacturing complexity |
|---|---|---|
| Oral solid dose (OSD) | Tablets, capsules | Mixing, granulation, compression, coating — highly scalable, lower sterility requirements |
| Sterile injectable | Vials, syringes, bags | Aseptic processing, sterile filtration, lyophilization — highest sterility requirements |
| Topical / semi-solid | Creams, ointments, gels | Emulsion chemistry, mixing homogeneity |
| Inhaled (MDI, DPI) | Metered dose and dry powder inhalers | Particle size control, device-process interface |
| Biologic (large molecule) | mAbs, proteins, vaccines | Upstream cell culture + downstream purification — high complexity across both drug substance and product |

---

## Small Molecule vs. Biologic Manufacturing

These two tracks have fundamentally different manufacturing approaches:

| Dimension | Small Molecule | Biologic |
|---|---|---|
| Production method | Chemical synthesis (defined reactions) | Biological expression (living cells) |
| Batch reproducibility | Very high — chemistry is deterministic | Inherently variable — cells are living systems |
| Process complexity | Relatively contained (synthesis + formulation) | Extensive (cell culture + multiple purification steps) |
| Scale-up challenge | Manageable with engineering principles | Highly complex — bioreactor scale-up is an entire specialty |
| Regulatory filing | NDA (New Drug Application) | BLA (Biologics License Application) |
| Sensitivity to change | Moderate | High — biologics are defined by their process ("the process is the product") |

The phrase "the process is the product" is important for biologics. Unlike a small molecule where you can define the drug completely by its chemical structure, a biologic's quality attributes depend on how it was made — the cell line, the media, the purification process. Two biologics with the same amino acid sequence can have different efficacy if made by different processes.

---

## The Batch Manufacturing Model

Most pharmaceutical manufacturing uses a **batch model**: a defined quantity of material is processed together through all steps, then tested, and released (or rejected) as a unit. Every batch is:

- **Uniquely identified** by a lot number
- **Documented** in an Executed Batch Record (EBR) completed in real time
- **Tested** against specifications before release
- **Traceable** — every material used in the batch is traceable back to its source

This batch model is fundamental to GMP. It enables traceability: if a problem is discovered post-market, the batch number tells you exactly which patients received which product from which materials.

**Continuous manufacturing** is an emerging alternative where material flows continuously rather than in discrete batches. It offers faster cycle times and potentially better process control, but requires real-time release testing and more sophisticated process monitoring. See: [manufacturing/unit_operations.md](unit_operations.md)

---

## Equipment Qualification: IQ / OQ / PQ

Before any equipment is used in GMP manufacturing, it must be qualified. The standard three-stage framework:

**IQ (Installation Qualification)**  
Documents that the equipment was installed correctly — right model, correct utilities connected, documentation received. Confirms it is what it's supposed to be.

**OQ (Operational Qualification)**  
Documents that the equipment operates within its specified parameters — calibration, alarm functions, operating range. Confirms it works correctly.

**PQ (Performance Qualification)**  
Documents that the equipment performs consistently in the actual process context — produces results meeting specifications under actual production conditions. Confirms it's fit for the intended use.

Equipment at the receiving site must be fully qualified before PPQ batches can be manufactured. Qualification status is reviewed during the Phase 1 gap analysis. See: [tech_transfer/phases.md](../tech_transfer/phases.md)

---

## Manufacturing Performance Metrics

MSAT tracks these metrics to characterize process performance:

| Metric | What it measures |
|---|---|
| Batch yield | Mass or volume of product per batch vs. theoretical maximum |
| Right First Time (RFT) | % of batches completed without a deviation |
| Cycle time | Total time from start to release of a batch |
| OEE | Overall Equipment Effectiveness — Availability × Performance × Quality |
| COGS | Cost of goods sold — total manufacturing cost per unit |
| Reject / discard rate | % of batches or units that don't meet release specifications |

These metrics are inputs to production scheduling models and targets for MSAT improvement projects. See: [scheduling/capacity_modeling.md](../scheduling/capacity_modeling.md)
