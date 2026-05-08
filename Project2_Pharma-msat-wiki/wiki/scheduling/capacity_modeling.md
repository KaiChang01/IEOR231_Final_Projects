# Capacity Modeling

**Backlinks:** [_index.md](../_index.md) | [scheduling/overview.md](overview.md) | [scheduling/campaign_planning.md](campaign_planning.md)  
**Related:** [scheduling/scheduling_tools.md](scheduling_tools.md) | [manufacturing/unit_operations.md](../manufacturing/unit_operations.md)

---

## What is Capacity Modeling?

Capacity modeling is the quantitative analysis of a manufacturing facility's ability to produce product. A capacity model answers questions like:

- How many batches per year can this facility produce?
- What is the maximum output if we run 24/7?
- Where is the bottleneck — which step or piece of equipment limits throughput?
- What happens to throughput if we add one more bioreactor?
- How much of our capacity is lost to cleaning, maintenance, and deviations?

For MSAT specifically, capacity modeling is the connection between process performance (cycle times, yields, failure rates) and business outcomes (supply reliability, cost). Improving a process parameter that doesn't affect a scheduling bottleneck has no impact on throughput; improving the bottleneck can unlock significant capacity.

---

## Key Capacity Concepts

**Design Capacity**  
Theoretical maximum output assuming 100% utilization, no downtime, no failures. A ceiling, not a realistic target.

**Effective Capacity (Available Capacity)**  
Design capacity minus planned downtime: scheduled maintenance, cleaning, equipment qualification, calibration, holidays. This is the realistic upper bound.

**Actual Throughput**  
Effective capacity minus unplanned losses: equipment failures, batch rejections, deviations, extended investigations. What actually comes out.

```
Design Capacity
    - Planned downtime (cleaning, maintenance, qualification)
    = Effective Capacity
    - Unplanned losses (failures, deviations, extended cycles)
    = Actual Throughput
```

The gap between Effective Capacity and Actual Throughput is the opportunity for process improvement.

---

## OEE (Overall Equipment Effectiveness)

OEE is the standard metric for quantifying manufacturing equipment efficiency. It is calculated as:

**OEE = Availability × Performance × Quality**

**Availability**  
% of planned production time that equipment is actually available (not in unplanned downtime or maintenance).  
Availability = (Planned time − Downtime) / Planned time

**Performance**  
% of available time that the process runs at its intended rate (vs. running slowly, stopping/starting, minor stoppages).  
Performance = (Actual output × Ideal cycle time) / Available time

**Quality**  
% of output that meets specification (not rejected or requiring rework).  
Quality = (Good units) / (Total units started)

A world-class OEE is typically considered ~85%. Pharmaceutical manufacturing often runs significantly below this due to:
- GMP-required cleaning and qualification (reduces availability)
- Fixed biological cycle times (limits performance improvement)
- Batch testing requirements (quality rejections can't always be recovered)

OEE analysis is useful for identifying which loss category dominates and where improvement effort should focus.

---

## Building a Capacity Model

A pharma facility capacity model is typically built as a spreadsheet or simulation model. The inputs:

**Process inputs (from MSAT)**

| Parameter | Description |
|---|---|
| Step cycle time | Duration of each unit operation per batch |
| Equipment requirements | Which equipment is needed for each step |
| Batch size | Volume or mass per batch |
| Yield per step | Expected output vs. input |
| Batch success rate | % of batches that pass without failure |
| Hold time constraints | Maximum time between steps |
| Cleaning cycle time | Time to clean between products or campaigns |

**Facility / resource inputs (from Engineering / Manufacturing)**

| Parameter | Description |
|---|---|
| Equipment count | How many bioreactors, fill lines, etc. are available |
| Equipment availability | Planned downtime schedules (maintenance, qualification) |
| Labor shifts | Available staffing hours per day / shift pattern |
| Utility constraints | Steam, water, air supply limits |

**Business inputs (from Supply Chain / Finance)**

| Parameter | Description |
|---|---|
| Demand forecast | Batches or kg needed per time period |
| Service level target | Acceptable % probability of meeting demand |
| Inventory targets | Safety stock levels |

---

## Bottleneck Analysis

The **bottleneck** is the step or resource with the highest utilization — the one that is most constraining to throughput. In any process, throughput is limited by the bottleneck. Adding capacity anywhere else doesn't increase total output.

**How to identify the bottleneck:**
1. Calculate the time each unit operation occupies per unit of output (cycle time / batch size)
2. Calculate available time per period for each piece of equipment
3. The equipment with the highest utilization (closest to 100%) is the bottleneck

**Theory of Constraints approach to bottleneck management:**
1. *Identify* the constraint
2. *Exploit* it — maximize throughput at the constraint by eliminating waste (reduce time the constraint is idle, in maintenance, or producing bad product)
3. *Subordinate* everything else to the constraint — other steps should feed and unload the constraint efficiently
4. *Elevate* the constraint — if exploitation isn't enough, invest in more capacity at the constraint
5. Repeat — once the constraint is elevated, the bottleneck will move somewhere else

---

## Simulation Modeling

Spreadsheet-based capacity models are useful for steady-state analysis but don't capture dynamic behavior — the interaction of random events (equipment failures, batch failures, variable cycle times) with scheduling decisions over time.

**Discrete Event Simulation (DES)** models the process as a sequence of events with probabilistic inputs. A DES model can:
- Capture the stochastic nature of pharma manufacturing (failures, variable cycle times)
- Analyze the impact of hold time violations under different schedule scenarios
- Evaluate capacity expansion options with realistic operational assumptions
- Run thousands of simulated scenarios to generate confidence intervals on throughput

Common DES tools in pharma: SuperPro Designer, Aspen Plus (batch), Arena, Simul8, custom Python/SimPy models.

MSAT provides the process data that populates these models; Industrial Engineering or Process Engineering teams (or specialized consultants) typically build them.

See: [scheduling/scheduling_tools.md](scheduling_tools.md)

---

## Capacity Analysis for Tech Transfer

When a product is being transferred to a new site, a capacity analysis is part of Phase 1 planning:

1. Does the receiving site have the equipment needed?
2. Does the receiving site have enough capacity to add this product alongside existing products?
3. What is the impact on the existing schedule if the new product is added?
4. Are there bottlenecks specific to the new product that need to be resolved before transfer?

The MSAT engineer on the receiving site is typically responsible for this analysis, often working with the site's Industrial Engineering or Manufacturing Planning group.
