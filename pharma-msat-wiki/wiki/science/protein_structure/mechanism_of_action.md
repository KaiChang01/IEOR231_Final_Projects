# Mechanism of Action

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [protein_structure/structure_and_function.md](structure_and_function.md) | [protein_structure/protein_structure_basics.md](protein_structure_basics.md) | [product_quality/cqa_stability.md](../product_quality/cqa_stability.md)

---

## Why MoA Matters to MSAT

Understanding mechanism of action (MoA) is not just a pharmacology topic — it directly informs which molecular attributes are critical to safety and efficacy, which in turn defines the CQA framework. If you don't know how the molecule works, you cannot rationally decide which quality attributes to measure or control.

For example: a mAb that kills tumor cells via ADCC depends on its Fc region binding Fc gamma receptors on NK cells. That interaction is glycan-dependent. Therefore, Fc glycosylation is a CQA. A mAb that works purely by blocking a receptor ligand interaction has no such dependence — glycosylation may still matter for half-life, but the criticality assessment is different.

---

## Monoclonal Antibody Mechanisms

mAbs can kill cells, block pathways, or recruit effector functions. Most therapeutic mAbs use one or more of the following:

### 1. Target Neutralization / Blocking

The mAb binds a soluble ligand or receptor and physically blocks an interaction. Examples:

- **Bevacizumab (Avastin)** — binds VEGF-A, blocking angiogenesis
- **Adalimumab (Humira)** — binds TNF-alpha, blocking inflammation
- **Nivolumab (Opdivo)** — binds PD-1, blocking immune checkpoint signaling

The binding affinity (Kd) and epitope coverage determine potency. Both are functions of CDR sequence and structure.

### 2. Antibody-Dependent Cellular Cytotoxicity (ADCC)

The mAb binds a target on a tumor cell via its Fab. The Fc region then binds FcγRIIIA (CD16a) on NK cells. The NK cell is activated and kills the target cell.

ADCC is governed by:
- **Fc glycosylation** — specifically core fucosylation of the Asn297 glycan. Afucosylated antibodies bind FcγRIIIA with ~50x higher affinity and show dramatically enhanced ADCC. This is why afucosylation is a CQA for many oncology antibodies.
- **IgG subclass** — IgG1 has the highest ADCC activity; IgG4 has essentially none.
- **FcγRIIIA polymorphism** (V158F) — patients vary in their response to ADCC-dependent mAbs.

### 3. Complement-Dependent Cytotoxicity (CDC)

The mAb Fc region activates the classical complement pathway by binding C1q. This triggers a cascade leading to the membrane attack complex (MAC), which lyses the target cell.

CDC is less common as a primary MoA but contributes for rituximab (anti-CD20). IgG1 and IgG3 activate complement; IgG4 does not.

### 4. Antibody-Dependent Cellular Phagocytosis (ADCP)

Macrophages express Fcγ receptors. A mAb-coated target cell is engulfed and destroyed. Often works in concert with ADCC.

### 5. Direct Apoptosis Induction

Some mAbs crosslink surface receptors and directly trigger programmed cell death without requiring immune effector cells. Example: certain anti-DR5 (death receptor 5) antibodies.

### 6. Receptor Downregulation

Binding can induce receptor internalization, reducing surface expression of the target and preventing ligand engagement. Many anti-HER2 antibodies (pertuzumab, trastuzumab) act partly through this mechanism.

---

## Bispecific Antibodies

Bispecific antibodies (bsAbs) have two distinct binding specificities — typically one targeting a tumor antigen and one targeting a T-cell activating receptor (e.g., CD3).

Example: **blinatumomab** (BiTE format) — one arm binds CD19 on B-cell malignancies, the other binds CD3 on T cells. This physically bridges the T cell to the tumor cell, directing T-cell killing. No Fc effector function is required.

Manufacturing implications: bispecifics are more complex to produce and purify than conventional mAbs. Mispairing of heavy and light chains is a key product-related impurity that must be controlled and measured.

---

## Fc-Mediated Effector Functions: Summary

| Effector function | Fc receptor | Cell type | Relevant glycan |
|---|---|---|---|
| ADCC | FcγRIIIA (CD16a) | NK cells, monocytes | Core fucose (negative regulator) |
| ADCP | FcγRI, FcγRIIa | Macrophages, monocytes | Fucosylation |
| CDC | C1q | — | Galactosylation (slight positive effect) |
| Half-life extension | FcRn | Endothelium | Sialylation (minor effect) |

---

## Neonatal Fc Receptor (FcRn) and Half-Life

IgG antibodies have long serum half-lives (typically 2–3 weeks for IgG1) because of FcRn-mediated recycling. After endocytosis, IgG binds FcRn in the acidic endosome (pH ~6), is protected from lysosomal degradation, and is recycled to the cell surface where it dissociates at physiological pH (7.4).

Mutations in the Fc region can enhance FcRn binding and extend half-life (e.g., YTE and LS mutations), enabling less frequent dosing.

Manufacturing relevance: Fc integrity (no clipping at the hinge, correct disulfide bonds) is required for normal FcRn binding and expected half-life. Fragmentation is a CQA partly because it compromises this interaction.

---

## From MoA to CQA

This is the critical linkage for MSAT:

| MoA element | Structural requirement | CQA |
|---|---|---|
| Antigen binding | CDR conformation intact | Binding affinity / potency |
| ADCC | Asn297 afucosylation | Fc glycan profile (fucosylation %) |
| Half-life | FcRn binding at pH 6 | Fc integrity, no hinge clipping |
| CDC | C1q binding | IgG1 subclass, Fc integrity |
| All mechanisms | No aggregation | Aggregates (% monomer) |
| All mechanisms | Correct amino acid sequence | Sequence variants / primary structure |

See: [product_quality/cqa_stability.md](../product_quality/cqa_stability.md) for how these are formally assessed and controlled.
