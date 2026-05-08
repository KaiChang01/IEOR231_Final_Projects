# Glycosylation

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [protein_structure/mechanism_of_action.md](mechanism_of_action.md) | [protein_structure/structure_and_function.md](structure_and_function.md) | [upstream/cellular_metabolism.md](../upstream/cellular_metabolism.md) | [product_quality/cqa_stability.md](../product_quality/cqa_stability.md)

---

## Why Glycosylation is Central to Biopharmaceuticals

Glycosylation is the most complex and functionally important post-translational modification in biopharmaceutical manufacturing. For monoclonal antibodies, the glycan attached at Asn297 in the Fc region directly modulates effector function, half-life, and immunogenicity. Because the glycan profile is determined by the cell's glycosylation machinery and is exquisitely sensitive to culture conditions, it is one of the primary CQAs that links upstream process parameters to product quality.

The phrase "the process is the product" is nowhere more literal than in glycosylation: the same amino acid sequence produced in different cells, or even in the same cells under different conditions, will have a different glycan profile and therefore different functional properties.

---

## Types of Glycosylation

### N-linked Glycosylation

Glycans are attached to the nitrogen of asparagine (Asn, N) residues within the consensus sequence **N-X-S/T** (where X is any amino acid except proline). This is the dominant form in mAbs.

The N-glycan at **Asn297** (CH2 domain of the Fc region) is present on both heavy chains and is the primary regulatory target. It is critical for maintaining the open conformation of the Fc, which is required for FcγR and C1q binding.

**Biosynthesis pathway:**
1. A common lipid-linked precursor (Glc3Man9GlcNAc2) is assembled in the ER and transferred en bloc to the nascent protein
2. Glucose and some mannose residues are trimmed in the ER (quality control step — misfolded proteins are retained)
3. Processing continues in the Golgi: further mannose trimming, then sequential addition of GlcNAc, fucose, galactose, and sialic acid by Golgi-resident glycosyltransferases

The result is a **heterogeneous mixture** of glycoforms, not a single glycan.

### O-linked Glycosylation

Glycans attached to the hydroxyl of serine (Ser) or threonine (Thr). Less common on mAbs — generally not a CQA for most therapeutic antibodies, though relevant for some fusion proteins (e.g., etanercept has O-glycosylation). O-glycosylation is less predictable and harder to engineer.

---

## The IgG1 Fc Glycan Structure

The core structure of the Asn297 N-glycan is a **complex biantennary glycan**:

```
         Sialic acid (SA) — optional
              |
         Galactose (Gal) — optional
              |
     GlcNAc — GlcNAc
        \          /
         \        /
          Mannose
         /        \
        /          \
     Mannose    Mannose
          \        /
           \      /
            GlcNAc — [Fucose] — optional
                |
             GlcNAc  ← attached to Asn297
```

The main variable positions:
- **Core fucose** — on the innermost GlcNAc; ~90–95% fucosylated in most CHO-produced mAbs
- **Terminal galactose** — G0 (no Gal), G1 (one Gal), G2 (two Gal)
- **Terminal sialic acid** — very low levels in most CHO-derived mAbs (CHO cells use NGNA, humans use NANA — an important species difference)
- **Bisecting GlcNAc** — added by GnTIII enzyme; rare in CHO, can be engineered

---

## Key Glycoforms and Their Functional Significance

| Glycoform | Abbreviation | Functional relevance |
|---|---|---|
| No terminal Gal, no Fuc | G0F (with Fuc) / G0 (without) | Standard; G0F is the most common species in typical CHO cultures |
| One Gal, with Fuc | G1F | Slightly enhanced CDC compared to G0F |
| Two Gal, with Fuc | G2F | Enhanced C1q binding (CDC); baseline for complement |
| No core fucose | G0, G1, G2 (afucosylated) | ~50x enhanced FcγRIIIA binding → dramatically enhanced ADCC |
| High mannose | Man5–Man9 | Enhanced clearance (mannose receptor on liver macrophages); lower FcRn binding; can enhance ADCC for some receptors |
| Sialylated | G2FS1, G2FS2 | Anti-inflammatory activity (for IVIG); reduced FcγR binding |

