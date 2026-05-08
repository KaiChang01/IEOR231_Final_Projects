# Scheduling Tools and Frameworks

**Backlinks:** [_index.md](../_index.md) | [scheduling/overview.md](overview.md) | [scheduling/capacity_modeling.md](capacity_modeling.md)  
**Related:** [scheduling/campaign_planning.md](campaign_planning.md)

---

## Overview

Production scheduling in pharma uses a hierarchy of tools, from enterprise-wide planning systems down to shop-floor Gantt charts. MSAT engineers are consumers and contributors to these systems rather than their primary operators, but understanding what each tool does — and what data it needs from MSAT — is important.

---

## Tier 1: Enterprise Resource Planning (ERP)

**What it is**  
The company-wide business system that manages orders, inventory, procurement, production orders, and financial data. SAP is the dominant ERP in large pharma; Oracle, Microsoft Dynamics, and others are also used.

**What it does for scheduling**  
- Maintains the Master Production Schedule at a high level (which batches, in which period, at which site)
- Generates production orders and materials requirements (MRP — Materials Requirements Planning)
- Tracks batch status, inventory, and disposition

**MSAT interaction with ERP**  
MSAT's process data (cycle times, yields, bill of materials) is loaded into the ERP as the basis for production order templates. When MSAT changes a process (e.g., a scale-up that changes batch size or cycle time), the ERP master data must be updated accordingly.

---

## Tier 2: Advanced Planning and Scheduling (APS)

**What it is**  
A specialized planning system that sits alongside (or integrates with) ERP and provides more sophisticated scheduling optimization capabilities. Common examples: SAP IBP (Integrated Business Planning), Kinaxis, o9 Solutions. Smaller pharma companies may use purpose-built pharma scheduling tools like Aspen Batch Plus, SchedulePro (PSI), or custom tools.

**What it does for scheduling**  
- Takes demand requirements from ERP and generates a feasible production schedule respecting resource constraints
- Optimizes the schedule against objectives (maximize throughput, minimize makespan, minimize changeover, meet due dates)
- Provides "what-if" scenario analysis — what happens if a batch fails? what if a bioreactor goes down?
- Maintains constraint data: equipment capacities, cleaning constraints, sequence-dependent changeover times

**MSAT interaction with APS**  
MSAT provides the process constraint data that the APS system enforces:
- Step cycle times and valid ranges
- Equipment requirements per step
- Sequence-dependent changeover matrices (how long to clean between products)
- Hold time limits
- Minimum and maximum campaign sizes

When this data is wrong or outdated, the APS generates schedules that are infeasible in practice — a common source of frustration between Planning and Manufacturing.

---

## Tier 3: Shop Floor Scheduling and Execution

**What it is**  
The detailed, day-to-day schedule for a specific manufacturing area, updated in near-real-time as actual production events occur. Often managed as a Gantt chart in a spreadsheet, whiteboard, or Manufacturing Execution System (MES).

**Manufacturing Execution System (MES)**  
Software that manages and records manufacturing execution — Electronic Batch Records (eBRs), equipment status, in-process testing, batch genealogy. Examples: Veeva Vault MFG, Emerson (Syncade), Rockwell PharmaSuite, Siemens SIMATIC IT.

MES provides real-time visibility into batch progress, which feeds back into the scheduling system — if a batch is running late, the schedule needs to update.

**MSAT interaction with shop floor scheduling**  
MSAT is often consulted in real-time when schedule decisions involve process risk: "Can we hold this material for an extra 4 hours?" (hold time question), "Can we start the next step now even though the previous step result isn't back yet?" (in-process test hold question).

---

## The Gantt Chart

The Gantt chart is the universal visualization for production scheduling — a horizontal bar chart showing activities on a time axis.

```
                 Mon    Tue    Wed    Thu    Fri    Sat    Sun
Bioreactor 1:  [Batch A seed train                         ]
Bioreactor 2:        [Batch B production run               ]
Harvest Tank:              [Harvest A      ]
Capture Col.:                    [Capture A]
Storage Tank:                            [Hold    ]
Fill Line:                                      [Fill A    ]
```

In pharma, Gantt charts are used for:
- Visualizing a campaign schedule
- Identifying resource conflicts
- Communicating schedule to cross-functional stakeholders
- Tracking progress against plan

Microsoft Excel is commonly used for simple Gantt charts. Dedicated scheduling software generates Gantt views automatically.

---

## Frameworks: Theory of Constraints vs. Lean

Two production management frameworks are relevant to pharma scheduling:

**Theory of Constraints (TOC)**  
See: [scheduling/capacity_modeling.md](capacity_modeling.md). Focuses scheduling effort on the bottleneck. Particularly relevant when one step genuinely limits total throughput — which is often the case in biologics (the bioreactor is frequently the constraint).

**Lean Manufacturing**  
Focuses on eliminating waste in all forms: overproduction, waiting, transport, over-processing, inventory, motion, defects. In pharma, lean is applied to reduce cycle times, streamline changeovers (SMED — Single Minute Exchange of Die), and create visual management systems.

Lean is more culture-driven than TOC and requires deep engagement with Manufacturing Operations and operators. MSAT contributes by identifying and reducing the process-driven sources of waste: long cleaning times, yield variability, test-and-hold waiting time.

---

## Simulation Tools

For capacity planning and what-if analysis beyond what APS can do:

| Tool | Type | Pharma use |
|---|---|---|
| SuperPro Designer | Process simulation + scheduling | Widely used in biotech — batch scheduling, resource allocation, economic analysis |
| Aspen Batch Plus | Batch scheduling | Process simulation for scheduling optimization |
| Arena / Simul8 | Discrete Event Simulation (DES) | Stochastic capacity modeling, variance analysis |
| SimPy (Python) | DES in Python | Flexible custom simulation; used by quantitatively skilled engineers |
| Excel + VBA | Spreadsheet simulation | Quick-and-dirty capacity models; widely used despite limitations |

MSAT engineers who can build or contribute to simulation models are significantly more effective at making the business case for process improvements, because they can quantify the throughput impact of a process change.

---

## MSAT's Data Responsibilities for Scheduling Tools

The quality of any scheduling tool is only as good as the process data feeding it. MSAT is responsible for:

1. **Maintaining accurate cycle time data** — as processes are improved or as real-world experience accumulates, cycle times must be updated in the scheduling system
2. **Flagging process constraints** — hold times, sequence dependencies, minimum campaign sizes
3. **Reporting on process reliability** — failure rates, deviation frequencies, and their scheduling impact
4. **Scenario analysis support** — providing process data for what-if analyses: "what if we add a second chromatography column?"

Inaccurate data in a scheduling system is worse than no scheduling system — it gives false confidence in a plan that cannot be executed.
