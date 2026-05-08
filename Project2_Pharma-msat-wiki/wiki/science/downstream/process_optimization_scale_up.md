# Process Optimization & Scale-Up (Downstream)

**Backlinks:** [downstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [downstream/chromatography_principles.md](chromatography_principles.md) | [downstream/uf_df.md](uf_df.md) | [tech_transfer/scale_up.md](../../../tech_transfer/scale_up.md)

---

## DSP Optimization: The Trade-Off Space

Downstream process optimization is fundamentally a multi-objective problem. For each chromatography step, the key trade-offs are:

- **Purity vs. yield:** Tighter operating conditions that improve purity (e.g., shallower elution gradient on CEX → better charge variant resolution) generally reduce yield (more product is discarded with impurities)
- **Throughput vs. resolution:** Faster flow rates → higher throughput but lower resolution
- **Column loading vs. yield:** Higher load density → more product per cycle (reduces number of cycles needed) but risks breakthrough and reduces purity
- **Resin reuse vs. column lifetime:** More cycles per column reduces cost but risks resin deterioration affecting performance

The optimization program finds the operating window where all constraints (purity, yield, throughput, column lifetime) are simultaneously satisfied.

---

## DoE Methodology for DSP

### Identify Parameters to Study

For a typical CEX bind-and-elute step, candidate parameters include:
- Load pH and conductivity (determine binding)
- Wash buffer pH and conductivity
- Elution buffer pH and conductivity (endpoint or step)
- Elution gradient slope (if gradient)
- Load density (g mAb per L resin)
- Flow rate during load, wash, elution
- Temperature

### Risk Assessment (FMEA)

Score each parameter for potential impact on yield and CQAs. Parameters with high risk scores are studied; parameters with low scores are fixed at standard values.

### Screening DoE

A fractional factorial design (e.g., Plackett-Burman with 12–20 runs) to identify which parameters significantly affect yield, HCP clearance, aggregate removal, and charge variant profile.

### Characterization DoE

Response surface design (central composite or Box-Behnken) on the 2–4 most important parameters. Generates a mathematical model of each response as a function of the parameters.

### Design Space Definition

From the response surface models, overlay contour plots to identify the operating region where all responses simultaneously meet specifications. This defines the design space (or PAR) submitted to regulators.

### Scale-Down Model Qualification

The optimization studies are run at small scale (e.g., 1-mL PreDictor plates for high-throughput resin screening, 5 mL Tricorn columns, or 200 mL research columns). The scale-down model must be qualified against the manufacturing scale.

---

## Scaling Chromatography Columns

Scale-up of chromatography is more straightforward than bioreactor scale-up because columns are fundamentally linear: if you keep the same linear flow velocity (cm/h) and bed height, the chromatographic behavior (retention time, peak shape, resolution) is maintained. Scale is changed by increasing column diameter.

### Constant Parameters During Scale-Up

| Parameter | Must be maintained | Why |
|---|---|---|
| Bed height (cm) | Yes | Determines plate count and retention volume |
| Linear flow velocity (cm/h) | Yes | Determines residence time in column |
| Column volumes (CV) for each step | Yes | Normalizes for column size |
| Buffer compositions and pH | Yes | Determine binding and elution |
| Load density (g/L resin) | Yes | Determines yield and pool quality |

Volume scales with cross-sectional area (diameter²). Doubling the diameter increases capacity 4-fold at the same bed height and flow velocity.

### Practical Scale-Up Challenges

**Column packing:** Large columns (≥60 cm diameter) are more difficult to pack uniformly than laboratory columns. Poor packing leads to channeling (non-uniform flow), which reduces resolution. Packing qualification tests (HETP, asymmetry factor using a test tracer like acetone) confirm adequate packing.

**Buffer preparation:** At commercial scale, buffers are prepared in 1,000–10,000 L tanks. Buffer preparation variability (pH ±0.05, conductivity ±1 mS/cm) can affect column performance. Buffer preparation is a CPP for DSP and must be controlled and validated.

**Pressure constraints:** Commercial-scale columns at high flow rates generate significant back pressure. The column hardware and resin must be pressure-rated for operating conditions. Some high-resolution resins (smaller particles) are pressure-limited at large scales and may require lower flow rates.

**Column equilibration volumes:** Equilibration time in column volumes is constant, but in absolute time, it may be longer due to lower allowable flow rates. This affects total cycle time and manufacturing schedule.

### Column Skid Scale-Up

Lab and pilot columns are run on research chromatography systems (ÄKTA). Commercial columns are run on process chromatography skids — custom-built, validated systems with appropriate pressure ratings, automated buffer selection, UV/conductivity/pH monitoring, and fraction collection.

The control system for the process skid must be validated (Part 11 compliance for electronic records) and operate within IPC alert/action limits.

---

## Scale-Up of UF/DF

UF/DF scale-up follows cross-flow filtration engineering principles:

### Constant Parameters

- **Membrane MWCO** (same membrane type and pore size)
- **Transmembrane pressure (TMP)** setpoint
- **Cross-flow velocity** (linear velocity across membrane surface)
- **Number of diafiltration volumes**
- **Buffer composition**

Scale is achieved by increasing membrane area (adding more cassettes or using larger cassette holders).

### Scale-Up Challenges

**Flux decline at scale:** Large-scale UF/DF systems have more hold-up volume and longer path lengths. Shear history and protein concentration polarization over time can differ from small scale.

**System hold-up volume:** The fraction of protein in the system hold-up volume (piping, pump heads, manifolds) is larger relative to the total volume at small scale. Scale-up must account for the absolute hold-up volume, not just the ratio, when calculating yield and final concentration.

**Mixing at dilution:** When adding concentrated excipient solutions or adjusting pH during UF/DF, mixing uniformity must be validated at large scale.

**Heat generation:** Large-scale pumps and fluid friction generate heat. Temperature control during UF/DF must be validated at scale.

---

## Continuous DSP: Emerging Approaches

Traditional DSP is batch: one Protein A cycle at a time, then the pool holds while CEX runs, etc. Continuous DSP approaches are emerging to increase throughput and reduce manufacturing footprint:

- **Periodic counter-current chromatography (PCC):** Multiple Protein A columns operated in staggered cycles; as one column loads, another elutes. Allows continuous feed from the bioreactor into a capture step without large hold tanks. 3–4 columns running in rotation.
- **Simulated moving bed (SMB) chromatography:** Advanced multi-column continuous chromatography for better separation than single-column. Primarily used for small molecules but being explored for mAb charge variant separation.
- **Continuous viral inactivation:** The Protein A eluate flows through a coil reactor with defined residence time (replacing the batch hold step).

These approaches are being commercialized and adopted at some facilities. They require more complex process development and regulatory approval but can offer significant capacity advantages.

---

## Resin and Membrane Lifetime Studies

Every reusable material (chromatography resin, UF/DF membrane) must be validated for the number of cycles or campaigns it can undergo while maintaining performance.

**Resin lifetime study design:**
1. Define the maximum number of cycles to validate (e.g., 200 cycles of Protein A)
2. Run the full number of cycles at small scale with representative feed (spiked with virus inactivation surrogates if needed for cleaning validation)
3. At defined intervals (e.g., every 25 cycles), test: step yield, product pool quality (HCP, aggregates, Protein A leach), column efficiency (HETP, asymmetry)
4. Confirm that performance remains within acceptance criteria through the full validated lifetime

Resin replacement schedules in manufacturing are set based on these validated lifetimes. MSAT tracks cumulative cycles per column and triggers replacement before the validated limit is reached.
