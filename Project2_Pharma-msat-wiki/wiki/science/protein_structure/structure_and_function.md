# Structure and Function

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [protein_structure/protein_structure_basics.md](protein_structure_basics.md) | [protein_structure/mechanism_of_action.md](mechanism_of_action.md) | [protein_structure/glycosylation.md](glycosylation.md) | [product_quality/product_related_impurities.md](../product_quality/product_related_impurities.md)

---

## The Core Principle

Structure determines function. For a therapeutic antibody, every functional property — binding affinity, selectivity, effector function, half-life, immunogenicity risk — is a consequence of its three-dimensional structure. When manufacturing perturbs that structure, function changes. This is the scientific basis for why structural attributes are CQAs.

This article focuses on **structural heterogeneity**: the fact that the product is not a single molecule but a population of molecular variants, and the implications for manufacturing and quality control.

---

## Sources of Structural Heterogeneity

A biopharmaceutical product is not a pure, uniform molecule. It is a complex mixture of molecular species that differ in post-translational modifications, degradation states, or assembly errors. This heterogeneity is inherent to biological production.

### Post-Translational Modifications (PTMs)

PTMs are chemical modifications made to the protein after translation, either enzymatically (in the cell) or non-enzymatically (spontaneously, in the cell or during processing).

**Enzymatic PTMs (cell-controlled):**
- **N-linked glycosylation** — attachment of complex oligosaccharide chains to Asn residues in an N-X-S/T sequon. The major PTM for mAbs; see [protein_structure/glycosylation.md](glycosylation.md) for full treatment.
- **C-terminal lysine clipping** — CHO cells express a carboxypeptidase that cleaves the C-terminal lysine from heavy chains. The result is a mixture of molecules with 0, 1, or 2 C-terminal lysines. This is a common source of charge heterogeneity but is generally considered non-critical for most mAbs since the clipping is nearly complete in serum.
- **N-terminal pyroglutamate** — glutamine or glutamate at the N-terminus of heavy or light chains can cyclize to form pyroglutamate. This also contributes to charge variants.

**Non-enzymatic PTMs (process- and time-driven):**
- **Deamidation** — asparagine (N) spontaneously loses an amide group to become aspartate (D) or isoaspartate. Rate depends on local sequence context, pH, temperature. Introduces a negative charge and can disrupt local structure if it occurs in the CDRs. A common charge variant and potential CQA.
- **Oxidation** — methionine and tryptophan residues can be oxidized by reactive oxygen species. Met oxidation in the Fc CH2 domain can reduce FcRn binding and shorten half-life. Driven by process conditions (dissolved oxygen, light exposure, metal ions).
- **Isomerization** — aspartate can isomerize to isoaspartate, disrupting backbone geometry. Similar functional consequences to deamidation.
- **Glycation** — non-enzymatic attachment of glucose to lysine residues. Level depends on glucose concentration in the bioreactor and time at elevated glucose. Adds a positive charge.

### Size Variants

- **Aggregates** — dimers, oligomers, submicron particles, visible particles. See [product_quality/product_related_impurities.md](../product_quality/product_related_impurities.md). Major immunogenicity and potency concern.
- **Fragments** — Fab arms, Fc fragments, half-molecules. Arise from protease activity or chemical hydrolysis at the hinge. Reduce potency; lose half-life (no FcRn recycling for fragments).
- **Half-antibodies** — one heavy + one light chain pair. Particularly relevant for IgG4 due to Fab arm exchange.

### Sequence Variants

Misincorporation of incorrect amino acids occurs at low frequency but can be detected by sensitive mass spectrometry. Cell line qualification includes peptide mapping to confirm the protein sequence. True sequence variants (not PTMs) are rare but represent a permanent change in the product.

---

## Functional Consequences of Key Variants

| Variant | Location | Functional consequence |
|---|---|---|
| CDR deamidation | Binding site | Reduced antigen affinity, loss of potency |
| Met oxidation (CH2) | Fc | Reduced FcRn binding → shorter half-life |
| Aggregates | Anywhere | Immunogenicity, loss of monomer potency |
| Hinge fragmentation | Hinge | Loss of bivalency, loss of Fc functions |
| Afucosylation | Asn297 glycan | Enhanced ADCC (desired for some products) |
| High mannose glycans | Asn297 | Altered clearance, possible enhanced FcγR binding |
| C-terminal Lys | Fc | Charge variant; minimal functional impact |

---

## The Concept of Structural Comparability

When a process change is made (a manufacturing site change, a raw material change, a process parameter shift), regulators require a demonstration that the product produced by the new process is **comparable** to the product produced by the old process — meaning the structural profile has not changed in a way that matters to safety or efficacy.

This comparability assessment is grounded in the structure-function relationship:
1. Characterize structural attributes before and after the change (primary, secondary, tertiary, HOS, PTM profile)
2. Map each attribute to its functional consequence
3. Determine whether any observed differences are within the range of historical variability and are scientifically justified as non-impactful

This is why a deep understanding of structure-function relationships is a core MSAT competency. See: [tech_transfer/comparability_studies.md](../../../tech_transfer/comparability_studies.md)

---

## Analytical Tools for Structural Characterization

| Attribute | Technique |
|---|---|
| Primary structure (sequence) | Peptide mapping by LC-MS/MS |
| Disulfide bonds | Non-reduced peptide mapping |
| PTMs (deamidation, oxidation) | Peptide mapping, intact mass |
| Glycan profile | Released glycan analysis (HILIC-FLD, MS) |
| Aggregates | SEC-HPLC, DLS, AUC, MFI |
| Fragments | SDS-PAGE (reduced/non-reduced), CE-SDS |
| Charge variants | icIEF (imaged capillary isoelectric focusing), CEX-HPLC |
| Secondary structure | CD, FTIR |
| Tertiary / HOS | HDX-MS, native MS, DSC |

---

## Manufacturing Process Effects on Structure

Each step of the manufacturing process introduces specific structural risks:

| Process step | Primary structural risk |
|---|---|
| Bioreactor (cell culture) | Glycosylation variation, oxidation, deamidation begin |
| Harvest (depth filtration, centrifugation) | Shear-induced aggregation |
| Protein A chromatography | Low-pH elution → aggregation, deamidation |
| Low-pH viral inactivation | Aggregation, fragmentation |
| Ion exchange chromatography | Enrichment or depletion of charge variants |
| UF/DF | Concentration-induced aggregation, shear |
| Freeze-thaw (bulk drug substance) | Aggregation, cryoconcentration effects |
| Formulation | pH and excipient effects on long-term stability |

Understanding this risk map is what allows MSAT to design the right control strategy for each step.