### Core Fucosylation and ADCC

This is the most commercially important glycan attribute. The core fucose on Asn297 sterically clashes with the FcγRIIIA binding site. Removing it (afucosylation) removes this steric clash and increases FcγRIIIA binding affinity ~50-fold, dramatically enhancing ADCC.

Products engineered for enhanced ADCC (e.g., obinutuzumab, mogamulizumab) are produced with strategies to reduce fucosylation:
- Using FUT8 (α-1,6-fucosyltransferase) knockout CHO cells
- Adding fucose analogs that compete with the fucosylation pathway
- Using non-fucosylating host cells (e.g., Yeast, duckweed)

For MSAT, controlling fucosylation% is a CPP-CQA linkage that runs through the bioreactor. Fucosylation is sensitive to: cell line, glucose concentration, manganese levels, and dissolved oxygen.

---

## Process Parameters That Affect Glycosylation

This is the critical list for MSAT engineers designing upstream process control strategies:

| Parameter | Effect on glycosylation |
|---|---|
| Cell line (glycosyltransferase repertoire) | Primary determinant of glycoform distribution |
| Culture pH | Lower pH → higher sialylation; affects Golgi enzyme activity |
| Dissolved oxygen (DO) | Low DO → increased high mannose; reduced galactosylation |
| Temperature | Lower temperature → generally improved galactosylation, reduced heterogeneity |
| Glucose concentration | High glucose → increased galactosylation; affects nucleotide sugar pools |
| Glutamine / ammonia | Elevated ammonia inhibits glycosyltransferases → reduced sialylation |
| Manganese supplementation | MnSO4 → enhanced galactosylation and sialylation (cofactor for β-galactosyltransferase) |
| Uridine / galactose feeds | Direct supplementation of precursors → enhanced galactosylation |
| Culture duration / cell viability | Extended cultures with low viability → increased sialylase release → desialylation |

These relationships are the basis for process characterization experiments that establish the design space for bioreactor operation.

---

## Glycosylation as a CQA

Regulatory classification depends on the product's MoA:

- **ADCC-dependent mAbs (e.g., oncology):** Fc fucosylation% is a key CQA; afucosylation% may be specified as a release criterion
- **Non-ADCC mAbs (e.g., blocking antibodies):** Glycan profile may still be a CQA for half-life (high mannose % affects clearance) and immunogenicity (non-human glycans like NGNA in CHO)
- **All mAbs:** Glycosylation site occupancy (macroheterogeneity) — the fraction of molecules carrying a glycan at Asn297 — is typically a CQA

---

## Analytical Methods for Glycan Analysis

- **Released glycan profiling (HILIC-FLD):** Glycans enzymatically released with PNGase F, labeled with fluorescent tag, separated by HILIC HPLC. Gives relative % of each glycoform. Workhorse assay for release testing.
- **Released glycan analysis by MS:** Higher resolution, identifies novel glycans and low-abundance species.
- **Intact mass by native MS:** Can resolve glycoform distribution on the intact antibody without releasing glycans.
- **Peptide mapping with glycopeptide analysis (LC-MS):** Site-specific glycosylation analysis; important for products with multiple glycosylation sites.
- **Lectin binding assays:** Rapid, antibody-like assays specific for certain glycan features (e.g., anti-galactose lectins). Less used for release now but common in process development.

---

## Species Differences: CHO vs. Human

CHO cells are the dominant production host for mAbs but differ from human cells in glycosylation:

| Feature | CHO cell | Human cell |
|---|---|---|
| Sialic acid type | NGNA (N-glycolylneuraminic acid) | NANA (N-acetylneuraminic acid) |
| Alpha-Gal | Present at low levels | Absent (humans have anti-Gal Ab) |
| Core fucosylation | High (~90–95%) | Variable (~85–95%) |

NGNA and alpha-Gal are non-human glycan epitopes. At low levels in mAbs, they are generally tolerated, but they are monitored and can be relevant to immunogenicity assessment.
