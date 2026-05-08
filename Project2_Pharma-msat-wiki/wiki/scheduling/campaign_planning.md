# Campaign Planning

**Backlinks:** [_index.md](../_index.md) | [scheduling/overview.md](overview.md)  
**Related:** [scheduling/capacity_modeling.md](capacity_modeling.md) | [msat/roles_responsibilities.md](../msat/roles_responsibilities.md)

---

## What is a Campaign?

A campaign is a series of consecutive batches of the same product produced in the same equipment suite without a full equipment changeover. Running in campaigns is more efficient than switching between products every batch because:

- Cleaning and changeover only happens at the start and end of the campaign, not between every batch
- Operators develop proficiency on a product during the campaign — learning curve benefits
- Equipment stays in a qualified and setup state for the product throughout the campaign
- Material and component staging is done once at campaign start

The fundamental tension in campaign planning is **campaign length vs. supply flexibility**. Longer campaigns are more efficient per batch but tie up equipment for extended periods and require building inventory — which increases working capital and exposes supply to risk if a batch fails.

---

## Campaign Planning Decisions

**Campaign size (number of batches)**  
The number of batches per campaign must be large enough to justify the setup/teardown overhead but small enough to allow schedule flexibility and respond to demand changes.

Minimum campaign size considerations:
- Cleaning and changeover cost (time, labor, materials)
- Equipment setup time (purging, sterilization, set-up qualification)
- First-batch-of-campaign effects — some processes show lower yield or higher variability on the first batch after changeover; if this is consistent, the first batch may be treated as a qualification run

Maximum campaign size considerations:
- Demand — you don't want to build more inventory than you can sell before expiry
- Risk — if a deviation occurs mid-campaign, a long campaign means more affected batches
- Equipment wear — some equipment degrades with continuous use (e.g., chromatography resins have a finite lifetime measured in cycles)

**Campaign sequencing (what order to run products)**  
In multi-product facilities, the order of products within a schedule period matters because of cleaning constraints:

- *Dedicated equipment*: if equipment is single-product, sequencing matters less
- *Shared equipment with validated cleaning*: cleaning validation may specify which transitions are acceptable (e.g., Product A to Product B requires a 3-hour clean; Product B to Product A requires an 8-hour clean)
- *Potency/toxicity-driven sequencing*: a highly potent compound followed by a less potent one requires a more rigorous cleaning validation. Most facilities sequence from least to most potent to minimize cross-contamination risk.

**Campaign timing (when to start)**  
Driven by demand forecast, inventory position, and raw material availability. The campaign must start early enough that the product is released and delivered before the demand date, accounting for:
- Batch cycle time
- Release testing time (weeks for some products)
- Shipping lead time
- Safety stock requirements

---

## Multi-Product Facility Scheduling Example

A simplified example of campaign sequencing in a multi-product sterile fill-finish facility:

```
Week:  1    2    3    4    5    6    7    8    9    10   11   12
Line A: [  Product X  ] [Clean] [    Product Y    ] [Clean] [  Product X  ]
Line B: [   Product Z  ] [C]  [    Product W     ] [C]   [  Product Z  ]
```

Key constraints driving this schedule:
- Product X and Y cannot run simultaneously (shared component)
- Product W requires a 2-week cleaning validation cycle after Product Z (historical contamination risk)
- Product X demand peak in Week 12 — schedule is backplanned from that date

---

## The Role of Safety Stock

Pharmaceutical supply chains maintain **safety stock** — inventory held above and beyond what's needed to meet forecasted demand — to buffer against:

- Batch failures (a failed PPQ or commercial batch leaves a gap in supply)
- Longer-than-expected release testing
- Manufacturing deviations that delay a campaign
- Demand spikes

Safety stock levels are set by Supply Chain based on service level targets (typically 95–99% for critical medicines). For MSAT, the implication is: if your process has a high batch failure rate or frequent deviations, more safety stock is needed, which means more inventory capital and potentially more manufacturing capacity.

Improving process reliability — fewer deviations, higher first-pass yield, more predictable cycle times — directly reduces safety stock requirements and manufacturing costs. This is one of the clearest business cases for MSAT process improvement work.

---

## Freeze-Thaw and Hold Time Constraints

In biologics manufacturing, intermediate materials (e.g., clarified cell culture harvest, purified protein solution) often have defined **hold times** — the maximum duration material can be stored at a given condition before it must be processed. Hold times are validated and GMP-required.

Hold time constraints create scheduling dependencies:
- Material from Step A must enter Step B within X hours
- If the next equipment is unavailable (occupied, in maintenance), the material may expire
- Freeze-thaw operations can be used to extend hold times but add cycle time and require validated freeze/thaw processes

Hold times are among the most frequent sources of scheduling inflexibility in biologics manufacturing. MSAT can improve scheduling flexibility by extending validated hold times through stability studies.

---

## Demand-Driven vs. Constraint-Driven Planning

Two philosophies exist in pharmaceutical production planning:

**Demand-driven planning (MRP/MPS approach)**  
Start from the demand forecast, backplan to determine when each batch must start, and identify resource needs. Reveals capacity shortfalls and drives procurement. Standard approach.

**Constraint-driven planning (Theory of Constraints approach)**  
Identify the bottleneck resource (the constraint) and build the schedule around maximizing throughput at the constraint. Every other resource is scheduled to subordinate to the constraint. More flexible in practice for complex multi-product scheduling.

Most pharma facilities use a hybrid: demand drives the overall plan, but the detailed schedule is built constraint-first.

See: [scheduling/capacity_modeling.md](capacity_modeling.md), [scheduling/scheduling_tools.md](scheduling_tools.md)
