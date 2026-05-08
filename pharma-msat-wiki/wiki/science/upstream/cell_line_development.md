# Cell Line Development & Clone Selection

**Backlinks:** [upstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [upstream/transfection.md](transfection.md) | [upstream/cellular_metabolism.md](cellular_metabolism.md)

---

## Why Cell Line Development is a Multi-Year Effort

The production cell line is the most fundamental determinant of everything downstream: titer, product quality (glycosylation, charge variants, impurity profile), process stability, and ultimately the product that goes into patients. A poorly selected cell line cannot be fully compensated for by downstream process optimization. Getting this right is worth years of effort because the cell line, once locked for clinical use, cannot be easily changed.

A typical cell line development (CLD) timeline from transfection to research cell bank (RCB):

- Transfection → pool selection: 3–6 weeks
- Single-cell cloning and outgrowth: 4–6 weeks
- Early screening (productivity, quality): 6–8 weeks
- Down-selection, stability assessment, fed-batch evaluation: 8–16 weeks
- Clone selection, Master Cell Bank (MCB) preparation and characterization: 6–12 months

Total: typically 12–24 months from transfection to a characterized MCB ready for clinical manufacturing.

---

## The Clone Selection Funnel

### Step 1: Stable Pool Generation

After transfection and selection (DHFR or GS), surviving cells form a **stable pool** — a heterogeneous mixture of cells, each having integrated the transgene at a different genomic location. The pool expresses the antibody but is too variable for manufacturing. It can be used for early process development.

### Step 2: Single-Cell Cloning

The stable pool is diluted to approximately one cell per well in 96-well plates. Each well that grows a colony is, in principle, a clonal population derived from a single cell — all cells in that well have identical genomes and integration sites.

**Clonality assurance** is a regulatory requirement (ICH Q5D): manufacturers must demonstrate that the production cell line is derived from a single cell. Methods:
- **Limiting dilution:** Dilute to <0.5 cells/well; statistical assurance of single-cell origin
- **Fluorescence-activated cell sorting (FACS):** Sort single cells into individual wells; imaging confirms one cell per well at time of seeding
- **Microfluidic single-cell dispensing (e.g., ClonePix, Berkeley Lights Beacon):** Emerging high-throughput systems with imaging documentation of single-cell origin

The Beacon system (Berkeley Lights) can perform selection and export in a microfluidic chip with documented single-cell imaging for every clone — an emerging standard for regulatory-grade clonality.

### Step 3: High-Throughput Screening

Hundreds to thousands of clones are screened in 96-well and 24-well plates. The key outputs at this stage:

- **Titer (productivity):** Measured by ELISA or protein A HPLC on clarified supernatant. Used to rank clones; top 5–20% advance.
- **Product quality attributes:** At early stages, often limited to SEC (aggregation) and icIEF (charge variants). Glycosylation analysis added at later stages.
- **Growth profile:** Viable cell density, viability, growth rate.

High-throughput tools: automated liquid handlers, miniaturized fed-batch (24-deepwell, ambr15), plate readers.

### Step 4: Fed-Batch Evaluation

Top clones from screening are evaluated in fed-batch conditions mimicking the intended production process, typically in ambr250 micro-bioreactors (250 mL, 24–48 parallel units) or shake flasks. This identifies whether high titer in the screen holds up under more representative conditions.

Key evaluation criteria:
- Titer under fed-batch conditions
- Full quality attribute profile (glycan, charge, aggregation, fragments, HCP)
- Growth kinetics (peak VCD, specific growth rate, metabolic profile)
- Consistency across replicate runs

### Step 5: Stability Assessment

The top 2–5 clones undergo a stability assessment: cells are passaged for an extended period (typically 60–100 generations past the research cell bank) to simulate the full manufacturing timeline. At early, mid, and late passage points, expression level and product quality are assessed.

A clone that loses 20–30% of its titer or shows quality drift over this period is a stability concern and would typically be deprioritized.

### Step 6: Clone Selection and Cell Banking

The best clone (or top 2 in parallel) is selected based on:
- Productivity
- Product quality profile (must be consistent with target product profile, TPP)
- Genetic stability
- Consistency / process robustness

This clone is expanded and banked as the **Research Cell Bank (RCB)** or directly as the **Master Cell Bank (MCB)**.

---

## Cell Banking

### Master Cell Bank (MCB)

A homogeneous pool of cells, all derived from the selected clone, cryopreserved in a large number of identical vials (typically 200–500 vials) at a defined passage number. Stored at two independent locations in liquid nitrogen.

The MCB is the source of all material used in clinical and commercial manufacturing. It is characterized to ICH Q5D requirements:
- Cell identity (isozyme analysis, karyotype, STR profiling)
- Sterility, mycoplasma, adventitious virus testing
- Expression level and product quality
- Sequence confirmation of expression cassette
- Gene copy number

### Working Cell Bank (WCB)

Derived from one or a few vials of the MCB. A larger collection of vials (often 500–1000) used for routine manufacturing. Each manufacturing campaign begins by thawing a single WCB vial.

The MCB → WCB passage adds a defined number of doublings; the cumulative passage from the MCB to end of the production run (the end-of-production cells, EOPC) is kept within the approved cell age limit.

---

## Accelerating CLD: Technology Trends

| Technology | What it does | Advantage |
|---|---|---|
| Berkeley Lights Beacon | Microfluidic single-cell selection with imaging | Documented clonality, high throughput, early quality data |
| ambr15/250 micro-bioreactors | Miniaturized, automated fed-batch at 15–250 mL | High-throughput screening under production-mimicking conditions |
| High-content imaging (ClonePix) | Identifies high-secreting colonies by fluorescent immunoassay | Rapid titer-based enrichment before screening |
| Targeted integration (CRISPR) | Directs insertion to defined genomic loci | Reduced clone-to-clone variability, faster development |
| AI-based clone ranking | ML models predict manufacturability from early data | Helps prioritize clones for downstream evaluation |

---

## The Clone-to-Product Quality Link

The cell line selected has a direct effect on product quality attributes that cannot be changed by downstream processing:

- **Glycosylation profile** — the CHO cell's specific glycosyltransferase expression pattern (which can vary clone to clone) determines the baseline glycoform distribution
- **Charge variant baseline** — some clones are prone to higher deamidation or C-terminal Lys retention due to endogenous enzyme expression levels
- **HCP profile** — the clone affects which CHO proteins are secreted into the culture medium; some clones have high levels of specific problematic HCPs (e.g., cathepsin D, lipase)

This is why quality attributes must be measured during clone selection, not just titer. A clone with excellent productivity but a glycan profile inconsistent with the target product profile must be rejected at the CLD stage, not discovered during tech transfer.
