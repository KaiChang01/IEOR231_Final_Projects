# Scale-Up

**Backlinks:** [_index.md](../_index.md) | [tech_transfer/overview.md](overview.md)  
**Related:** [tech_transfer/process_characterization.md](process_characterization.md) | [manufacturing/unit_operations.md](../manufacturing/unit_operations.md)

---

## Definition

Scale-up is the process of transferring a manufacturing process from smaller-scale equipment to larger commercial-scale equipment while maintaining product quality. It is almost always a component of tech transfer, but it is a distinct technical challenge.

The reason scale-up is hard is that many physical phenomena do not scale linearly with batch size. A process that works at 10L can fail at 1000L not because anyone made a mistake, but because the physics changed.

---

## Why Processes Don't Simply Scale Linearly

When you increase batch size, the geometry of the system changes. The key dimensionless parameters that govern physical processes — mixing, heat transfer, mass transfer — often behave differently at different scales.

**Mixing**  
In a larger vessel, achieving the same degree of mixing requires more energy per unit volume. Impeller tip speed, power-per-unit-volume, and mixing time all behave differently. A suspension that stays homogeneous in a 10L tank with a given agitator speed may not stay homogeneous in a 1000L tank at the same shaft RPM.

**Heat Transfer**  
As volume scales cubically but surface area scales only quadratically, the surface-area-to-volume ratio decreases at larger scale. This means heating and cooling happen more slowly in large vessels. Processes that are temperature-sensitive (reaction kinetics, precipitation, crystallization) can behave very differently.

**Mass Transfer**  
In bioreactor processes (cell culture, fermentation), oxygen transfer from gas to liquid is critical. Larger bioreactors have worse oxygen transfer characteristics unless specifically engineered to compensate. This affects cell growth kinetics and ultimately product yield and quality.

**Shear**  
Agitation at large scale can generate localized high-shear zones that don't exist at small scale. This matters for shear-sensitive materials — biologics molecules, fragile particles, cells.

---

## Scale-Up Strategies

**Dimensional Analysis and Similarity**  
The classical engineering approach: identify the governing dimensionless numbers (Reynolds number, power number, Nusselt number, etc.) and design the large-scale process to match the small-scale process in those dimensionless parameters.

Practically, it's rare to achieve full similarity — there are usually too many competing constraints. The goal is to identify which dimensionless parameters are most critical for product quality and prioritize those.

**Empirical Bracketing**  
Run small-scale experiments that bracket the expected large-scale operating conditions. For example, if mixing at large scale is predicted to be less efficient, run small-scale experiments at lower agitation to simulate this, and confirm product quality is maintained.

**Scale-Down Models**  
Develop a validated small-scale model of the large-scale process that can be used for ongoing process development without the cost and logistics of running at full scale. Scale-down models are especially important for biologics manufacturing, where bioreactor runs are expensive and long.

A good scale-down model can:
- Screen process parameter ranges inexpensively
- Investigate deviations by replicating conditions at small scale
- Support regulatory submissions as a platform for future process changes

---

## Scale-Up Risks by Product Type

### Small Molecule / Solid Dosage (tablets, capsules)

Key scale-up challenges:
- **Granulation** — Wet granulation endpoint and granule properties change with scale; the relationship between impeller speed, chopper speed, and liquid addition rate is non-linear
- **Blending** — Blend uniformity and segregation behavior depend on mixing dynamics that differ at scale
- **Compression** — Tablet press speed and compression force interact with granule properties; scale-up here is relatively well understood

### Sterile / Injectable (small molecule)

Key scale-up challenges:
- **Filtration** — Filter sizing scales with area; fouling behavior can differ
- **Fill speed** — High-speed filling can introduce particulates or affect vial integrity
- **Lyophilization** — Lyophilizer performance is highly equipment-specific; cycle conditions (shelf temperature ramp rates, chamber pressure) require re-optimization at each piece of equipment

### Biologics (monoclonal antibodies, proteins, vaccines)

Key scale-up challenges:
- **Cell culture / fermentation** — Bioreactor scale-up is the most technically demanding area in pharma manufacturing; pO2, pH, temperature, and mixing all interact with cell growth and protein expression
- **Purification (downstream processing)** — Chromatography column sizing, buffer volumes, and flow rates scale with column volume; binding capacity and resolution must be validated at scale
- **Viral inactivation and filtration** — Regulatory requirements for viral safety must be maintained at scale

---

## Scale-Up Documentation

Every scale-up should be supported by:

1. **Scale-up rationale** — A scientific document explaining the scale-up approach: which parameters were held constant, which were scaled, and why
2. **Prediction vs. actual comparison** — After the first large-scale runs, compare actual process performance to predictions. Deviations from prediction are learning opportunities, not necessarily failures.
3. **Updated process characterization** — If scale changes alter the process behavior, the characterization data may need to be updated to reflect large-scale conditions

See: [tech_transfer/process_characterization.md](process_characterization.md)
