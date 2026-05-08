# Harvest

**Backlinks:** [upstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [upstream/seed_train_bioreactor.md](seed_train_bioreactor.md) | [downstream/overview.md](../downstream/overview.md) | [product_quality/product_related_impurities.md](../../product_quality/product_related_impurities.md)

---

## What Harvest Accomplishes

Harvest is the transition from upstream to downstream processing. Its goal is to separate the secreted antibody (in the conditioned medium) from the cells, cell debris, and particulate matter that would interfere with downstream chromatography.

Harvest is typically not a purification step — it does not significantly reduce soluble impurities like HCPs or DNA, though it does remove cellular particulates. The key deliverable of harvest is a clarified harvest (also called clarified bulk culture fluid, CBCF) that:
- Has low turbidity (no visible particles)
- Is free of intact cells and large debris
- Has low enough particulate load to pass through downstream depth filtration

---

## Harvest Step 1: Centrifugation (Disk-Stack Centrifuge)

The primary cell removal step. The disk-stack centrifuge uses multiple stacked conical discs to increase the effective settling area, applying high centrifugal force (3,000–10,000 × g effective) to sediment cells and debris continuously.

**How it works:**
- Culture broth flows into the centrifuge bowl through the center
- The spinning bowl applies centrifugal force
- Cells (heavier) sediment to the periphery and are periodically ejected as solids
- Clarified supernatant exits through the top

**Key parameters:**
- Feed flow rate (determines residence time; lower flow rate = more efficient centrifugation)
- Discharge interval (how often solids are ejected)
- Centrifuge bowl temperature (to minimize product degradation)
- Dissolved oxygen in feed (some facilities use N2 sparging to reduce oxidation during harvest)

**Limitations:**
- Does not remove all sub-micron debris
- Shear during centrifuge discharge can lyse remaining viable cells, releasing intracellular contents (HCPs, proteases, DNA)
- The clarified centrate still contains significant levels of HCP, DNA, and fine particles

---

## Harvest Step 2: Depth Filtration

The centrate is passed through one or more depth filters (also called depth filtration or DF) to remove residual fine particles, cell debris, and in some cases to adsorb soluble impurities.

**What depth filters are:** Thick pads of filter media (typically cellulose fiber with a diatomaceous earth filler and a positively charged resin binder). The porous matrix traps particles by:
- Mechanical interception (particles larger than pore size)
- Adsorptive capture (electrostatic interaction of negatively charged particles/DNA with positively charged resin binder)

**Configuration:** Typically two stages — a coarser pre-filter followed by a finer polishing filter (e.g., Millipore DOHC/XOHC, Pall SUPRAcap). The coarse filter extends the life of the fine filter.

**Key parameters:**
- Differential pressure across the filter (increasing ΔP signals filter loading → end of filter capacity)
- Flux rate (L/m² filter area/hour)
- Turbidity of the filtrate (should decrease through harvest)
- Bioburden control (depth filtration is not sterile)

**What depth filtration reduces:**
- Turbidity: dramatically (harvest to clarified)
- Sub-micron particles: significantly
- DNA: partially (positively charged resin adsorbs DNA)
- HCP: partially (some adsorption)
- Lipids/cell membrane fragments: partially

**What it does not remove:**
- Soluble HCPs (requires chromatography)
- Viruses
- Soluble DNA

---

## Harvest Step 3: Sterile Filtration (Bioburden Reduction)

The clarified harvest is typically passed through a 0.2 µm (or 0.22 µm) membrane filter before proceeding to downstream chromatography. This is a bioburden reduction step, not a sterilizing filtration — the downstream process is not aseptic until the final sterile filtration of the drug substance, but controlling bioburden at harvest prevents microbial growth during intermediate holds.

---

## Alternative and Integrated Harvest Technologies

### Tangential Flow Filtration (TFF) for Harvest

Some processes use TFF (cross-flow filtration) instead of centrifugation. The culture broth flows across a hollow fiber or flat-sheet membrane; cells are retained and recycled while permeate (containing the product) passes through.

Used for: high-density perfusion cultures, processes with fragile cells, or when centrifugation capacity is insufficient. Can be operated continuously.

### Flocculation

Adding a cationic polymer (e.g., polyethylenimine, PEI) to the harvest causes cells, debris, and HCPs to aggregate into larger flocs that can be removed by filtration or centrifugation more efficiently. Can also reduce HCP and DNA levels more than centrifugation alone.

### Continuous Harvest (for Perfusion)

In perfusion bioreactor systems, an alternating tangential flow filtration (ATF) system continuously removes product-containing permeate while retaining cells. Harvest in perfusion is not a discrete step but a continuous draw from the ATF filtrate.

---

## MSAT Concerns at Harvest

### Cell Viability at Harvest

Low viability at harvest means more cell lysis → more HCP, more protease release → higher fragment levels, more HCP carryforward. The harvest viability IPC limit (typically ≥70%) is set with this in mind.

### Protease Control

Proteases released from lysed cells can fragment the antibody at the hinge region. MSAT engineers must:
- Monitor fragmentation as a function of harvest timing (delay harvest until cell viability drops → more fragmentation)
- Assess impact of temperature during harvest hold (lower temperature → slower protease activity)
- Understand whether protease inhibitors are used (not common in manufacturing due to regulatory concerns but used in development)

### HCP and DNA Carryforward

The HCP and DNA levels in the clarified harvest feed directly into the downstream purification challenge. Higher levels in harvest require more clearance downstream. If harvest HCP levels are unusually high (due to cell lysis, unusual HCP secretion from the clone, or poor depth filter performance), it affects the risk profile for subsequent steps.

### Shear and Aggregation

The centrifuge discharge, peristaltic pumps, and depth filtration create hydrodynamic shear that can induce aggregation. This is especially problematic for aggregation-prone molecules. Minimizing shear (lower pump speeds, gentle handling) and monitoring aggregate levels in the clarified harvest are good practices.

---

## Harvest: Key In-Process Measurements

| Measurement | Purpose | Typical IPC limit |
|---|---|---|
| Viable cell density at harvest | Confirm culture endpoint | Within expected range |
| Cell viability at harvest | Safety margin for HCP/protease | ≥70% (typical) |
| Turbidity (NTU) of centrate | Confirm centrifuge performance | Product-specific |
| Turbidity of depth filtration permeate | Confirm filter performance | Typically <5–10 NTU |
| Filter differential pressure | Monitor filter loading | Process-specific limit |
| Bioburden of clarified harvest | Confirm no contamination | Typically ≤10 CFU/100 mL |
| Titer (protein A HPLC or ELISA) | Mass balance input to DSP | For yield tracking |
