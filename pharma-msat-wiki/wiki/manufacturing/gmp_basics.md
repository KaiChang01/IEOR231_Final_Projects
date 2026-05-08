# GMP Basics

**Backlinks:** [_index.md](../_index.md) | [msat/overview.md](../msat/overview.md) | [manufacturing/overview.md](overview.md)  
**Related:** [regulatory/ich_guidelines.md](../regulatory/ich_guidelines.md)

---

## What is GMP?

Good Manufacturing Practice (GMP) — also called Current Good Manufacturing Practice (cGMP) — is the regulatory system of practices and standards that ensures pharmaceutical products are consistently produced and controlled to quality standards appropriate for their intended use.

GMP exists because pharmaceutical manufacturing failures can directly harm patients. Unlike consumer goods where a defect is an inconvenience, a contaminated or sub-potent drug can kill someone. GMP is the set of requirements that prevents this.

In the United States, GMP is enforced by the FDA under:
- **21 CFR Part 211** — Current Good Manufacturing Practice for Finished Pharmaceuticals
- **21 CFR Part 210** — cGMP for Manufacturing, Processing, Packing, or Holding of Drugs

Globally, the EU, WHO, and ICH (Q7 for APIs, Q10 for pharmaceutical quality systems) have parallel frameworks. See: [regulatory/ich_guidelines.md](../regulatory/ich_guidelines.md)

---

## Why GMP Shapes Everything MSAT Does

GMP is not a checklist you complete once — it is the operating environment in which MSAT works. Every document MSAT writes, every experiment it runs in the manufacturing environment, every change it makes to the process, must be done *within* the GMP framework.

Concretely, this means:

- Experiments must be documented with controlled instruments and traceable materials
- Any deviation from the approved process must be formally documented and investigated
- Changes to the process must go through change control and may require regulatory notification
- All work must be reviewed and approved by Quality Assurance

If you're coming from an R&D background, GMP can feel constraining — you can't just try something and see what happens. Everything that happens on a manufacturing floor must be planned, approved, documented, and reviewed. This friction exists for good reason: it prevents the casual "it'll be fine" attitude that causes real harm at manufacturing scale.

---

## Core GMP Principles

**Document what you do; do what you document**  
The most fundamental GMP principle. If it wasn't documented, it didn't happen — from a GMP standpoint. Every step, every measurement, every observation must be recorded in the batch record or relevant GMP document, at the time it happens.

**Data integrity (ALCOA+)**  
All GMP records must be: Attributable (who did it?), Legible (can it be read?), Contemporaneous (recorded at the time?), Original (not a copy or reconstruction?), Accurate (correct?). The + adds: Complete, Consistent, Enduring, Available.

Data integrity failures — backdating records, correcting entries without proper documentation, falsifying data — are the most serious GMP violations and can result in warning letters, consent decrees, or facility shutdowns.

**Process control over testing**  
GMP philosophy (and ICH Q10) holds that quality cannot be "tested into" a product — you can't catch every problem by testing finished product. Quality must be *built in* through process control. Testing is verification, not assurance.

**Validated processes**  
All critical manufacturing processes must be validated before they are used to produce commercial product. See: [tech_transfer/phases.md](../tech_transfer/phases.md)

---

## Key GMP Systems

**Document Control**  
All GMP-relevant documents — SOPs, batch records, specifications, protocols, reports — are controlled documents. They have version numbers, approval signatures, and are stored in a Document Management System (DMS). An outdated SOP cannot be used.

**Batch Records**  
The Master Batch Record (MBR) is the approved manufacturing instruction. The Executed Batch Record (EBR) is completed step-by-step during manufacturing. EBRs are legal records and must be retained for the product's shelf life plus some defined period (often years).

**Deviations**  
Any departure from an approved process or specification must be documented as a deviation. Deviations are investigated to determine root cause, impact on product quality, and CAPA. Batch disposition (release or rejection) depends on the deviation investigation outcome. MSAT writes many of these.

**Change Control**  
Any proposed change to a validated process, equipment, material, method, or facility must go through change control. The MSAT role: write the technical assessment evaluating the potential impact on product quality and determine what additional work (studies, validation, regulatory filing) is needed.

**CAPA (Corrective Action / Preventive Action)**  
The structured response to a quality problem. Corrective action fixes the immediate problem; preventive action prevents recurrence. CAPA effectiveness is verified after implementation.

**Calibration and Preventive Maintenance**  
All instruments and equipment used in manufacturing or testing must be calibrated on schedule. Equipment must have preventive maintenance performed per vendor specifications. Out-of-calibration instruments can invalidate data retroactively.

---

## FDA Inspections

FDA inspects pharmaceutical manufacturing facilities on a regular schedule (typically every 2 years for commercial sites). Inspectors review batch records, deviation investigations, change controls, validation reports, laboratory records, and procedures.

Common FDA inspection findings that MSAT is accountable for:
- Inadequate investigation of manufacturing deviations (failure to determine root cause)
- Changes made without change control
- Validation data that doesn't support the process claims
- Data integrity issues in batch records or laboratory systems

MSAT engineers should write every technical document as if an FDA inspector will read it — because they might.

---

## GMP in the Context of MSAT Work

| MSAT Activity | GMP requirement |
|---|---|
| Running process characterization studies | Experiments done with controlled instruments and documented per study protocol |
| Writing batch records | Approved via formal review/approval; version-controlled |
| Engineering runs (pre-validation) | May be done with partial GMP compliance depending on site procedures |
| PPQ batches | Full GMP — every step documented in real time in the EBR |
| Deviation investigation | Required within defined timeframe; documented in deviation management system |
| Change control | Technical assessment authored and approved before any change is implemented |
| CPV data review | Periodic review of manufacturing data using validated statistical tools |
