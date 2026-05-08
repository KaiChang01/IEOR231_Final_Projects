# ICH Guidelines

**Backlinks:** [_index.md](../_index.md) | [manufacturing/gmp_basics.md](../manufacturing/gmp_basics.md) | [msat/overview.md](../msat/overview.md)  
**Related:** [tech_transfer/process_characterization.md](../tech_transfer/process_characterization.md) | [tech_transfer/comparability_studies.md](../tech_transfer/comparability_studies.md)

---

## What is ICH?

The International Council for Harmonisation of Technical Requirements for Pharmaceuticals for Human Use (ICH) is the body that develops internationally harmonized guidelines for pharmaceutical development, manufacturing, quality, safety, and efficacy.

ICH guidelines are not directly legally binding in any country, but they are incorporated into regulatory guidance by major agencies (FDA, EMA, PMDA in Japan, Health Canada, and others), which means following ICH guidelines is effectively required for global drug registration.

For MSAT engineers, the most important ICH guidelines are in the **Q (Quality)** series. These define how pharmaceutical processes should be developed, characterized, validated, controlled, and managed over their lifecycle.

---

## ICH Q8 — Pharmaceutical Development

**What it covers:** The scientific principles for developing a pharmaceutical product and its manufacturing process.

**Key concepts:**

**Quality by Design (QbD)**  
The philosophy that quality should be built into the product through understanding, not tested in at the end. Under QbD, you begin with a clear definition of what the product must do (the Target Product Profile), work backward to define the quality attributes required (CQAs), then design the process to consistently deliver those attributes.

Contrast with the older approach: develop the process empirically, then validate it "as is" without deeply understanding which parameters actually matter.

**Quality Target Product Profile (QTPP)**  
A summary of the desired quality characteristics of the drug product — route of administration, dosage form, dosage strength, container-closure system, pharmacokinetics, drug product quality criteria. The QTPP is the starting point for QbD development.

**Critical Quality Attribute (CQA)**  
A property of the drug substance or product whose variation has a direct impact on safety, efficacy, or quality. Must be within defined limits. See: [tech_transfer/process_characterization.md](../tech_transfer/process_characterization.md)

**Design Space**  
The multidimensional combination of input variables and process parameters within which the process is demonstrated to produce product meeting all CQA specifications. Operating within the design space is not considered a regulatory change — you have validated flexibility within this space.

**Control Strategy**  
The planned set of controls (on materials, process parameters, equipment, facilities, methods, and finished product testing) that ensures process performance and product quality.

**Why Q8 matters for MSAT:**  
Q8 is the scientific rationale for process characterization. The concepts of CQA, CPP, design space, and control strategy that MSAT uses daily all come from Q8.

---

## ICH Q9 — Quality Risk Management

**What it covers:** A systematic approach to the identification, assessment, control, communication, and review of risks to pharmaceutical product quality.

**Key tools (referenced in Q9):**

| Tool | Use |
|---|---|
| FMEA (Failure Mode and Effects Analysis) | Systematic risk assessment of process steps; identifies where failures can occur and their impact |
| Ishikawa (Fishbone) Diagram | Visual tool for identifying potential causes of a problem or risk |
| Fault Tree Analysis | Top-down analysis linking a specific failure mode to its potential causes |
| HACCP (Hazard Analysis and Critical Control Points) | Systematic hazard identification; common in food and biologics |

**Why Q9 matters for MSAT:**  
Q9 provides the structured risk assessment methodology used in:
- Process characterization (risk assessment determines which parameters to study)
- Change control assessments (risk assessment determines what additional work is needed)
- Deviation investigations (risk assessment guides impact assessment)
- Tech transfer planning (risk assessment identifies the most critical transfer activities)

FMEA is the most commonly used Q9 tool in MSAT work.

---

## ICH Q10 — Pharmaceutical Quality System

**What it covers:** The requirements for a pharmaceutical quality system (PQS) that applies throughout the product lifecycle: development, technology transfer, commercial manufacturing, and product discontinuation.

**Four main elements of Q10:**

**1. Process Performance and Product Quality Monitoring**  
Systematic monitoring of manufacturing data to confirm the process is in a state of control. This is what MSAT implements as Continued Process Verification (CPV) and statistical process control (SPC). The goal is early detection of negative trends before they result in failures.

**2. Corrective Action and Preventive Action (CAPA)**  
The structured process for responding to quality events: corrective action (fix the problem) and preventive action (prevent recurrence). MSAT leads CAPA development for process-related issues.

**3. Change Management**  
Formal management of any change to the process, materials, equipment, or facility. MSAT assesses the technical impact of proposed changes and determines what validation, regulatory, or qualification activities are needed.

**4. Management Review of Process Performance and Product Quality**  
Periodic (typically annual) review at the management level of process performance data, deviation trends, CAPA status, and product quality. MSAT provides the data package (CPV annual product review) that feeds this review.

**Why Q10 matters for MSAT:**  
Q10 is essentially a job description for MSAT. The four elements of Q10 map directly to the four core ongoing activities of an MSAT team in commercial manufacturing.

---

## ICH Q11 — Development and Manufacture of Drug Substances

**What it covers:** Extension of Q8 specifically to drug substance (API) manufacturing — both chemical synthesis (small molecules) and biological/biotechnological methods (biologics).

**Key concepts:**

**Starting Materials**  
The regulatory and scientific rationale for defining where the manufacturing process "starts" for regulatory purposes. This determines which steps are covered by the drug substance filing.

**Process Understanding for Biologics**  
Q11 addresses the particular challenges of biologics: inherent variability of biological systems, the "process is the product" principle, and the approach to characterizing CPPs for biological production steps (cell culture, fermentation).

**Why Q11 matters for MSAT:**  
Particularly relevant for biologics MSAT. Q11 provides the framework for how to approach process characterization and process understanding for complex biological manufacturing processes, where the CQA–CPP relationships are more complex and harder to quantify than in chemical synthesis.

---

## ICH Q12 — Technical and Regulatory Considerations for Pharmaceutical Product Lifecycle Management

**What it covers:** A newer guideline (2020) that creates a more flexible framework for managing post-approval changes — specifically, allowing companies to make certain changes with less regulatory burden if they have demonstrated sufficient process understanding.

**Key concept: PACMP (Post-Approval Change Management Protocol)**  
A protocol filed with regulators in advance that defines a set of changes the company is permitted to make and the conditions under which they can be made. If a change falls within the PACMP conditions, it can be implemented with a reduced regulatory submission burden (notification rather than prior approval).

**Why Q12 matters for MSAT:**  
Q12 enables more agile process improvement. A well-prepared PACMP, grounded in robust process characterization, allows MSAT to implement process improvements faster. Understanding Q12 is increasingly important for MSAT engineers involved in post-approval change management.

---

## Summary Table

| Guideline | Topic | Key MSAT relevance |
|---|---|---|
| Q8 | Pharmaceutical Development | CQA, CPP, QbD, Design Space, Control Strategy |
| Q9 | Quality Risk Management | FMEA, risk-based prioritization for characterization and change control |
| Q10 | Pharmaceutical Quality System | CPV, CAPA, Change Management, Management Review |
| Q11 | Drug Substance Development | Biologics process characterization, starting materials |
| Q12 | Lifecycle Management | Post-approval changes, PACMP |
| Q5E | Comparability (biologics) | Comparability study design and acceptance — see [tech_transfer/comparability_studies.md](../tech_transfer/comparability_studies.md) |
