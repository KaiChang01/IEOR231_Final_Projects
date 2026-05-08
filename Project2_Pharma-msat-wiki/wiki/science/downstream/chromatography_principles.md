# Chromatography Principles

**Backlinks:** [downstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [downstream/chromatography_mab_purification.md](chromatography_mab_purification.md)

---

## What Chromatography Does

Chromatography separates molecules based on differential interactions with a stationary phase (the resin inside the column) as they are carried by a mobile phase (the buffer). Molecules with stronger affinity for the stationary phase are retained longer; molecules with weaker affinity pass through faster.

In biopharmaceutical downstream processing, chromatography is the primary purification tool. The therapeutic protein is either selectively bound while impurities flow through (bind-and-elute mode), or the impurities are retained while the product flows through (flow-through mode).

---

## Key Concepts

### Selectivity

Selectivity (α) describes how well two components are separated from each other. High selectivity means the column distinguishes sharply between product and impurities. Selectivity is the fundamental determinant of purity.

Selectivity depends on:
- The nature of the stationary phase (affinity ligand, charge group, hydrophobic surface)
- The mobile phase conditions (pH, salt concentration, organic modifier)
- The molecule's specific properties (charge, hydrophobicity, binding site)

### Resolution

Resolution (Rs) captures the degree of separation between two peaks:
```
Rs = 1.18 × (tR2 - tR1) / (w1/2,1 + w1/2,2)
```
where tR = peak retention time, w1/2 = peak width at half-height.

Rs > 1.5 is generally considered baseline separation. Rs depends on both selectivity and efficiency.

### Column Efficiency (Theoretical Plates)

Column efficiency (N, in theoretical plates) measures how sharp the peaks are — low dispersion = high N = high efficiency. Efficiency is determined by:
- Particle size (smaller particles → lower dispersion → higher N)
- Flow rate (higher flow → more dispersion → lower N at high flow)
- Column packing quality

Efficiency is expressed as height equivalent to a theoretical plate: H = L/N. Better columns have lower H.

### The Van Deemter Equation

```
H = A + B/u + C×u
```
- **A term (Eddy diffusion):** Multiple paths through packing. Minimized by uniform, small particles.
- **B term (longitudinal diffusion):** Molecule diffusion along the column axis. Important at low flow rates.
- **C term (mass transfer resistance):** Slow equilibration between mobile and stationary phase. Increases with flow rate.

The minimum plate height (optimum resolution) occurs at an intermediate flow velocity. In manufacturing, columns are often operated above the optimal velocity (for speed) at some cost to efficiency.

### Loading: Dynamic Binding Capacity (DBC)

The maximum amount of product that can be bound per unit volume of resin without significant breakthrough (product appearing in the column effluent during loading). DBC is measured at 10% breakthrough (DBC10%) as the standard.

DBC depends on:
- Resin ligand density and accessibility
- Protein concentration and size
- Flow rate (higher flow → lower DBC due to mass transfer)
- Buffer conditions (pH, salt for ion exchange)

Operating well below the DBC wastes capacity; operating near or above it compromises yield. Process characterization defines the acceptable load range.

### Cycle, Equilibration, Load, Wash, Elution, Strip, Regeneration, Storage

A standard bind-and-elute chromatography cycle:

1. **Equilibration:** Condition the column with the binding buffer (3–5 column volumes, CV)
2. **Load:** Apply the feed containing the product; product binds, impurities flow through
3. **Wash:** Remove non-specifically bound impurities with binding buffer or a mild intermediate wash
4. **Elution:** Apply elution buffer (changed pH, salt, or competitor) to release the product. Collect the product-containing fractions.
5. **Strip:** Apply a harsher condition to remove tightly bound contaminants (e.g., high salt, low pH, chaotropes). This regenerates the resin.
6. **Sanitization:** Apply NaOH (typically 0.1–1 M) to inactivate bioburden and denature contaminating proteins.
7. **Re-equilibration:** Return to binding buffer for the next cycle.
8. **Storage:** Column stored in a bacteriostatic solution (e.g., 20% ethanol) between campaigns.

### Column Volumes (CV)

Operations are always described in column volumes to normalize for column size. Loading 50 CV means loading 50 times the column volume of feed. Elution with 5 CV means collecting elution fractions over 5 times the column volume.

---

## Chromatography Modes Relevant to mAb Purification

### Affinity Chromatography

Uses a biologically specific ligand (e.g., Protein A) that binds the product with high selectivity. One-step separation from the bulk of impurities. Highest selectivity of any mode but also the most expensive resin.

### Ion Exchange Chromatography (IEX)

Separates by surface charge. Two subtypes:
- **Cation Exchange (CEX):** Negatively charged resin (sulfonate, carboxylate groups) binds positively charged proteins. mAbs (pI typically 7–9) bind to CEX at pH < pI.
- **Anion Exchange (AEX):** Positively charged resin (quaternary amine groups) binds negatively charged molecules. DNA and most HCPs are negatively charged at pH 7–8; mAbs may flow through AEX at this pH.

Elution from IEX is achieved by increasing salt concentration (competing ions displace the protein) or by changing pH.

### Hydrophobic Interaction Chromatography (HIC)

Separates by surface hydrophobicity. High-salt conditions promote hydrophobic interactions; elution is achieved by decreasing salt. Used for aggregate removal (aggregates are more hydrophobic than monomers due to exposed hydrophobic patches).

### Size Exclusion Chromatography (SEC)

Separates by size. No stationary-phase binding — separation is purely by differential exclusion from pores. Used analytically (SEC-HPLC for aggregate/fragment quantitation) but rarely for large-scale preparative purification due to low capacity and limited resolution.

### Mixed-Mode Chromatography

Combines multiple interaction modes (e.g., hydrophobic + ionic). Provides different selectivity than single-mode resins; useful when standard resins do not achieve the required purity.

---

## Column Hardware

**Resin (packing material):** Beaded matrix (agarose, silica, polystyrene, methacrylate) with functional groups or ligands attached. Particle sizes: 20–200 µm for preparative columns.

**Column body:** Stainless steel (traditional) or single-use (cartridge). Pressure-rated to handle operating pressures.

**Skids:** Automated chromatography systems (ÄKTA pilot/process, BioRad BioLogic, custom skids) handle buffer delivery, flow control, UV/conductivity/pH monitoring, and fraction collection.

**Sanitization:** NaOH cycling (0.1–1 M) is the standard sanitization agent. Columns must demonstrate chemical stability to NaOH cycling over their intended lifetime (number of cycles × concentration × contact time = NaOH exposure). This is validated as part of column resin lifetime studies.
