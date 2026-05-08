# Chromatography Methods for mAb Purification

**Backlinks:** [downstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [downstream/chromatography_principles.md](chromatography_principles.md) | [downstream/viral_clearance.md](viral_clearance.md) | [protein_structure/protein_charge.md](../../protein_structure/protein_charge.md)

---

## Protein A Affinity Chromatography (Capture Step)

### What It Is

Protein A is a bacterial surface protein from *Staphylococcus aureus* that binds with high affinity (Kd ~10 nM) to the Fc region of IgG antibodies. Recombinant Protein A ligands are immobilized on beaded agarose resins (MabSelect, MabSelect SuRe, MabSelect PrismA, Amsphere A3, etc.) to create a highly selective affinity resin.

### Why It Is the Dominant Capture Step

A single Protein A chromatography step typically achieves:
- 99.9% or higher removal of non-IgG proteins
- 100-fold or greater reduction in HCP
- Significant DNA reduction (not complete — DNA does not bind)
- Significant aggregate reduction (partial — some aggregates have accessible Fc regions and bind)

This extraordinary selectivity means that after one Protein A step, the product is already at >95% purity. The entire remainder of the downstream train is cleaning up the last 1–5% of impurities.

### Protein A Step Operation

**Loading:** Clarified harvest is loaded at neutral pH (7.0–7.5). mAb binds via Fc; most impurities flow through. Load density: 20–40 g mAb per L resin.

**Wash:** A wash buffer removes non-specifically bound impurities. Some processes use a high-salt intermediate wash (500–1000 mM NaCl) to disrupt electrostatic interactions with HCPs.

**Elution:** pH is dropped to ~3.5–3.8 using citrate or acetate buffer. The low pH protonates histidine residues in the Fc binding interface, disrupting the Protein A–Fc interaction and releasing the mAb. Eluate pH is immediately adjusted (neutralized) to ~5.0–6.0 to avoid product damage.

**Key CPPs:**
- Elution pH (lower pH → more complete elution but more aggregation risk and deamidation)
- Elution conductivity
- Load density (too high → poor binding, breakthrough)
- Load conductivity (high salt can interfere with binding)

### Protein A Resin Lifetime

Protein A resins are expensive (~$10,000/L or more). They are designed for reuse over 100–200 cycles per column lifetime. The resin must be validated for the maximum number of cycles it can undergo while maintaining performance (yield, HCP clearance, Protein A ligand leaching levels). This is a resin lifetime study.

Protein A ligand leaches into the product pool during elution. Leached Protein A is immunogenic and is a controlled process-related impurity. Downstream steps (especially low-pH viral inactivation hold) further reduce leached Protein A. Final drug substance has a specification (typically <10–50 ppm leached Protein A).

### Limitations of Protein A

- Cannot separate mAb charge variants (all charge variants have intact Fc regions)
- Cannot remove aggregates whose Protein A binding sites are occluded
- Cannot separate product-related impurities (fragments with intact Fc region bind; Fab fragments and Fc fragments elute abnormally)
- Cannot completely remove HCPs — some CHO HCPs non-specifically adsorb to the resin or to the product

---

## Low-pH Viral Inactivation

This is not a chromatography step, but it falls in the same position in the platform. See [downstream/viral_clearance.md](viral_clearance.md) for full treatment. Briefly: the Protein A eluate is held at pH 3.3–3.7 for ≥30–60 minutes to inactivate enveloped viruses. The pool is then neutralized before proceeding.

---

## Cation Exchange Chromatography (CEX) — Intermediate Purification

### Purpose

CEX is the primary polishing step after Protein A and viral inactivation. It:
- Removes residual HCPs not cleared by Protein A
- Removes residual DNA
- Clears aggregates (aggregates bind more tightly than monomers to CEX at most operating conditions, due to multivalent binding)
- Separates charge variants (the main peak, acidic variants, and basic variants have different affinities for CEX)

### Mode of Operation

Most mAb CEX steps run in **bind-and-elute** mode:
- Load at a pH that places the mAb above the binding threshold for the CEX resin (typically pH 4.5–5.5, below the mAb pI of 7–9)
- Impurities with lower pI (HCPs, DNA) flow through at this pH
- Elute the mAb with a salt gradient or step elution, which disrupts the ionic interaction

Alternatively, **flow-through CEX** mode is sometimes used: adjust conditions so the mAb flows through while specific impurities bind.

### CEX and Charge Variant Control

Because CEX separates by charge, it directly shapes the charge variant profile of the drug substance. By adjusting the elution gradient slope, pH, or conductivity:
- A shallower gradient → better resolution between main peak and variants → higher main peak %, lower overall yield
- A steeper gradient → worse resolution, higher yield, but includes more variants

Process characterization for CEX must include charge variant profile as a response alongside yield and HCP clearance. The window between acceptable purity (% main peak) and acceptable yield defines the operating space.

### Common CEX Resins

Capto S, Capto SP ImpRes, SP Sepharose FF, SP Sepharose HP, Fractogel SO3, Nuvia S. The choice depends on protein-specific binding properties, particle size (affects resolution vs. productivity), and pressure characteristics.

---

## Anion Exchange Chromatography (AEX) — Polishing

### Purpose

AEX is typically operated in **flow-through mode** for mAb purification. The mAb has a high pI (7–9) and at pH 7–8 is weakly to non-charged, while:
- DNA (highly negatively charged) binds strongly
- Many HCPs (pI <7) bind
- Endotoxin (LPS, negatively charged) binds

The mAb flows through, while these impurities are captured by the positively charged AEX resin. This is a very efficient clearance step for DNA and HCPs that escaped Protein A and CEX.

### Mode of Operation

Load the neutralized CEX pool onto the AEX column pre-equilibrated at pH 7–8 with low ionic strength. Collect the flow-through containing the mAb. Impurities remain bound. Strip and sanitize between cycles.

**Key CPPs:**
- Load pH (must be in range where mAb does not bind)
- Load conductivity (low conductivity → better binding of impurities, but also risk of mAb binding if conditions are not well controlled)
- Load density (must not overload the impurity binding capacity)

### Common AEX Resins

Q Sepharose FF, Capto Q, Capto DEAE, Mustang Q (membrane adsorber — useful at very large scales due to low pressure drop and single-use option).

---

## Hydrophobic Interaction Chromatography (HIC)

HIC is used less frequently in the standard platform but is valuable when:
- Aggregates cannot be sufficiently removed by CEX
- Specific product-related impurities (e.g., misfolded species) have different hydrophobicity than the main product

**Mode:** Bind-and-elute. Load at high salt (promotes hydrophobic interactions); elute by decreasing salt (reduces hydrophobic interactions). Aggregates, misfolded species, and some HCPs bind more tightly than the monomeric mAb under typical conditions.

**Key risk:** HIC at high salt concentrations can cause aggregation of some molecules during the loading step. Selection of appropriate operating conditions requires careful characterization.

---

## Mixed-Mode Chromatography

Examples: Capto adhere (phenyl + anion exchange), MEP HyperCel (mercapto-ethyl-pyridine — hydrophobic at high pH, reverse mode at low pH). Used when standard modes do not achieve required clearance.

---

## The Full DSP Train: Clearance Summary

| Step | HCP | DNA | Aggregates | Protein A | Viruses |
|---|---|---|---|---|---|
| Protein A (capture) | High | Moderate | Moderate | — | Moderate (enveloped) |
| Low-pH inactivation | None | None | None | Partial | Complete (enveloped) |
| CEX (bind-elute) | High | High | High | High | Some |
| AEX (flow-through) | High | Very High | Low | None | Some |
| Viral filtration | None | None | None | None | Complete (non-enveloped) |

Each step provides a "log reduction factor" (LRF) for each impurity class. The cumulative clearance across all steps must meet specifications. This is demonstrated in process characterization and validation studies.
