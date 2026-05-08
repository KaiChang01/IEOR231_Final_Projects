# Transfection

**Backlinks:** [upstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [upstream/cell_line_development.md](cell_line_development.md)

---

## What Transfection Is

Transfection is the process of introducing foreign DNA into a eukaryotic cell. In biopharmaceutical manufacturing, the DNA of interest is a gene expression construct encoding the therapeutic antibody's heavy and light chains. The goal of transfection is to get this DNA into the CHO cell nucleus where it can be transcribed, and to have it stably integrate into the host cell genome so that it is passed to all daughter cells during proliferation.

There are two types of transfection outcomes:

- **Transient transfection:** The introduced DNA remains episomal (not integrated) and is expressed for a limited time (days to weeks) before being diluted out or degraded. Used for rapid protein production in process development but not suitable for manufacturing cell lines.
- **Stable transfection:** The introduced DNA integrates into the host cell genome and is stably inherited by daughter cells. This is the foundation of every manufacturing cell line.

---

## Expression Constructs

The gene of interest is carried in a **plasmid vector** — a circular DNA molecule engineered with the necessary regulatory elements:

- **Promoter:** Drives high-level transcription of the antibody gene. Most common: CMV (cytomegalovirus) immediate early promoter, EF1α, or proprietary synthetic promoters.
- **Heavy chain gene** — full-length cDNA encoding the antibody heavy chain including signal peptide (directs the protein to the secretory pathway)
- **Light chain gene** — full-length cDNA encoding the antibody light chain
- **Selection marker** — allows cells that have taken up the construct to be selected. Common markers:
  - **DHFR (dihydrofolate reductase):** used in DHFR-deficient CHO cells (CHO DG44 or DUXB11). Cells that integrate the construct survive in media lacking hypoxanthine/thymidine. Subsequent amplification with methotrexate (MTX) increases DHFR (and co-amplified antibody gene) copy number.
  - **Glutamine synthetase (GS):** used in GS-deficient CHO or NS0 cells. Cells with GS integration survive in glutamine-free media. Lonza's proprietary GS system. No amplification step needed; typically gives higher initial productivity.
  - **Antibiotic resistance genes (neo, hygro, zeo):** simpler but less commonly used for manufacturing cell lines
- **Poly-A signal:** Required for mRNA stability and processing.

The heavy and light chain genes can be on a **single plasmid** (easier to transfect, ensures co-delivery) or on **two separate plasmids** (can optimize heavy/light chain ratio by varying plasmid amounts).

---

## Transfection Methods

### Electroporation

The cell membrane is transiently permeabilized by a high-voltage electrical pulse, allowing DNA to enter the cytoplasm. Highly efficient for CHO cells.

Instruments: MaxCyte (flow-electroporation for large-scale), Lonza 4D Nucleofector, BioRad Gene Pulser.

Advantages: High efficiency, scalable, no viral vector required.
Disadvantages: Some cell death, requires optimization of pulse conditions.

### Lipofection (Lipid Nanoparticles)

Cationic lipids form complexes (lipoplexes) with the negatively charged DNA, which are endocytosed by cells. Lower efficiency than electroporation for CHO; more commonly used for HEK293 transient transfection.

### Viral Transduction

Retroviruses and lentiviruses can stably integrate transgenes. Used for some research applications but less common for manufacturing cell line development due to regulatory concerns about viral integration sites.

---

## Stable Integration and Genome Position Effects

After transfection, the DNA integrates at **random genomic locations**. This is the source of the clone-to-clone variability that makes cell line development a screening exercise: integration near heterochromatin leads to gene silencing (low productivity), while integration in transcriptionally active regions leads to high expression.

The same construct in the same CHO cell line will produce vastly different titers depending on where it integrates. This is why thousands of clones must be generated and screened. See: [upstream/cell_line_development.md](cell_line_development.md)

### Site-Specific Integration

Emerging technologies allow targeting of the transgene to pre-characterized "safe harbor" sites in the CHO genome that support high, stable expression:

- **RMCE (Recombinase-Mediated Cassette Exchange):** Uses recombinases (Flp, Cre) to integrate the gene at a pre-inserted landing pad
- **CRISPR-Cas9 directed integration:** Directs integration to specific loci; rapidly developing

These approaches aim to reduce clone-to-clone variability and accelerate cell line development by producing high-expressing clones with greater consistency.

---

## Gene Copy Number and Expression Level

The number of gene copies integrated affects expression level, but the relationship is not simply linear:
- Too few copies → low productivity
- Too many copies → can be unstable, mRNA limiting rather than gene copy number

**DHFR amplification:** By gradually increasing the concentration of methotrexate (a DHFR inhibitor), selection pressure drives cells to amplify the DHFR gene — and co-amplify neighboring sequences including the antibody gene. This can increase copy number 50–100x and dramatically increase titer. However, highly amplified cell lines can be genetically unstable over long culture periods.

GS-based systems generally operate at lower copy number but higher per-copy expression due to the tight selection pressure, and they tend to be more stable.

---

## Quality and Regulatory Considerations

**Expression cassette integrity:** The full sequence of the inserted expression cassette must be confirmed after cell line development (sequencing). Any mutation in the gene encoding the antibody sequence represents a potentially serious quality issue.

**Genetic stability:** The cell line must be shown to stably express the product throughout the duration of the manufacturing process and over the full cell age permitted (typically measured in population doubling levels, PDLs). Stability is assessed by comparing end-of-production cells (EOPCs) to early passage cells for expression level, gene copy number, and product quality.

**ICH Q5D:** The ICH guideline on derivation and characterization of cell substrates used for production of biotechnological/biological products governs how cell lines must be characterized and what must be tested before clinical use.
