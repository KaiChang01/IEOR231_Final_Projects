# Upstream Process Overview

**Backlinks:** [science/overview.md](../overview.md) | [_index.md](../../../_index.md)  
**Related:** [science/downstream/overview.md](../downstream/overview.md) | [upstream/seed_train_bioreactor.md](seed_train_bioreactor.md) | [upstream/cellular_metabolism.md](cellular_metabolism.md)

---

## What Upstream Means

Upstream processing (USP) encompasses everything from the cell bank through harvest: the biological production of the drug substance by living cells. In contrast to chemical synthesis, upstream is a biological process — its output depends on the health, physiology, and genetic stability of the cells, not just on the concentrations of input reagents.

The upstream process typically accounts for:
- The majority of product-specific quality attributes (glycosylation, charge variants, aggregation initiated in culture)
- A large fraction of manufacturing cycle time
- The greatest process development effort (cell line development is a multi-year program)

---

## The Standard CHO-Based mAb Upstream Process

For a commercial monoclonal antibody, the upstream process follows a defined platform:

```
Master Cell Bank (MCB)
        |
Working Cell Bank (WCB)   ← thaw one vial per campaign
        |
Seed expansion (shaker flasks → small bioreactors)
        |
N-1 bioreactor (pre-production seed bioreactor)
        |
Production bioreactor (N-stage; 2,000–20,000 L)
        |
Harvest
        |
→ Downstream Processing
```

### Why CHO Cells?

Chinese Hamster Ovary (CHO) cells are the dominant production host for therapeutic mAbs. Reasons:
- **Regulatory track record:** Decades of approved products give regulators confidence
- **Post-translational modification compatibility:** CHO cells perform N-linked glycosylation and other PTMs on human-like (though not identical) pathways
- **High productivity:** Evolved cell lines routinely achieve 5–15 g/L titers in modern fed-batch processes
- **Genetic stability:** CHO cells maintain transgene expression across many generations
- **Established engineering tools:** CRISPR, zinc finger nucleases, siRNA, glycoengineering all well-developed in CHO

Alternative hosts exist for specific products: E. coli (for antibody fragments lacking glycosylation, like Fab fragments), yeast (some glycoproteins), NS0/Sp2/0 murine myeloma cells (legacy products, being phased out due to NGNA and alpha-Gal concerns), HEK293 (some gene therapy applications).

---

## Process Modes

### Fed-Batch (Dominant Platform)

Cells are inoculated into the production bioreactor. A concentrated nutrient feed is added intermittently or continuously over the culture duration. At the end of the run (typically 10–14 days), the entire culture is harvested.

Advantages: simpler operation, well-understood, good productivity, good quality control.

Disadvantages: batch-to-batch variability, productivity limited by finite culture volume and accumulation of toxic metabolites (lactate, ammonia).

### Perfusion

Cells are retained in the bioreactor (by alternating tangential flow filtration, centrifuge, etc.) while spent medium is continuously removed and fresh medium continuously added. Cells can be maintained at very high density for weeks.

Advantages: Higher volumetric productivity, removal of metabolic waste, better product quality consistency (product removed before quality degrades).

Disadvantages: Complex equipment, continuous operation demands, longer characterization required.

Perfusion is increasingly used for biologics requiring shorter residence time in culture (unstable products) or for intensified manufacturing (smaller facility footprint).

### Continuous Manufacturing

An emerging area where upstream and downstream are integrated: continuous perfusion feeds a continuous DSP train (periodic countercurrent chromatography, continuous viral inactivation, etc.). Not yet standard but regulatory guidance (FDA, EMA) is evolving to accommodate.

---

## Key Performance Indicators

| KPI | Definition | Typical commercial target |
|---|---|---|
| Volumetric productivity (titer) | g protein per L of bioreactor volume | 5–15 g/L (fed-batch) |
| Specific productivity (qp) | pg protein per cell per day | 30–80 pg/cell/day |
| Viable cell density (VCD) | 10^6 viable cells per mL | Peak 20–60 × 10^6/mL |
| Cell viability | % viable cells at harvest | ≥70% (typical IPC limit) |
| Integrated viable cell density (IVCD) | Area under VCD-time curve | Proportional to total protein produced |
| Culture duration | Days from inoculation to harvest | 10–14 days (standard fed-batch) |

---

## Upstream Section Map

| Article | Content |
|---|---|
| [upstream/transfection.md](transfection.md) | How the antibody gene gets into the CHO cell |
| [upstream/cell_line_development.md](cell_line_development.md) | How a stable, high-producing clone is selected |
| [upstream/cellular_metabolism.md](cellular_metabolism.md) | How cells grow and consume nutrients; metabolic state effects on quality |
| [upstream/seed_train_bioreactor.md](seed_train_bioreactor.md) | Expanding cells from vial to production scale |
| [upstream/harvest.md](harvest.md) | Separating cells and debris from the product-containing medium |
| [upstream/process_optimization_scale_up.md](process_optimization_scale_up.md) | DoE-based optimization and scale-up principles |
