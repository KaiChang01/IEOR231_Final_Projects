# Production Scheduling Overview

**Backlinks:** [_index.md](../_index.md) | [msat/roles_responsibilities.md](../msat/roles_responsibilities.md)  
**Related:** [scheduling/campaign_planning.md](campaign_planning.md) | [scheduling/capacity_modeling.md](capacity_modeling.md) | [manufacturing/overview.md](../manufacturing/overview.md)

---

## Why Production Scheduling in Pharma is Hard

Production scheduling is a universal manufacturing challenge, but pharmaceuticals have a distinct set of constraints that make it particularly complex:

**Long cycle times**  
A biologic drug substance batch takes 3–6 weeks from cell bank thaw to drug substance fill. A lyophilized injectable product takes 2–5 days for a single lyophilizer cycle. Scheduling errors made today have consequences measured in weeks or months.

**Regulatory constraints on the process**  
You cannot simply speed up or slow down a manufacturing step. Cycle times are often fixed by the biology (cell growth takes the time it takes), by validated parameters (lyophilization cycles are validated at specific ramp rates), or by regulatory filings. Flexibility is limited compared to most manufacturing industries.

**Cleaning and changeover**  
Multi-product facilities must clean equipment between products to prevent cross-contamination. Cleaning validation is GMP-required and time-consuming. Campaign sequencing must account for cleaning cycles and validated cleaning changeover times.

**Equipment availability and maintenance**  
GMP-required preventive maintenance, calibration, and equipment qualification activities remove equipment from production on defined schedules. These must be incorporated into the production schedule.

**Demand unpredictability**  
Clinical trial supply needs can change rapidly. Commercial demand can shift due to market factors, competitor products, or safety signals. The manufacturing plan must be responsive while maintaining supply continuity.

**Shelf life and expiry**  
Drug products have defined shelf lives. Scheduling must ensure that product doesn't expire before it reaches patients — and that batches are manufactured early enough to allow for release testing (which can take weeks) before the product is needed.

**Material supply lead times**  
Raw materials and components (API, excipients, primary packaging) have procurement lead times. A production schedule must be coordinated with procurement so materials are available when needed.

---

## The Planning Hierarchy

Production scheduling sits within a broader planning hierarchy:

```
Strategic Capacity Planning (3–5 years)
        ↓
Aggregate / S&OP Planning (12–18 months)
        ↓
Master Production Schedule (3–12 months)
        ↓
Detailed Production Scheduling (days to weeks)
        ↓
Execution (shop floor dispatch)
```

**MSAT's primary domain** is the middle two layers — providing process data that drives the Master Production Schedule and participating in detailed scheduling decisions when process expertise is needed.

Supply Chain / Planning owns the scheduling function. MSAT's role is not to run the schedule but to make the process information that underlies it as accurate and reliable as possible, and to improve process performance when scheduling constraints are driven by process inefficiencies.

---

## Scheduling Constraints in Pharma

Constraints fall into several categories:

| Constraint Type | Examples |
|---|---|
| Equipment / resource | Bioreactor is occupied; lyophilizer is in maintenance; fill line is running another product |
| Sequence-dependent | Product A must clean before Product B (one-way constraint); or sequencing two products requires a different (longer) cleaning validation |
| Time-dependent | Batch must move to next step within X hours; material hold time expires |
| Material availability | API not yet released from QC; primary packaging on back-order |
| Regulatory | Product must be tested and released before a country's customs deadline |
| Labor | Specialized operator required for a step; shift availability |

Constraint identification is a joint exercise between MSAT (process constraints), Manufacturing Operations (labor and equipment), Engineering (maintenance windows), and Supply Chain (material and demand).

---

## MSAT's Specific Role in Scheduling

**Process data provider**  
MSAT is the authoritative source for: step cycle times, equipment requirements per step, hold time limits (how long material can wait between steps), yield expectations, and process failure rates. All of these are inputs to the scheduling model.

**Bottleneck identification and resolution**  
When a process step is the scheduling bottleneck, MSAT is responsible for understanding whether the constraint can be improved — by reducing cycle time, improving yield, reducing failure rate, or qualifying additional equipment.

**Process deviation impact assessment**  
When a deviation occurs on the manufacturing floor, MSAT assesses whether the batch is recoverable (can it proceed? at what risk?) and how quickly. This real-time assessment directly impacts whether the schedule recovers or slips.

**Campaign sizing input**  
MSAT advises on the minimum and maximum campaign sizes from a process perspective: minimum number of batches to minimize changeover overhead; maximum number before process performance drift becomes a risk.

See: [scheduling/campaign_planning.md](campaign_planning.md)

---

## Key Scheduling Metrics

| Metric | Why it matters |
|---|---|
| Throughput (batches/year or kg/year) | Determines whether a facility can meet demand |
| Capacity utilization | % of available time the facility is producing; high utilization leaves no buffer for deviations |
| Schedule adherence | % of planned activities completed on time; chronic slippage indicates process or planning problems |
| Makespan | Total time to complete a set of batches; minimizing makespan is a scheduling objective |
| Cycle time | Time from start to release of a single batch; drives inventory levels and supply chain flexibility |
| OEE | Availability × Performance × Quality for a piece of equipment; the standard metric for equipment efficiency |
