# Unit Operations

**Backlinks:** [_index.md](../_index.md) | [manufacturing/overview.md](overview.md)  
**Related:** [tech_transfer/scale_up.md](../tech_transfer/scale_up.md) | [tech_transfer/process_characterization.md](../tech_transfer/process_characterization.md)

---

## Definition

A unit operation is a discrete, defined processing step in a manufacturing process. Complex pharmaceutical manufacturing processes are decomposed into a sequence of unit operations, each of which transforms the material in a specific, controlled way.

Understanding unit operations is essential for MSAT because:
- Process characterization is done at the unit operation level (each step has its own CPPs and CQAs)
- Scheduling models represent processes as sequences of unit operations with defined cycle times
- Troubleshooting is done by isolating which unit operation caused a problem
- Scale-up challenges are specific to each type of unit operation

---

## Small Molecule / Oral Solid Dose Unit Operations

This is the most common manufacturing platform for traditional drugs. The process converts API powder + excipients into tablets or capsules.

**Dispensing / Weighing**  
Raw materials are weighed and dispensed to specification. Critical for dose accuracy. First GMP step.

**Blending / Mixing**  
API and excipients are combined to achieve a homogeneous blend. Blend uniformity is a CQA — poor blending means variable dose content. CPPs: blend time, mixing speed, load level, particle size distribution of inputs.

**Granulation** (if used)  
Aggregates fine particles into granules to improve flow and compressibility. Two types:
- *Wet granulation*: add liquid binder to powder, then dry. Better uniformity but more complex.
- *Dry granulation (roller compaction)*: compress powder into ribbons then mill. Avoids moisture-sensitive APIs.

**Milling / Sizing**  
Reduces particle size or sizes granules to a target distribution. Particle size affects dissolution (and therefore bioavailability for poorly soluble drugs).

**Compression / Tableting**  
Granules or blend are compressed into tablets on a rotary tablet press. CPPs: compression force, press speed, punch tooling. CQAs: tablet weight, hardness, friability, thickness, dissolution.

**Film Coating** (if used)  
Applies a thin polymer film to tablets: for appearance, moisture protection, taste masking, or controlled release. CPPs: inlet air temperature, spray rate, pan speed, atomization air pressure.

**Capsule Filling**  
Alternative to compression: fills powder or granules into hard gelatin or HPMC capsule shells.

---

## Sterile Injectable Unit Operations

Sterile products (vials, syringes, IV bags) require more complex processing due to sterility requirements. Any contamination is unacceptable.

**Compounding / Formulation**  
API is dissolved or suspended in a sterile vehicle (water for injection, buffer). pH, tonicity, stabilizers are adjusted. Done in a closed system.

**Sterile Filtration**  
Solution is passed through a 0.22 µm sterilizing-grade membrane filter. This is the primary bioburden reduction step for most sterile solutions. Filter integrity is tested before and after. CPPs: filter type, pressure, flow rate, flush volume.

**Aseptic Filling**  
Sterile solution is filled into sterile containers (vials, syringes) in a cleanroom (ISO 5 or better) under HVAC-controlled conditions. This is the highest-risk GMP step — any breach of aseptic technique can contaminate product.

**Lyophilization (Freeze-Drying)**  
Used for products that are unstable in liquid form. The solution is frozen in vials, then water is removed by sublimation under vacuum. Produces a dry cake that is reconstituted before administration. CPPs: shelf temperature ramp rates, chamber pressure, condenser temperature. Equipment-specific — lyophilizer cycles must be developed for each piece of equipment.

**Visual Inspection**  
Every unit is inspected for particulate matter, container defects, and fill level — manually or semi-automatically.

---

## Biologics Unit Operations

Biologics manufacturing has two main sections: **upstream** (producing the protein) and **downstream** (purifying it).

### Upstream Processing

**Cell Banking**  
Working and master cell banks store the production cell line. Maintained under strictly controlled conditions; any change requires extensive comparability studies.

**Seed Train / Inoculum Preparation**  
Cells are grown from a vial of working cell bank through progressively larger bioreactors until sufficient cell density is achieved for production scale.

**Production Bioreactor**  
The main production step. Cells grow in a bioreactor (typically 1,000–25,000L for commercial scale) under controlled temperature, pH, dissolved oxygen, and nutrient feed. Duration: 10–21 days typically. CPPs: temperature, pH, pO2, agitation, feed schedule. CQAs: cell density, viability, product titer, glycosylation profile.

**Harvest / Clarification**  
The bioreactor culture (cells + product-containing fluid) is processed to remove cells and cell debris. Methods: centrifugation, depth filtration, microfiltration. This is the transition between upstream and downstream.

### Downstream Processing

**Capture Chromatography**  
First purification step — selectively binds the protein of interest. For monoclonal antibodies, Protein A affinity chromatography is standard. Removes >99% of non-product impurities in one step.

**Virus Inactivation**  
Low pH incubation (for Protein A eluate) or solvent/detergent treatment inactivates potential adventitious viruses. Regulatory requirement for all biologic products.

**Intermediate Purification Chromatography**  
Additional chromatography steps (ion exchange, hydrophobic interaction) to remove residual impurities: host cell proteins (HCP), host cell DNA, aggregates, charge variants.

**Virus Filtration**  
Nanofiltration (20nm filter) physically removes virus-sized particles. Second viral safety step.

**Ultrafiltration / Diafiltration (UF/DF)**  
Concentrates the protein solution and exchanges the buffer to the final formulation buffer. Sets the concentration and excipient composition for drug substance.

**Final Filtration and Drug Substance Filling**  
Sterile filtration of the purified drug substance, then filled into storage bags or vials. Stored frozen (-80°C for most mAbs).

---

## Process Flow Diagram Convention

Unit operations are typically depicted in a **Process Flow Diagram (PFD)** with standardized symbols. For scheduling purposes, each unit operation is a node with:

- A **cycle time** (how long it takes)
- **Equipment requirements** (which specific equipment is needed)
- **Predecessor / successor constraints** (what must happen before it, what can happen in parallel)

These PFD attributes are the inputs to scheduling models. See: [scheduling/capacity_modeling.md](../scheduling/capacity_modeling.md)
