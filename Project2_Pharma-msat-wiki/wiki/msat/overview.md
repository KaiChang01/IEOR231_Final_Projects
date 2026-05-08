# MSAT Overview

**Backlinks:** [_index.md](../_index.md) | [msat/roles_responsibilities.md](roles_responsibilities.md)  
**Related:** [tech_transfer/overview.md](../tech_transfer/overview.md) | [manufacturing/overview.md](../manufacturing/overview.md) | [regulatory/ich_guidelines.md](../regulatory/ich_guidelines.md)

---

## What is MSAT?

Manufacturing Science and Technology (MSAT) is the department in a pharmaceutical company that owns the manufacturing process from a scientific standpoint. It sits at the intersection of R&D and Manufacturing Operations — it is responsible for understanding the process deeply enough to transfer it, troubleshoot it, validate it, and continuously improve it.

A useful way to think about it: if Manufacturing Operations runs the process day-to-day, MSAT understands *why* the process works, *what* can go wrong and *why*, and *how* to change it safely.

MSAT is sometimes called by other names depending on the company: Process Science, Technical Operations (Tech Ops), Manufacturing Technical Support, or Process Development (in smaller organizations where it's not separated from R&D).

---

## Where MSAT Sits in the Org

```
R&D / Process Development
        |
        |  [tech transfer]
        ↓
     MSAT
        |
        |  [validated process, SOPs, batch records]
        ↓
Manufacturing Operations
        |
        |  [deviation reports, process questions]
        ↓
     MSAT  ← (also provides ongoing support back to Mfg Ops)
```

MSAT is the technical bridge. R&D develops the process and hands it off via tech transfer. MSAT receives it, validates it, and hands it to Manufacturing in a state that is production-ready. Once the product is in commercial manufacturing, MSAT remains the technical owner — it investigates deviations, implements process improvements, and supports regulatory filings.

---

## Why MSAT Exists

The problem MSAT solves is that drug development and drug manufacturing are fundamentally different activities operating under different constraints:

- R&D runs processes at small scale with highly skilled scientists, tolerating variability in service of learning
- Manufacturing runs processes at commercial scale with operators following SOPs, under strict GMP, with zero tolerance for unplanned variability

Without a bridge function, processes developed in R&D would routinely fail to scale up or would produce variable quality at commercial scale. MSAT's job is to de-risk that transition and then sustain the process in a state of control.

The regulatory framework underpinning MSAT's existence is ICH Q10 (Pharmaceutical Quality System), which defines the requirement for a "robust pharmaceutical quality system" that includes process understanding and continuous improvement. See: [regulatory/ich_guidelines.md](../regulatory/ich_guidelines.md)

---

## MSAT's Core Activities

The scope of MSAT work clusters around five activity types:

**1. Tech Transfer**  
Moving a manufacturing process from one site or scale to another — from R&D to clinical manufacturing, from clinical to commercial, or from one commercial site to another. This is often considered MSAT's primary function. See: [tech_transfer/overview.md](../tech_transfer/overview.md)

**2. Process Validation**  
Building and executing the evidence package that proves the manufacturing process is capable and reproducible at commercial scale. MSAT owns Stage 2 of the FDA's three-stage validation lifecycle (PPQ) and contributes to Stages 1 and 3. See: [tech_transfer/phases.md](../tech_transfer/phases.md)

**3. Process Characterization**  
Systematic studies that identify Critical Process Parameters (CPPs) and define their acceptable operating ranges — the scientific foundation for everything else MSAT does. See: [tech_transfer/process_characterization.md](../tech_transfer/process_characterization.md)

**4. Technical Support to Manufacturing**  
Real-time support when manufacturing runs into problems: investigating deviations, writing technical reports, assessing impact on product quality, and proposing corrective actions.

**5. Continuous Process Improvement**  
Ongoing analysis of manufacturing data to identify trends, optimize yields, reduce cycle times, and strengthen process robustness. Formalized as Continued Process Verification (CPV) under the FDA's 2011 Process Validation guidance.

---

## MSAT's Key Interfaces

| Function | Nature of the relationship |
|---|---|
| R&D / Process Development | Receives process knowledge and TTP from R&D; participates in late-stage development to prepare for transfer |
| Manufacturing Operations | Provides technical support, SOPs, validated procedures; receives deviation investigations |
| Quality Assurance (QA) | Collaborates on validation protocols, deviations, change control; QA approves what MSAT authors |
| Regulatory Affairs | Provides process data and technical justification for CMC sections of regulatory filings |
| Engineering | Coordinates on equipment qualification (IQ/OQ/PQ), facility design, and scale-up equipment selection |
| Supply Chain | Interacts on production scheduling, campaign planning, capacity constraints |

---

## MSAT in the Context of ICH Q10

ICH Q10 describes the pharmaceutical quality system and identifies four elements. MSAT is primarily responsible for:

- **Process Performance and Product Quality Monitoring** — CPV, trending, control charts
- **Corrective Action / Preventive Action (CAPA)** — for manufacturing deviations and OOS events
- **Change Management** — technical assessment and validation of manufacturing changes
- **Management Review inputs** — process capability data, deviation trends

See: [regulatory/ich_guidelines.md](../regulatory/ich_guidelines.md)
