# Protein Structure Basics

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [protein_structure/structure_and_function.md](structure_and_function.md) | [protein_structure/glycosylation.md](glycosylation.md) | [protein_structure/protein_charge.md](protein_charge.md)

---

## Why Protein Structure Matters for MSAT

The therapeutic protein is the product. Every manufacturing decision — bioreactor pH setpoint, purification column resin, formulation buffer — ultimately exists to protect or optimize the structural integrity of this molecule. An MSAT engineer who cannot read a protein structure report or interpret analytical data on aggregation is operating blind.

This article covers the structural hierarchy of proteins and the properties of monoclonal antibodies specifically, since mAbs are the dominant format in modern biologics manufacturing.

---

## The Four Levels of Protein Structure

### Primary Structure

The sequence of amino acids linked by peptide bonds. This is encoded by the gene inserted into the expression system and does not change during manufacturing (barring rare mis-incorporation events). For a mAb, the heavy and light chain sequences define the identity of the molecule.

Primary structure is confirmed analytically by peptide mapping (LC-MS/MS) and is the reference for all other structural levels.

### Secondary Structure

Local, repeating patterns of folding stabilized by hydrogen bonds between backbone atoms:

- **Alpha helix** — a right-handed coil, ~3.6 residues per turn
- **Beta sheet** — extended strands connected by H-bonds, either parallel or antiparallel
- **Loops and turns** — irregular segments connecting helices and sheets, often functionally important

Antibodies are predominantly beta-sheet proteins (immunoglobulin fold). Secondary structure is assessed by circular dichroism (CD) spectroscopy and Fourier-transform infrared (FTIR) spectroscopy.

### Tertiary Structure

The complete three-dimensional fold of a single polypeptide chain. This is determined by the full set of interactions: hydrogen bonds, hydrophobic packing, electrostatic interactions, and disulfide bonds. For a mAb, each chain adopts its tertiary structure independently before assembly.

**Disulfide bonds** are covalent linkages between cysteine residues (via oxidation of thiol groups). They are critical to the stability and correct folding of antibodies. A mAb typically has:

- 4 intrachain disulfides per heavy chain
- 2 intrachain disulfides per light chain
- 1 heavy-light interchain disulfide per chain pair
- 2 heavy-heavy interchain disulfides (hinge region)

Incorrect disulfide bonding (mispaired cysteines) is a product-related impurity that can affect potency and immunogenicity.

### Quaternary Structure

The assembly of multiple polypeptide chains into a functional complex. A mAb is a tetramer: two identical heavy chains and two identical light chains, held together by disulfide bonds and non-covalent interactions. This gives it its characteristic Y-shape.

The quaternary structure creates two functional regions:
- **Fab region** (antigen-binding fragment) — the two "arms" of the Y, responsible for target binding
- **Fc region** (crystallizable fragment) — the "stem" of the Y, responsible for effector functions (complement activation, ADCC, neonatal Fc receptor binding that governs half-life)

---

## Antibody Architecture in Detail

```
        VH   VL
         \   /
    CH1 - CL      ← Fab (x2)
          |
    Hinge region  ← flexible, contains interchain disulfides
          |
    CH2 - CH2
    |         |
    CH3 - CH3       ← Fc
```

**Variable domains (VH, VL):** contain the Complementarity Determining Regions (CDRs) — the hypervariable loops that directly contact antigen. The CDRs are the binding site. Six CDRs total (3 from VH, 3 from VL) form the antigen-binding paratope.

**Constant domains:** determine antibody class (IgG, IgM, IgA, etc.) and Fc-mediated effector functions. Most therapeutic mAbs are IgG1 or IgG4.

---

## IgG Subclasses

| Subclass | Key features | Common therapeutic use |
|---|---|---|
| IgG1 | Strong Fc effector functions (ADCC, CDC) | Oncology mAbs (e.g., rituximab, trastuzumab) |
| IgG2 | Reduced effector functions, different hinge disulfide pattern | Blocking antibodies |
| IgG4 | Minimal effector function, Fab arm exchange in vivo | Checkpoint inhibitors, blocking antibodies |

IgG4 can exchange half-molecules (one Fab + one Fc arm) with endogenous IgG4 in vivo — a phenomenon called Fab arm exchange. This is often addressed by a S228P hinge mutation that stabilizes the molecule.

---

## Higher-Order Structure and Biophysical Properties

**Higher-order structure (HOS)** is the general term for everything beyond primary sequence — secondary, tertiary, quaternary, and supramolecular organization. HOS is increasingly important to regulators because it is linked to potency and immunogenicity.

Key HOS-related concerns in manufacturing:

- **Aggregation** — formation of dimers, oligomers, or large particulate species; linked to immunogenicity risk and loss of potency; driven by shear stress, freeze-thaw, temperature, pH extremes
- **Fragmentation** — partial degradation of the molecule; can arise from proteases in cell culture or from chemical hydrolysis
- **Misfolding** — incorrect tertiary structure; can arise from stressed conditions during manufacture or storage

Techniques for HOS assessment: size-exclusion chromatography (SEC), dynamic light scattering (DLS), analytical ultracentrifugation (AUC), native mass spectrometry, hydrogen-deuterium exchange MS (HDX-MS).

---

## Manufacturing Relevance

| Structural level | What can go wrong in manufacturing | Key control point |
|---|---|---|
| Primary | Amino acid misincorporation (very rare), sequence variants | Cell line qualification, peptide mapping |
| Secondary / Tertiary | Misfolding, incorrect disulfide bonds | Bioreactor redox conditions, purification pH |
| Quaternary | Incorrect chain assembly, Fab arm exchange (IgG4) | Cell culture conditions, purification |
| HOS | Aggregation, fragmentation | Temperature control, shear, pH across all steps |

---

## Backlinks to Related Concepts

- Structural heterogeneity → [protein_structure/structure_and_function.md](structure_and_function.md)
- Glycosylation as a structural modifier → [protein_structure/glycosylation.md](glycosylation.md)
- Charge variants from deamidation/isomerization → [protein_structure/protein_charge.md](protein_charge.md)
- CQA framework for structural attributes → [product_quality/cqa_stability.md](../product_quality/cqa_stability.md)
