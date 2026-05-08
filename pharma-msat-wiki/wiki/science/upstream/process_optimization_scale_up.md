# Process Optimization & Scale-Up (Upstream)

**Backlinks:** [upstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [upstream/seed_train_bioreactor.md](seed_train_bioreactor.md) | [upstream/cellular_metabolism.md](cellular_metabolism.md) | [tech_transfer/scale_up.md](../../../tech_transfer/scale_up.md) | [tech_transfer/process_characterization.md](../../../tech_transfer/process_characterization.md)

---

## The Goal of Upstream Optimization

Upstream process optimization has two simultaneous objectives:
1. **Maximize productivity** (titer × yield) within the production schedule
2. **Ensure product quality** within CQA specifications

These objectives are often in tension: conditions that maximize cell growth and titer (high glucose, 37°C, extended culture) can degrade product quality (more deamidation, more aggregation, altered glycosylation). The optimization program finds the operating space where both objectives are met.

---

## Design of Experiments (DoE) in Upstream Development

Sequential DoE is the structured methodology for upstream optimization. The stages:

### Stage 1: Screening (Identifying Significant Factors)

**Objective:** Identify which of many candidate process parameters significantly affect titer and CQAs.

**Design:** Fractional factorial (Plackett-Burman, or 2^(k-p) fractional factorial). Study a large number of parameters with a manageable number of experiments by confounding higher-order interactions.

**Typical upstream screening factors:** pH, temperature, DO, feed timing, feed volume, feed composition, seed density, inoculation density, shift timing.

**Output:** A ranked list of significant factors. Insignificant factors are fixed at convenient values for the rest of development.

### Stage 2: Response Surface Methodology (Characterization)

**Objective:** Understand the shape of the response surface — how titer and CQAs respond across the ranges of the significant parameters.

**Design:** Central composite design (CCD) or Box-Behnken. These designs include centerpoints and axial points, allowing fitting of quadratic response surface models.

**Output:** A mathematical model predicting titer and CQA values as functions of the key parameters. From this model, the optimal operating point and the design space (acceptable parameter ranges) can be derived.

### Stage 3: Worst-Case Confirmation

Run experiments at the edges of the proposed PAR (Proven Acceptable Range) to confirm that product quality is still acceptable there. This is the regulatory confirmation that the design space is correctly defined.

---

## High-Throughput Screening Tools

### ambr15 and ambr250

The ambr (Advanced Micro Bioreactor) systems provide miniaturized, automated bioreactors at 15 mL and 250 mL scale with full pH, DO, and temperature control. 24–48 reactors can be run in parallel.

Advantages:
- Statistical power: run many conditions simultaneously, generate DoE data efficiently
- Automation: reduces operator variability
- Small volume: minimal cell bank usage during early development

The ambr system is the dominant tool for upstream process development in modern biopharma. Scale-down qualification (showing that ambr mimics pilot or production bioreactor behavior) is a key process development deliverable.

### Scale-Down Model Qualification

For regulatory submissions, process characterization experiments are run at scale-down. Regulators expect evidence that the scale-down model accurately predicts commercial-scale behavior. Qualification involves:
- Running parallel experiments at scale-down and at commercial (or pilot) scale under identical conditions
- Comparing titer, CQAs, metabolite profiles, and growth kinetics
- Statistical analysis: are scale-down results within the range of commercial-scale variability?

### Perfusion Screening

For perfusion processes, the ambr15 with perfusion capability (hollow fiber integration) or AMBR250 with ATF can screen perfusion conditions (perfusion rate, cell bleed rate, VCD setpoint).

---

## Feed Development

The feed medium is often the biggest lever for upstream productivity optimization. Feed development involves:

1. **Cell-specific consumption rate (CSCR) measurement:** Determine how fast cells consume each amino acid, vitamin, and carbon source at relevant conditions. Measured by amino acid analysis of spent medium samples.

2. **Feed design:** Formulate a feed that replenishes nutrients at rates matching consumption. Amino acid ratios in the feed should match consumption ratios; otherwise some amino acids accumulate (potentially toxic or quality-affecting) while others become limiting.

3. **Feed concentration optimization:** Higher concentration reduces the volume added (less dilution of the culture), but increases osmolality if not managed.

4. **Feed timing and frequency:** Bolus vs. continuous; daily vs. every 2 days; tied to glucose concentration or to time.

5. **Targeted feed supplements:** Uridine, galactose, MnSO4, copper to drive glycosylation targets. N-acetyl mannosamine (ManNAc) as sialic acid precursor.

---

## Scale-Up Principles

### Engineering Parameters for Scale-Up

When moving from ambr250 → 2 L → 50 L → 2000 L → 20,000 L, the key engineering parameters that change with scale:

**Power per unit volume (P/V):**
```
P/V ∝ (N³ × D⁵) / V
```
where N = agitation speed, D = impeller diameter, V = volume. Keeping P/V constant across scales is a common first approach to ensuring similar mixing and oxygen transfer.

**kLa (volumetric oxygen mass transfer coefficient):**
```
kLa ∝ (P/V)^0.4 × (vvm)^0.5
```
where vvm = gas volumetric flow per volume. Must be sufficient to maintain DO setpoint at peak oxygen demand.

**Mixing time (θmix):**
```
θmix ∝ (V / (N × D³))
```
Mixing time increases dramatically with scale. Gradients in pH, DO, and nutrients become significant at large scale. Gradient effects can change cell physiology and product quality.

**Tip speed:**
```
vtip = π × N × D
```
Tip speed is a proxy for shear at the impeller. If shear-induced cell damage is a concern, keeping tip speed constant (rather than P/V) is the appropriate scale-up criterion.

**Bubble-related shear:**
At large scale, the main source of cell damage is bubble bursting at the culture surface (coalescence and rupture of sparge bubbles). Polysorbate 80 (or other surfactants) in the medium is a key protective agent. Microsparging (smaller bubbles) reduces bubble size but increases CO2 stripping efficiency.

### Scale-Up Failure Modes

| Issue at scale | Root cause | MSAT response |
|---|---|---|
| Lower titer than at small scale | Poor mixing → nutrient gradients, glucose depletion zones | Review mixing time, improve feed distribution |
| Different glycan profile | CO2 accumulation (pH effect), O2 difference, temperature gradients | Adjust gas sparging, review pH control |
| Higher aggregation | Increased shear (agitation or sparging) | Reduce agitation, change sparger design |
| Slower growth | Inoculation density, seed train differences | Investigate N-1 bioreactor performance |
| Variable batch-to-batch | Raw material variability, operator differences | Tighten IPC ranges, raw material qualification |

---

## Yield Analysis and Mass Balance

MSAT tracks yield at each upstream step to understand overall process efficiency:

```
Overall upstream yield = Titer (g/L) × Production bioreactor volume (L) × Harvest yield fraction
```

The harvest yield fraction accounts for product lost during centrifugation and filtration (product adsorption to filter media, volume left in vessel, etc.). A well-optimized upstream harvest typically recovers 90–95% of the bioreactor titer.

Mass balance is a tool for deviation investigation: if yield is lower than expected, systematic checking of each step (bioreactor titer, centrate titer, filtrate titer) localizes where the loss occurred.
