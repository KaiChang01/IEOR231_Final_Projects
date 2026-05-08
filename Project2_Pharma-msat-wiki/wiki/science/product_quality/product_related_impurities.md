# Product-Related Impurities

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [product_quality/cqa_stability.md](cqa_stability.md) | [product_quality/analytical_assays.md](analytical_assays.md) | [protein_structure/structure_and_function.md](../protein_structure/structure_and_function.md)

---

## Definition and Regulatory Framework

ICH Q6B distinguishes between:

- **Product-related impurities** — molecular variants of the desired product that arise during manufacture or storage. They share the core amino acid sequence but differ in some structural attribute (size, charge, modification state).
- **Process-related impurities** — substances derived from the manufacturing process but not from the protein itself: host cell proteins (HCPs), host cell DNA, residual protein A, cell culture media components, adventitious agents.

This article focuses on **product-related impurities**, which are the structurally heterogeneous variants of the drug substance itself.

The regulatory standard (ICH Q6B) requires that all product-related impurities be identified, characterized, and their safety and potency implications assessed. Those with the potential to affect safety or efficacy are candidates for CQA designation.

---

## Why These Are "Impurities" Despite Being Made of the Drug

The term "impurity" is regulatory, not chemical. These variants are made of the same protein as the intended product, but because they differ structurally, they may have different:
- Binding affinity or selectivity
- Effector function
- Half-life
- Immunogenicity risk
- Stability profile

They are therefore distinct entities that require their own characterization, even though they are not extraneous chemical contaminants.

---

## Major Categories of Product-Related Impurities

### 1. Aggregates

**What they are:** Non-covalent or covalent oligomers of the drug substance — dimers, trimers, and higher-order species — and submicron or micron-scale particles.

**Why they matter:** Aggregates are associated with increased immunogenicity risk. They can activate immune cells through multivalent crosslinking of B-cell receptors, activate complement, or serve as danger signals. They also represent loss of monomer potency.

**Formation mechanisms:**
- Conformational instability leading to exposure of hydrophobic patches → non-covalent aggregation
- Disulfide bond scrambling → covalent aggregation
- Physical stresses: shear (pumping, mixing), freeze-thaw, concentration, heat

**Control points:**
- Upstream: maintain cell viability, avoid excessive shear
- Downstream: gentle unit operations, controlled pH and temperature
- Formulation: excipients (surfactants like polysorbate 20/80, sugars like sucrose/trehalose) stabilize against aggregation

**Analytical methods:** SEC-HPLC (quantitative for soluble aggregates), DLS (size distribution), MFI (micro-flow imaging, for subvisible particles ≥2 µm), light obscuration (USP <788> for particles ≥10 and ≥25 µm).

### 2. Fragments

**What they are:** Molecules that have been partially degraded — Fab/c fragments from hinge region hydrolysis, half-antibodies, Fd fragments.

**Why they matter:** Loss of bivalency (affects potency for some mechanisms), loss of Fc region (affects FcRn recycling → shorter half-life, ADCC loss, complement loss).

**Formation mechanisms:**
- Proteolytic cleavage: proteases secreted by cells or released from lysed cells in late-culture or harvest
- Chemical hydrolysis: acid-catalyzed at low pH (Protein A elution, low-pH viral inactivation)
- Hinge region is the most susceptible site (flexible, exposed, accessible)

**Control points:**
- Cell culture viability monitoring — cell lysis releases intracellular proteases
- Harvest timing — avoid excessive post-peak culture
- Careful management of low-pH steps (time, temperature)
- Downstream chromatography can separate fragments from intact IgG

**Analytical methods:** Reduced and non-reduced CE-SDS or SDS-PAGE; SEC-HPLC can detect large fragments.

### 3. Charge Variants (as impurities)

Deamidated, oxidized, glycated, and other chemically modified species are discussed in detail in [protein_structure/protein_charge.md](../protein_structure/protein_charge.md). Here, the classification perspective:

- Charge variants are product-related impurities when they arise from chemical modification
- Their criticality depends on location (CDR vs. Fc) and functional impact
- Quantified as % acidic and % basic variants by icIEF

### 4. Misassembled Forms

**Half-antibodies:** One heavy chain + one light chain. Relevant especially for IgG4 (Fab arm exchange) and bispecific antibodies.

**Bispecific mispairs:** In bispecific antibody production, mispairing of the two different heavy chains or heavy-light chain mispairing creates inactive or off-target binding species. A major product-related impurity for bispecifics. Controlled by protein engineering (knob-into-hole, CrossMAb), cell co-expression strategies, and chromatographic separation.

**Light chain dimers / heavy chain dimers:** Rare but possible under stressed conditions.

### 5. Glycosylation Variants

From the purification perspective, glycoforms are not typically removed (all glycoforms co-elute from Protein A), so the glycan distribution in the drug substance reflects the bioreactor output. Individual glycoforms that are present at levels that raise safety concerns (e.g., high mannose if linked to enhanced clearance in a PK-sensitive application) may be designated as product-related impurities with specifications.

NGNA (non-human sialic acid from CHO cells) and alpha-Gal are potential immunogenic glycan epitopes that are monitored. See: [protein_structure/glycosylation.md](../protein_structure/glycosylation.md)

---

## Process-Related Impurities (Brief)

For completeness, the main process-related impurities (not covered in depth here):

| Impurity | Source | Key concerns | Analytical method |
|---|---|---|---|
| Host Cell Proteins (HCPs) | CHO cell lysate | Immunogenicity, potency interference, stability (proteases) | ELISA (HCP ELISA), proteomics |
| Host Cell DNA | CHO genomic DNA | Theoretical oncogenicity, infectivity concern | qPCR |
| Residual Protein A | Protein A resin leaches | Immunogenicity | ELISA |
| Cell culture media components | Serum, insulin, etc. | Safety, animal-derived material risk | Vendor CoAs, qualified raw materials |
| Adventitious agents | Viral contamination | Patient safety | Viral clearance studies, in-process testing |
| Endotoxin | Gram-negative bacteria | Pyrogenicity | LAL assay |
| Bioburden | Microbial contamination | Patient infection | Membrane filtration, rapid methods |

---

## Setting Specifications for Product-Related Impurities

The specification for each impurity is derived from:

1. **Clinical batch data** — what levels were present in lots used in pivotal trials that demonstrated safety and efficacy
2. **Process capability** — what the process can consistently achieve
3. **Toxicology / risk assessment** — what level is biologically acceptable
4. **Analytical method capability** — the limit of quantification drives the lower bound of what can be specified

ICH Q6B guidance and EMA/FDA expectations require that impurities present above a reporting threshold be qualified (safety assessment) and that those linked to safety/efficacy concerns be specified as CQAs. See: [product_quality/cqa_stability.md](cqa_stability.md)
