# Seed Train & Production Bioreactor Development

**Backlinks:** [upstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [upstream/cellular_metabolism.md](cellular_metabolism.md) | [upstream/harvest.md](harvest.md) | [upstream/process_optimization_scale_up.md](process_optimization_scale_up.md)

---

## The Seed Train

The seed train is the series of expansion steps that takes cells from a single thawed vial of the working cell bank (WCB) to the inoculation volume required for the production bioreactor. It is the "warm-up" for the actual production run.

### Why the Seed Train Matters

The production bioreactor might contain 20,000 L of culture. A WCB vial contains ~1 mL at ~10–30 × 10⁶ viable cells/mL. To fill the production bioreactor at a target inoculation density of ~0.3–0.5 × 10⁶ cells/mL requires ~6,000–10,000 L of seed culture — meaning the cells need to expand by a factor of ~10⁶ from the vial. This happens through 8–12 doublings across 5–8 vessel stages.

The seed train affects:
- **Consistency of the production bioreactor inoculation:** If cells arrive at N-1 in a different metabolic or growth state, the production run will behave differently. Poor seed train performance is a common source of production bioreactor variability.
- **Cell age at the start of production:** Total cell doublings from the MCB to the start of production (plus the production run itself) must be within the validated cell age limit.

### Typical Seed Train Stages

```
WCB vial thaw (1 mL)
    ↓  shake flask (~125 mL)
    ↓  shake flask (~500 mL)
    ↓  Rocking bioreactor or spinner flask (~3–10 L)
    ↓  Seed bioreactor (50–250 L)     ← N-2
    ↓  Seed bioreactor (500–2000 L)  ← N-1 (inoculation train bioreactor)
    ↓  Production bioreactor (2,000–20,000 L) ← N
```

The nomenclature counts backward from the production step: N is production, N-1 is the last seed stage, N-2 is the stage before that.

### Seed Train Parameters and Controls

| Parameter | Typical control point | Rationale |
|---|---|---|
| Inoculation density | 0.2–0.5 × 10⁶ cells/mL | Too low → long lag phase; too high → hits stationary phase too early |
| Temperature | 36–37°C | Standard mammalian culture |
| pH | 6.9–7.1 | Physiological range; tight control not as critical as in production |
| Dissolved oxygen | 20–50% | Adequate for exponential growth |
| Duration / passage criteria | 3–4 days, or at specific VCD | Ensures cells are in mid-log phase at passage |
| Passage ratio (split ratio) | 5–10x | Determines number of doublings per passage |

### Critical Seed Train Attributes

At each stage, the cells are assessed before passaging or inoculating:
- **Viability:** Must exceed a minimum (typically ≥90% at seed stages)
- **VCD:** Within expected range for stage
- **Sterility / mycoplasma:** Checked at specific points
- **Absence of contamination** (pH, color, turbidity as rapid indicators)

Seed train failure (contamination, low viability, slow growth) leads to campaign cancellation and loss of the batch — a significant cost. Robust seed train processes with ample in-process controls are a manufacturing priority.

---

## Production Bioreactor

### Bioreactor Design and Key Equipment

The production bioreactor is a stirred tank reactor (STR). Key components:

- **Vessel:** Stainless steel (traditional) or single-use (disposable bioreactor bags, up to ~2000 L). Single-use eliminates cleaning validation and sterilization requirements, reducing turnaround time and contamination risk.
- **Agitation system:** Impeller (stirrer blade). Provides mixing and O2 mass transfer. The type (Rushton, pitched blade, marine impeller), size, and speed affect shear stress and mixing efficiency.
- **Sparger:** Ring sparger or open pipe at the bottom of the vessel through which air and O2 are bubbled for oxygenation and CO2 removal. Bubble size and flow rate affect mass transfer coefficient (kLa) and foam generation.
- **pH control:** pH is monitored with an electrochemical probe and controlled by CO2 sparging (acidify) and base addition (NaOH or Na2CO3; alkalize). Acid and base reservoirs are connected via peristaltic pumps.
- **DO control:** Measured with a dissolved oxygen probe; controlled by cascade: first increase agitation, then increase air flow, then blend O2 into the sparge gas.
- **Temperature control:** Water jacket or internal coils; precise to ±0.1°C.
- **Sensors:** pH, DO, temperature are standard. Advanced bioreactors include on-line capacitance (cell density proxy), Raman spectroscopy (glucose, lactate), off-gas analysis (O2 uptake, CO2 evolution).

### Key Bioreactor Process Parameters (CPPs)

| Parameter | Typical range | Key CQAs affected |
|---|---|---|
| pH | 6.8–7.2 | Glycosylation (sialylation), charge variants |
| DO | 20–50% air saturation | Glycosylation (high mannose, Gal), oxidation |
| Temperature | 36.5–37°C (growth); 31–34°C (production, post-shift) | qp, glycosylation |
| dCO2 | <150 mmHg | Cell growth, pH effects |
| Agitation (tip speed / P/V) | Product-specific | Shear-induced aggregation |
| Feed addition (rate, composition) | Product-specific | Glycosylation, metabolite levels, titer |
| Dissolved O2 step-change / O2 overlay | Process-specific | Oxidation of methionine |

### Inoculation

The N-1 bioreactor culture is transferred to the production bioreactor at a defined inoculation density (typically 0.3–0.6 × 10⁶ cells/mL). The production vessel is pre-filled with basal medium; the N-1 culture is added.

### Production Culture Execution

After inoculation, the process follows a defined sequence:
1. Growth phase at 37°C (approximately days 0–4)
2. Temperature shift (if used) to 31–34°C at a trigger point (VCD, day of culture)
3. Fed-batch feeds according to schedule
4. Daily or twice-daily sampling for cell density, viability, glucose, lactate, glutamine, ammonia
5. At-line measurements: some are automated with auto-samplers and analyzers (Nova Flex, Cedex Bio HT)

### Scale-Up Principles

Moving from small-scale (development) to commercial scale is one of MSAT's core challenges. The key engineering parameters that must be maintained or deliberately adjusted at scale:

- **kLa (oxygen mass transfer coefficient):** Scales with agitation power/volume (P/V) and sparger gas flow rate. Must be sufficient to maintain DO setpoint as cell density and oxygen demand increase.
- **Mixing time:** At large scale, mixing time increases. Poor mixing leads to pH and nutrient gradients — cells experience different conditions depending on their location in the vessel.
- **CO2 removal:** More challenging at large scale due to larger volume and longer bubble residence time. CO2 can accumulate if sparging is insufficient.
- **Shear stress:** Higher agitation at scale can increase hydrodynamic shear. Bubble bursting at the liquid surface (from sparger or overlay gas) is the primary source of cell damage.

Scale-up is typically guided by maintaining constant **P/V** (power per unit volume), constant **tip speed** (impeller peripheral velocity), or empirical matching of oxygen uptake rate (OUR). The correct criterion is product-specific and must be demonstrated experimentally. See: [upstream/process_optimization_scale_up.md](process_optimization_scale_up.md)
