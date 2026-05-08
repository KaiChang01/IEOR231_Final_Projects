# Cellular Metabolism & Growth Kinetics

**Backlinks:** [upstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [upstream/seed_train_bioreactor.md](seed_train_bioreactor.md) | [protein_structure/glycosylation.md](../../protein_structure/glycosylation.md) | [product_quality/cqa_cpp_process_control.md](../../product_quality/cqa_cpp_process_control.md)

---

## Why Metabolism Matters to MSAT

The bioreactor is not a chemical reactor — it is a living system. Cell growth, productivity, and product quality are all downstream consequences of cellular metabolic state. An MSAT engineer who cannot interpret a metabolic profile (glucose, lactate, glutamine, ammonia, VCD, viability over time) cannot make informed decisions about cell culture process development, deviation investigations, or scale-up.

More specifically:
- Lactate and ammonia accumulation are toxic to cells and degrade product quality
- Metabolic byproducts drive pH changes that must be compensated (CO2, base addition)
- Nutrient depletion limits productivity and triggers cell stress/apoptosis
- The nucleotide sugar pools that supply glycosylation enzymes are metabolic outputs

---

## Growth Phases

In a batch or fed-batch culture, cells progress through defined growth phases:

### 1. Lag Phase

Immediately after inoculation. Cells adapt to the new environment (adjust metabolism, recover from cold storage if seeded from a frozen vial). Minimal cell division. Duration: 12–24 hours.

### 2. Exponential (Log) Phase

Cells dividing at the maximum rate (μmax) supported by nutrient availability. This is when most cell expansion occurs. Glucose and glutamine are consumed rapidly; lactate and ammonia accumulate.

The specific growth rate (μ) is defined as:
```
μ = (ln N2 - ln N1) / (t2 - t1)
```
where N is cell count. During log phase, μ ≈ μmax.

### 3. Stationary Phase

Nutrient depletion or toxic metabolite accumulation (or deliberate temperature shift) slows growth. VCD plateaus. In fed-batch, the feed is designed to sustain cells in this phase for as long as possible — this is when the majority of antibody is produced (cells allocate resources to secretion rather than growth).

### 4. Decline Phase

Cell viability begins to fall. Apoptosis and necrosis increase. Intracellular proteases and other enzymes are released into the culture medium. Product quality degrades: HCP levels rise, fragmentation increases, glycosylation changes. Harvest before viability falls below ~70% is a standard IPC criterion.

---

## Key Metabolites

### Glucose

The primary carbon and energy source. Taken up by cells and metabolized through glycolysis to pyruvate, then either:
- Oxidized in the TCA cycle to CO2 + H2O (oxidative phosphorylation, ~30 ATP per glucose)
- Reduced to lactate (Warburg effect / aerobic glycolysis)

CHO cells, like most mammalian cells in culture, preferentially produce lactate even under aerobic conditions (Warburg effect). This leads to:
- Lactate accumulation in the culture
- pH decrease (lactic acid)
- Base addition to maintain pH setpoint
- Large osmolality increases if NaOH is used for pH control

Metabolic engineering approaches and feed design aim to shift cells toward **lactate consumption** in later culture stages, reducing the toxic load.

**Glucose as CPP:** Glucose concentration in the bioreactor directly affects:
- Cell growth rate (glucose-limited growth at low concentrations)
- Lactate production rate (higher glucose → more Warburg)
- Glycosylation (glucose feeds UDP-glucose and UDP-galactose nucleotide sugar pools; low glucose → reduced galactosylation)
- Glycation (high glucose → lysine glycation; high charge variants)

### Glutamine

The primary nitrogen source. Consumed by cells and metabolized to:
- Glutamate → α-ketoglutarate (TCA cycle entry)
- Ammonia (as a byproduct of glutamine catabolism and from spontaneous deamination)

**Ammonia** is toxic to cells above ~5–10 mM and inhibits glycosyltransferases, particularly those involved in sialylation. Ammonia accumulation is a common reason for quality degradation in late-stage cultures.

Strategies to manage ammonia:
- Glutamine-free feeds using dipeptides (Ala-Gln, Gly-Gln) that release glutamine slowly
- GS-expressing cell lines that synthesize glutamine from glutamate + ammonia (net ammonia consumer)
- pH control strategies that favor ammonia volatilization

### Lactate

Produced by cells during aerobic glycolysis. Toxic above ~30–40 mM. Also drives base addition to maintain pH, increasing osmolality.

In many fed-batch processes, cells shift from net lactate production to net lactate consumption ("metabolic shift") in mid-culture. This shift is associated with improved culture performance and product quality. Controlling glucose concentration in the feed is a primary tool for promoting this shift.

### Oxygen and CO2

**Dissolved oxygen (DO):** Cells require oxygen for oxidative phosphorylation. DO is maintained at 30–50% air saturation in most processes by sparging air/O2 into the bioreactor. Low DO → impaired mitochondrial function, increased reactive oxygen species, altered glycosylation (reduced galactosylation, more high mannose).

**Dissolved CO2 (dCO2):** A metabolic byproduct and pH contributor. At high cell densities, CO2 accumulates, driving pH down. In large-scale bioreactors, CO2 removal (by sparging with N2 or increasing gas flow) is a scale-up challenge. High dCO2 inhibits cell growth and can affect glycosylation.

---

## Growth Kinetics: Key Parameters

| Parameter | Symbol | Units | Typical range |
|---|---|---|---|
| Specific growth rate | μ | d⁻¹ | 0.4–0.7 d⁻¹ (log phase) |
| Doubling time | td | h | 18–30 h |
| Maximum viable cell density | VCDmax | 10⁶/mL | 20–60 × 10⁶/mL (fed-batch) |
| Specific productivity | qp | pg/cell/day | 20–80 pg/cell/day |
| Specific glucose consumption rate | qGluc | mmol/10⁶ cells/day | varies |
| Specific lactate production rate | qLac | mmol/10⁶ cells/day | varies |
| Yield coefficient (lactate/glucose) | YL/G | mol/mol | 0–2 (0 = fully oxidative, 2 = fully glycolytic) |
| Integrated viable cell density | IVCD | 10⁶ cells·d/mL | drives total titer |

---

## Temperature Shift Strategy

A common fed-batch process development strategy is the **temperature shift**: cells are grown at 37°C during the exponential phase, then shifted to a lower temperature (31–34°C) at a defined point (usually early stationary phase).

Effects:
- Slower growth → cells allocate more resources to protein secretion (qp increases)
- Reduced metabolism → less lactate accumulation
- Extended culture duration → more total product
- Reduced protease activity → less fragmentation
- Can affect glycosylation (lower temp → less galactosylation in some systems)

The temperature shift timing and magnitude are CPPs that affect titer and product quality. They require characterization and validation as part of the process development package.

---

## Feeding Strategy

The **feed medium** is a concentrated nutrient solution added to the bioreactor to replenish glucose, amino acids, vitamins, and growth factors consumed by the cells.

Feed strategies:
- **Bolus feeding:** Fixed volume additions at defined time points. Simple to execute, less precise.
- **Glucose-stat / controlled feeding:** Continuous or frequent small feeds based on glucose measurement (on-line or at-line). Maintains glucose in a defined window. Requires more sophisticated measurement and control.
- **Cell-specific feeding (CSPR):** Feed rate is proportional to cell density. Theoretically gives each cell the same amount of nutrients regardless of density.

Feed composition optimization is a major process development effort. The amino acid profile must match cell consumption patterns; trace metals (copper, zinc, manganese, iron) must be included at appropriate levels; pH of the feed must be considered.

**Manganese supplementation** deserves specific mention: manganese is a cofactor for β-galactosyltransferase and α-sialyltransferase. Adding MnSO4 to the feed medium can significantly increase galactosylation and sialylation levels — and therefore can be used to shift the glycan profile. This is a common tool in process optimization when galactosylation is a CQA.
