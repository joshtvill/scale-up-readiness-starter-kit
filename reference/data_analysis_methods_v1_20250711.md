# Data Analysis Methods for Integrated Issue Troubleshooting

## Use Case
This reference document outlines generalized data analysis strategies used to investigate complex, integrated manufacturing issues. It is meant for process engineers, systems integration leads, and MSAT teams who need to localize root cause across equipment, materials, process parameters, and upstream dependencies.

These methods are abstracted from high-throughput semiconductor environments but are broadly applicable to biotech, medtech, or regulated manufacturing settings.

---

## Core Methods

### 1. **Signal Turn-On Analysis**
Use to identify when a defect, excursion, or yield issue began:
- Create time-ordered plots of relevant metrics (e.g., defect rate, viability, fill weight)
- Mark the first occurrence where values exceed control or spec limits
- Cross-reference with tool, lot, or recipe change logs

> **Goal:** Detect when a problem first emerged, narrowing the timeframe for root cause search

---

### 2. **Tool or Line-Level Correlation**
Used to isolate whether the issue is associated with a specific tool, equipment module, or process line:
- Group lots or batches by tool ID or station
- Plot failure metrics by tool to check for consistent outliers
- Use pivot tables or boxplots to compare distributions

> **Goal:** Identify high-leverage suspects for equipment-related issues

---

### 3. **Upstream Input or Material Lot Grouping**
Trace whether incoming material variability is driving the issue:
- Group lots by input raw material batch or supplier
- Analyze within-group vs across-group consistency
- Check for recurrences tied to specific component lots

> **Goal:** Flag potential supplier-related or incoming QC issues

---

### 4. **Spatial Distribution Mapping (if applicable)**
Check if issues have a location-dependent signal:
- For wafers: spatial defect maps, site-level plots
- For bioreactors or cartridges: port, region, or layer-based mapping
- Map symptom (e.g., viability drop, defect) against physical layout

> **Goal:** Differentiate uniform vs localized failure modes

---

### 5. **Parameter Drift and Stability Checks**
Identify whether critical parameters have drifted over time:
- Pull control parameter logs (e.g., pH, temp, speed, dose time)
- Plot over time or batch number
- Overlay against spec and trend lines

> **Goal:** Reveal gradual shifts that may not immediately trigger alarms but correlate with performance decline

---

### 6. **Interruption and Maintenance Correlation**
Determine if tool aborts, maintenance events, or interventions coincide with issue onset:
- Overlay issue trend against tool uptime, resets, or PM logs
- Investigate tool state before and after known interventions

> **Goal:** Expose mechanical or procedural precursors to symptom onset

---

### 7. **Commonality and Divergence Analysis**
Use when comparing affected vs unaffected lots:
- Build a table listing tools, materials, and operators involved
- Highlight factors *unique* to affected vs unaffected
- Use to eliminate shared factors and narrow candidates

> **Goal:** Systematically converge toward unique variables in failing cases

---

## When to Apply
Use these techniques:
- During early scoping of a newly emerged or trending issue
- As a pre-experiment phase to prioritize hypotheses
- To support discussions with QA, automation, or upstream suppliers

These are not exhaustive, but provide a reusable analytical scaffold for investigating integrated systems failures, especially where failure is ambiguous, intermittent, or multi-factorial.

---

## Related Assets
- `system_issue_investigation_tracker.xlsx`: for logging and tracking model-based troubleshooting
- `postmortem_summary_template.docx`: for summarizing issue and resolution

> These tools work together to move from signal detection → root cause → system learning.
