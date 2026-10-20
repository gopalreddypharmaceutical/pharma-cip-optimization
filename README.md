# Clean-in-Place (CIP) Valve Sequence Optimizer using 8D Method

## 📌 Project Context & Overview
This repository details a formal, data-driven optimization package that leverages the structured **8D (Eight Disciplines) Root-Cause Analysis** framework. 

It documents the engineering investigation, diagnostic testing, and permanent logic corrections deployed on an automated pharmaceutical process system to resolve erratic cycle times. By troubleshooting sub-optimal valve pulsing sequences and slow drain-cycle timers, the project demonstrates a verified **18% reduction in total batch turnaround times** across critical production assets while maintaining absolute GxP sterile boundary requirements and validation criteria.

---

## 🏗️ Diagnostic Analysis & Engineering Correction
The optimization framework follows standard engineering problem-solving and automated timing path re-engineering (Purdue Model Level 1 Optimization):

```text
[LEGACY TIMING CONSTRAINT]
Phase 1: Pre-Wash Rinse Loop (10 Min) ──► Phase 2: Valve Pulsing Delay (45s Stall) ──► Phase 3: Drain Lag
                                                        ▲
                                             [Root Cause: Pump Cavitation]

[OPTIMIZED CYCLE MAPPING]
Phase 1: Pre-Wash Rinse Loop (10 Min) ──► Phase 2: Synchronized Scavenge Link ─────► Phase 3: Immediate Drain
```

### Technical Root Cause Resolving:
* **The Diagnostic Discovery:** Time-series time data mapping revealed that a scavenging return pump was running dry for up to 45 seconds during sequence transitions due to linear, un-interlocked timer blocks. This led to pipeline backpressure stalls.
* **The Permanent Logic Fix:** Rewrote the PLC ladder logic routines to replace fixed timers with **Dynamic Conductivity Interlocks**. Return routing and drain valves now pulse based on fluid boundaries, maximizing volumetric throughput.

---

## 📁 Repository Directory Structure

```text
📁 pharma-cip-optimization
├── 📁 docs
│   ├── 📝 Project4_CIP_8D_Optimization_Report.md     <- D1-D8 formal engineering report
│   └── 📊 Project4_CIP_Optimized_Timing_Schedule.csv <- Before/after timing, frequency, & savings matrices
└── 📄 README.md                                      <- Main portfolio description & document index
```

---

## 📑 Core Documentation Breakdown

### 1. 8D Engineering Optimization Report
Located at [`docs/Project4_CIP_8D_Optimization_Report.md`](./docs/Project4_CIP_8D_Optimization_Report.md), this comprehensive investigation file traces the project from team formation (D1) and containment (D3) up to permanent correction programming (D5-D6) and corporate SOP standardization (D7).

### 2. Before/After Valve Timing Schedule
Located at [`docs/Project4_CIP_Optimized_Timing_Schedule.csv`](./docs/Project4_CIP_Optimized_Timing_Schedule.csv), this data grid itemizes legacy vs. optimized execution parameters across all cleaning phases, detailing pump speeds, frequency thresholds, and specific process cycle efficiency gains.

