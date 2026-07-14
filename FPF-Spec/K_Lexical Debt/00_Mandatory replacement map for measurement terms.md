---
type: fpf-knowledge-page
context:
  - FPF
page_type: fpf-knowledge-page
mode: canonical-generated
title: Mandatory replacement map for measurement terms
part: "[[FPF - Part K - Lexical Debt]]"
parents:
  - "[[FPF - Part K - Lexical Debt]]"
source_file: FPF-Spec.md.breaks.my.obsidian.bak
source_lines:
  - 85814
  - 85827
status: generated
generated_on: 2026-06-15
generated: true
---



> **Rule:** In all **normative** content (specifications, data schemas, etc.), the deprecated terms **“axis”** and **“dimension”** (and their plural or compound forms) **MUST NOT** be used to denote a measurable aspect. Use **Characteristic** in the Tech register instead. Other colloquial terms should be mapped to canonical terms as listed below. In **Plain** narrative, deprecated aliases may appear _only on first use_ and only if paired with their canonical equivalent for clarity.

| Deprecated term (context) | **Replace with** (Tech register) | Plain register allowance | Canonical Reference |
| --- | --- | --- | --- |
| axis (of measurement); dimension (of a system or quality) | **(disallowed in Core prose)** → use **Characteristic** | No parenthetical allowance in Core; use **Characteristic**, **Measure**, or **Coordinate** only | [[00_A.17 - Canonical “Characteristic” (A.CHR-NORM)]] (CHR-NORM) |
| point (on an axis); data point | **Coordinate** (on a Scale) | “point” _(in explanations only, e.g. “a point on the scale”)_ | [[00_A.18 - Minimal CSLC in Kernel (Characteristic ⟷ Scale ⟷ Level ⟷ Coordinate) (A.CSLC-KERNEL)]] (CSLC-KERNEL) |
| metric value; raw score | **Coordinate** (or **Value**) | “value” _(acceptable in plain usage when context is clear, but formally it’s a Coordinate tied to a Characteristic)_ | [[00_A.18 - Minimal CSLC in Kernel (Characteristic ⟷ Scale ⟷ Level ⟷ Coordinate) (A.CSLC-KERNEL)]], [[00_C.16 - Measurement & Metrics Characterization (MM-CHR)]] |
| score (composite or normalized) | **Score** (produced via a **ScoringMethod**) | “score” _(if needed in narrative, ensure it’s explained as a result of a defined ScoringMethod)_ | A.17/A.18 (ScoringMethod/Score) |
| unit dimension; unit axis | **Unit** (of a Scale) | “unit” _(plain usage okay)_ | [[00_A.18 - Minimal CSLC in Kernel (Characteristic ⟷ Scale ⟷ Level ⟷ Coordinate) (A.CSLC-KERNEL)]] (Scale/Unit) |
| metric (as a noun) | **Avoid in Tech and as primitive** → use **`U.DHCMethodRef` / `U.Measure` / Score** | “metric” _(Plain only on first use, with pointer to canonical terms)_ | [[00_C.16 - Measurement & Metrics Characterization (MM-CHR)]] § 5.1 (L5), [[00_A.18 - Minimal CSLC in Kernel (Characteristic ⟷ Scale ⟷ Level ⟷ Coordinate) (A.CSLC-KERNEL)]] |
