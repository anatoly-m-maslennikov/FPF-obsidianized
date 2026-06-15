---
type: "fpf-pattern"
context:
  - "FPF"
page_type: "fpf-pattern"
mode: "canonical-generated"
fpf_id: "C.22"
title: "Problem Typing & TaskSignature Assignment (Problem-CHR)"
part: "[[FPF - Part C — Kernel Extension Specifications]]"
parents:
  - "[[FPF - Part C — Kernel Extension Specifications]]"
source_file: "FPF-Spec.md"
source_lines:
  - 45325
  - 45539
status: "generated"
terms:
  - "U.DescriptorMap"
  - "U.Discipline"
  - "U.Kind"
generated_on: "2026-06-15"
generated: true
---


**Purpose.** Give FPF an **admissible, minimal, and portable** way to type a problem for downstream selector-facing use after the problem-side representation is stable enough for Principles-to-Work, eligibility, acceptance, or policy-governed choice. [[C.22.2 - ProblemCard@Context|C.22.2]]-selector-facing use carries the first problem-framing record for a messy signal; [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]-selector-facing use attaches the stabilized problem to CHR-grounded traits and a minimal `TaskSignature (S2)` record for downstream selector-facing use. The `TaskSignature` attachment is **Context-local**, evidence-relation-traceable, tri-state-aware, and bridge-visible. TaskSignature is *minimal* but sufficient for **eligibility**, **acceptance**, and **policy-governed** choice.

**Status & placement.** Part C (Kernel Extensions Specifications) → Cluster C.I (Core CHRs/CALs).
**Depends on:** **[[C.16 - Measurement & Metrics Characterization (MM‑CHR)|C.16]] MM‑CHR** (measurement admissibility), **[[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]** (selector S2/S3), **[[G.0 - Frame Standard and Comparability Governance - CG‑Spec|G.0]]** (CG‑Spec invariants).
**Coordinates with:** **[[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]]** (Acceptance and Evidence profiles), **[[C.23 - MethodFamily Evidence & Maturity (Method‑SoS‑LOG)|C.23]]** (MethodFamily admissibility and maturity), **[[C.18 - Open‑Ended Search Calculus (NQD‑CAL)|C.18]] NQD‑CAL** (QD and illumination), **[[C.19 - Explore-Exploit Governor (E-E‑LOG)|C.19]] E/E‑LOG** (emitters and policies), **[[E.10 - Unified Lexical Rules for FPF|E.10]]** (LEX).

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:1 - Intent

Operationalise No-Free-Lunch discipline in selection by making every run-time decision against a **typed TaskSignature (S2)**, not a paragraph. A problem reaches [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]] when its problem-side representation is stable enough for a selector-facing typed attachment record; a task or work target is ready for selection only when that attachment can be made to a declared `TaskKind`, task family, or work target without pre-binding a method. Method absence, method contestability, or method-family ambiguity is a common practical cue for this transition, but it is not the ontology of problemhood. The signature is the **smallest CHR-typed set** sufficient to drive **Eligibility -> Acceptance -> policy-governed selection** without inadmissible arithmetic or silent coercions; crossings are reviewable (Bridge+CL -> **R_eff only**).

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:1.1 - Term split used in this pattern

- `TaskSignature` attachment means attaching one typed problem record to one declared task family or work target; it does **not** pre-bind a method.
- `ScopeSlice(G)` means the claim-bounding scope cut over `EntityOfConcernRef` and scope; it is not an evidence-path slice and not a baseline-set slice.
- `threshold` is not one undifferentiated family here:
  - articulation and closure thresholds stay with cue or prompt governing patterns such as [[B.4.1 - Observe -- Notice -- Stabilize -- Route|B.4.1]] and [[B.5.2.0 - U.AbductivePrompt|B.5.2.0]]
  - acceptance-gate thresholds stay with [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]]
  - the work-measure threshold target used in specialization claims is only the declared success mark for the current task family or work target
### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:1.2 - ProblemCard@Context relation

`ProblemCard@Context` is the [[C.22.2 - ProblemCard@Context|C.22.2]]-problem-side record-side record shape for stabilizing one context-bound problem representation before downstream Principles-to-Work (P2W).

A `ProblemCard@Context` record can be used to prepare `ProblemProfile`, `TaskKind`, or candidate `TaskSignature` material for later use. Binding to one `TaskSignature` is admissible only when the downstream selector-facing object is ready. If several downstream signatures remain plausible, keep them as candidate signatures rather than binding one chosen `TaskSignature`.

This relation does not move problem-card fields into `TaskSignature`. `TaskSignature` remains the minimal [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]] attachment record for eligibility, acceptance, and selection. `ProblemCard@Context` remains the reviewable problem-side record that carries the reason this problem, in this context, can proceed to P2W, characterization, comparison, search, refresh, retirement, or another governing pattern.

The corresponding claims are governed by their named governing patterns.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:2 - Problem Frame (DesignRunTag split; crossing-visible)

**Selector-facing problem case**
For selector-facing [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]] use, a problem case applies when the problem-side representation is stable enough to attach or emit a minimal `TaskSignature` for eligibility, acceptance, and policy-governed selection. Method absence, method contestability, or method-family ambiguity is a common downstream reason for [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]] use, but it is not the only reason a `ProblemCard@Context` may be needed upstream. [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]] therefore does not define problemhood by method absence; it defines the downstream typed attachment record used once problem-side readiness is truthful. When the question under repair is still a symptom, contested framing, stale context, set-derived candidate, opportunity cue, or preselected work item, use [[C.22.2 - ProblemCard@Context|C.22.2]] before binding one chosen `TaskSignature`. When selection or synthesis of a method becomes live, strategy or policy is governed by [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] and `E/E-LOG`; [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]] use does not introduce a strategy or policy kernel type.
**Unknown‑first discipline.** Author S2 with `unknown` traits rather than coercions; **SoS‑LOG** branches MUST specify `{admit|degrade|abstain|sandbox}` handling for `unknown` via closed enums registered at UTS.

Un‑typed "problems" collapse into **informal prose**; selectors cannot **filter or abstain** admissibly; acceptance-gate thresholds leak into scoring; cross‑Context reuse is by name, not Bridge. We need a Context‑local descriptor that (i) obeys **MM‑CHR admissibility** (Scale/Unit/Polarity proven before any aggregation), (ii) records **Assurance lanes (TA/VA/LA)** per **[[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]]** and **ReferencePlane**, (iii) carries **tri‑state unknowns** explicitly, and (iv) records crossing attestations (**BridgeCard + UTS row**) with **Φ(CL)/Φ_plane** policy‑ids.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:3 - Problem

Without typed descriptors, **Eligibility and Acceptance** degenerate into prose; **inadmissible operations** creep in (ordinal means; unit mixing); **cross‑plane comparisons** lose **CL/Φ** penalty assignment (**penalties to R_eff only**).

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:4 - Forces

| Force                        | Tension                                                                                                                           |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Parsimony vs sufficiency** | Fewer fields to avoid ceremony **vs** enough to drive admissible gating.                                                              |
| **Unknowns**                 | Many traits are **unknown** in the initial problem record → tri‑state semantics must propagate to Acceptance without silent coercions.                |
| **CHR admissibility**             | **No mean on ordinals; no unit mixing**; polarity & scale type must be declared *before* aggregation.                             |
| **Locality vs portability**  | Problem is **in‑room**; still must cross **via Bridges**, with **CL** and (if planes differ) **CL^plane** penalties → **R** only. |

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5 - Solution — **Problem‑CHR** (fields) + **TaskSignature (S2) attachment** *(normative)*

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.1 - Minimal CHR fields (tri‑state aware).
**Selector-side field boundary.** The fields below are live only after problem framing has been stabilized enough to ask eligibility, acceptance, selection, method-family, or policy-governed choice questions. They are not a universal problem-framing checklist and must not replace the [[C.22.2 - ProblemCard@Context|C.22.2]] Thin `ProblemCard@Context` pass for a messy signal. Each live field is **CHR-typed** (Characteristic, Scale, Unit, Polarity; MM-CHR discipline). Every predicate admits `unknown` (tri-state). Unknown-handling policy propagates `{degrade|abstain|sandbox}` per Acceptance profile or EvidenceProfile policy (recorded in SCR). (G.4/G.6 alignment)

**Optional extension absence rule.** If QD, OEE, archive, generator, parity, specialization, or another optional relation is not live for the current case, the corresponding optional fields are absent, not `unknown`. Use `unknown` only for a live field whose value is currently unknown. An absent non-live extension does not trigger `{degrade|abstain|sandbox}` propagation.

* **`DataShape`** — data regime and admissible transforms (e.g., tabular, sequence, graph; density; stationarity claims).
* **`NoiseModel`** — uncertainty class and robustness envelope (e.g., iid Gaussian; heavy‑tailed; adversarial budget).
* **`ObjectiveProfile`** — objective heads (**Scale, Unit, Polarity** and **ReferencePlane** declared), polarity, and **admissible order relations** (lexicographic, Pareto, medoid or median where admissible). **Weighted sums across mixed scale types are forbidden**; ordinal heads use order-only guards. For QD tasks, explicitly enumerate quality heads, diversity or descriptor-space heads, and any policy-authorized QD contribution heads; see **DominanceRegime** below. Do not introduce a default QD score. If a scalar or set-scalarization policy is live, cite the governing CAL policy and keep dominance and telemetry roles explicit.
* `RegularityTraits` — method‑relevant structure (**convexity, differentiability, separability, monotonicity**) as CHR‑typed predicates with guard‑macros (e.g., `ORD_COMPARE_ONLY`, `UNIT_CHECK`, `POLARITY_CHECK`). Include `ConditionClass` (e.g., stiffness/κ‑proxies) where applicable.
* **`Constraints`** — explicit hard and soft constraint classes (feasibility predicates; **ResourceEnvelope** and **RiskEnvelope**). **Acceptance-gate thresholds live in [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]] only; never inside CHR or code paths.**
* `ShiftClass` and stationarity — CHR‑typed claims about regime stability (iid | covariate‑shift | concept‑drift | adversarial). Default=`unknown`. Acceptance or flow use is governed by this field in gating; otherwise abstain.
* `EvidenceGraphRef ([[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]])` — carriers & **lane tags (TA/VA/LA)** with **freshness windows**; **no self‑evidence**; default Γ‑fold = **weakest‑link** unless CAL proves an alternative.
* `ScopeSlice(G)` — the **USM claim-bounding scope cut** over **EntityOfConcernRef and scope** (discipline governance in **CG‑Spec**; Domain is a catalog mark only).
* `Size/Scale` — size and condition proxies (**n, m, κ, sparsity**) with **declared units**; unit mismatch ⇒ {sandbox|refuse}.
* **`Freshness`** — validity window for descriptors.
* `Missingness` — **MCAR, MAR, or MNAR** (or mapped equivalents) per **CHR.Missingness**; MUST be honoured by Acceptance and Flows.
* `KindSet` — **`U.Kind[]`** for the selected entities addressed by the TaskKind; separates **EntityOfConcern kind** from **Scope (USM)**.

**QD and Illumination extensions (normative; ties to [[C.18 - Open‑Ended Search Calculus (NQD‑CAL)|C.18]] and [[C.19 - Explore-Exploit Governor (E-E‑LOG)|C.19]]).**

Use this extension block only when QD, illumination archive, set-return, or OEE generator relation is live for the current case. It is not part of every `TaskSignature`.

* **`CharacteristicSpaceRef`** — reference to **`U.CharacteristicSpace`**, with declared **d≥2**; **characteristics are CHR‑typed**; **ReferencePlane** per characteristic; pin edition via **`CharacteristicSpaceRef.edition`**.
* **`ArchiveConfig`** — archive **topology** (grid, CVT, or graph), **resolution** (bins or centroids), **K‑capacity**, **`InsertionPolicyRef`** (elite replacement, dedup, or novelty), and **`DistanceDefRef.edition`** (declare **metric or pseudometric** status and invariances; any normalisation **MUST** cite admissible scale transforms in **CG‑Spec**); admissibility follows CG‑Spec.
* **`EmitterPolicyRef`** — pointer to emitter/governor policy ([[C.19 - Explore-Exploit Governor (E-E‑LOG)|C.19]]) applicable to this TaskSignature; **edition id** recorded.
* **`DominanceRegime`** — `{ParetoOnly | ParetoPlusIllumination}`. **Default = `ParetoOnly`** (illumination remains report‑only telemetry unless CAL explicitly authorises `ParetoPlusIllumination`, policy‑id cited).
* **`IlluminationSummary`** — a **telemetry summary over `Diversity_P`**; reported by default; excluded from dominance unless a CAL enables `ParetoPlusIllumination` (policy‑id cited).
* **`IlluminationMap`** *(parity‑run)* — required **IlluminationMap publication** (grid, CVT, or graph per `ArchiveConfig`) recording coverage per niche or cell with `DescriptorMapRef` and `DistanceDefRef.edition`. **Leaderboards as single‑score lists are forbidden**; comparisons **MUST** be under CG‑frames.
* **`PortfolioMode`** — `{Pareto | Archive}`. **Default = `Archive`**: selectors preserve retained archive evidence (QD archives) rather than a single “best” set; ε‑fronts remain admissible for local decisions under CG‑Spec.
* **`Budgeting`** — evaluation, time, and batch **budgets**, including **E/E‑LOG exploration budget** id; units declared (CG‑Spec).
* **`TelemetryHooks`** — **PathSliceId**, **decay and refresh policy ids**, and **edition counters** to record **U.DescriptorMap** and **policy‑id** updates upon illumination gains.
* **`GeneratorIntent`** (OEE) — optional intent to use a registered **`GeneratorFamily`** ([[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]), with pointers to **`EnvironmentValidityRegion`**, **`TransferRulesRef`**, and **coverage and regret** reporting expectations.

**Admissibility.** Before any numeric comparison or aggregation, **prove CSLC admissibility** (Scale, Unit, Polarity) and **cite CG‑Spec.Characteristics**; record **ReferencePlane**. **Unknowns** propagate as {degrade|abstain|sandbox}; **no `unknown→0/false` coercions**.

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.2 - TaskSignature (S2) — attachment definition (design‑time + run‑time).
A TaskSignature is the minimal typed record consumed by selector-facing use:
`⟨Context, TaskKind, TaskFamilyRef?, KindSet:U.Kind[], DataShape, NoiseModel, ObjectiveProfile, Constraints{incl. Resource/Risk Envelopes}, ScopeSlice(G), EvidenceGraphRef, Size/Scale, Freshness, Missingness, ShiftClass?, BehaviorSpaceRef?, ArchiveConfig?, EmitterPolicyRef?, DominanceRegime?, PortfolioMode?, Budgeting?, TelemetryHooks?, GeneratorIntent?⟩`

**Minimality rule.** S2 carries only fields required for **Eligibility→Acceptance→admissible selection**; any additional traits derived at design‑time are recorded as provenance (UTS) but **do not expand S2**.

Values are **CHR‑typed** with **provenance**; traits may be **inferred** from CHR and CAL bindings (e.g., *convexity known? differentiable? ordinal vs interval scales?*) and from **USM** scope metadata. Unknowns are tri‑state; **Missingness semantics MUST align with CHR.Missingness** and be honored by Acceptance and Flows.

`TaskKind` names the governing kind of work or problem under this context. `TaskFamilyRef?` names one comparison-relevant family inside that task kind when specialization, transfer, or parity question is live. `TaskSignature` is the context-bound typed attachment record for one current case under that kind and scope cut. `KindSet` continues to name the selected entities addressed by the task kind; it is not a substitute for the task-family reference.

**DesignRunTag hygiene.** Do not mix DesignRunTag in one signature; record **GateCrossings** as **CrossingBundles** (**[[E.18 - Transformation Flow Structure|E.18]]**; Bridge+UTS through **[[F.9 - Alignment & Bridge across Contexts|F.9]]**, **[[F.17 - Unified Term Sheet (UTS)|F.17]]**, **[[E.17 - Multi‑View Publication Kit|E.17]]**, and **[[E.18 - Transformation Flow Structure|E.18]]**) when importing design‑time traits into run‑time.

#### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.2.1 - Specialization-claim reference discipline (normative)
Any claim that one holder, dyad, team, or explicitly scoped specialist portfolio acquired usable specialization **SHALL** state one declared `TaskFamilyRef` or `TaskSignature`, one named work-measure threshold target, an adaptation budget, and the freshness or provenance basis for reuse. A method may be selected, refined, or retired as part of that story, but the method is not the bearer of the specialization claim. The attached task-family record should stay rich enough for the same task family and work target to remain admissible in [[C.22.1 - Task-family adaptation signature|C.22.1]] adaptation signatures, [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] specialization profiles, and [[G.9 - Parity and Benchmark Harness|G.9]] adaptation parity without reconstructing the claim from narrative prose.

Low-human-overlap or newly discovered task families remain admissible when those task-family or signature references are explicit by value.
### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.3 - Provenance & planes.
Record **Context** and **ReferencePlane** for each value; on any cross-Context or cross-plane reuse, attach BridgeDescription + UTS row, apply **CL** (and, if planes differ, **CL^plane**) penalties to **R_eff only**; both **Φ(CL)** and (if used) **Φ_plane** MUST be **monotone, bounded, and table‑backed**; **no “distance” language; penalties never mutate F/G.** Record policy‑ids in SCR and cite Bridge ids on crossings.

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.4 - Attachment & use.

* **Eligibility** gates read TaskSignature against each **MethodFamily.Eligibility** ([[C.23 - MethodFamily Evidence & Maturity (Method‑SoS‑LOG)|C.23]]) and **CG‑Spec.MinimalEvidence** for referenced characteristics.
* **Acceptance** clauses ([[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]]) use these fields for **acceptance-gate threshold predicates** (acceptance-gate thresholds live in Acceptance only).
* **Selection kernel** (G.5.S3) applies an **admissible order** (often partial); **weighted sums across mixed scale types are forbidden**. If only a partial order remains, **return a Pareto (non‑dominated) set** with tie notes. If `PortfolioMode=Archive`, the selector **may** return a **QD archive** (per `ArchiveConfig`) **in addition to** or **instead of** a Pareto set. **Illumination** enters dominance **only** if `DominanceRegime=ParetoPlusIllumination` is **enabled by CAL** (policy id cited); otherwise, QD telemetry values are **reported** but **excluded** from dominance.
* When `GeneratorIntent` is present, G.5-governed selection may use a registered **`GeneratorFamily`** (POET‑class); the selection domain becomes **pairs** `{environment, method}`, with Environment guarded by **`EnvironmentValidityRegion`** and **`TransferRulesRef`** ([[C.23 - MethodFamily Evidence & Maturity (Method‑SoS‑LOG)|C.23]] wiring). Report **`IlluminationSummary`** as a **telemetry summary over `Diversity_P`** (report‑only by default) in telemetry; dominance remains unaffected unless policy changes as above.

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.5 - Unknowns.
Every field admits `unknown`; downstream **degrade, abstain, or sandbox** behavior is explicit per Acceptance profile or EvidenceProfile; no implicit coercions.

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.6 - Publication.
Output a **ProblemProfile** (...Description) that carries the bound TaskSignature, **UTS** Name Cards for any minted values (twin labels), and SCR-visible provenance ([[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] evidence relations, lane tags, freshness, **ReferencePlane**). **Mark any vendor or tool examples as Plain‑register only (LEX V‑4); they are non‑normative.**

### [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:5.7 - Open‑Ended tasks (GeneratorFamily) *(normative)*.
If the problem requires **open‑ended generation** of tasks or environments, S2 **SHALL** include `GeneratorIntent` with pointers to **`EnvironmentValidityRegion`** (admissible region for generated environments), **`TransferRulesRef`** (cross‑environment transfer constraints), and **coverage and regret** telemetry expectations. Selector outputs are then declared sets over **{environment, method}**; **coverage and regret** are reported telemetry values and **IlluminationSummary** is a **telemetry summary** (reported), excluded from dominance unless a **CAL** policy promotes them (policy‑id recorded in SCR; see `DominanceRegime`). Edition increments of **CharacteristicSpaceRef.edition**, **DescriptorMapRef.edition**, **DistanceDefRef.edition**, and (OEE) **`TransferRulesRef.edition`**, and the **policy‑id** associated with illumination increases **SHALL** be recorded in SCR.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:6 - Archetypal Grounding (Tell–Show–Show)

*Tell–Show–Show hook (per [[E.8 - FPF Authoring Conventions & Style Guide|E.8]]):* label examples as **Show‑1 (continuous ODE)** and **Show‑2 (MIP)** and cite CHR guard‑macros in‑line so engineers can see **which field supplied which Eligibility or Acceptance input**.  **Explicitly annotate which S2 fields triggered each Eligibility and Acceptance decision** (e.g., `service_level@ordinal → ORD_COMPARE_ONLY`, `budget@ratio → unit alignment check`).

**A. Differential equations (continuous systems, solver choice).**
*ProblemProfile.* `DataShape=ODE, stiff?=unknown, Size/Scale={n≈10^3}, ObjectiveProfile={↓error@ratio, ↑throughput@ratio}, Constraints={budget≤X, safety_gate@ordinal}, RegularityTraits={Lipschitz known?=unknown, Jacobian sparsity=high}, Missingness=MAR`.
*Attachment.* Selector consumes TaskSignature; **eligibility** filters MethodFamilies that require known stiffness or differentiability (unknown ⇒ **degrade/abstain** per family); **Acceptance** enforces `safety_gate` as **ordinal predicate**, not averaged (ORD\_COMPARE\_ONLY), and budgets with **unit‑aligned sums** (ratio). The selector returns a **Pareto set**; no cross‑ordinal weighting.

**B. Mixed‑integer optimisation (planning and scheduling).**
*ProblemProfile.* `DataShape=MIP, NoiseModel=deterministic, ObjectiveProfile={↓cost@ratio, ↑service_level@ordinal}, Constraints={SLA hard, workforce soft}, RegularityTraits={convex_relaxation=available}, Size/Scale={vars~10^5}, Missingness=MCAR`.
*Attachment.* **CG‑Spec** forbids means over **service\_level** (ordinal); **Acceptance** holds acceptance-gate thresholds; **Eligibility** checks convex‑relaxation availability; **Selection** applies **lexicographic** guard (assumption‑fit ≻ evidence‑fit ≻ resource), compute **R\_eff** with Γ‑fold, apply **CL** penalty to **R** only; if partial order remains, return a **Pareto set**.

> *Contemporary source references (informative):* modern **Julia** ecosystems illustrate a registered outer interface with specialised implementations inside (e.g., DifferentialEquations.jl, JuMP), aligning with [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]→[[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] multi‑method selection under NFL.

**C. Quality-Diversity archive and declared set (illumination).**
*ProblemProfile.* `DataShape=policy‑search; ObjectiveProfile={↑reward@ratio, ↑coverage@ratio (report‑only)}, DominanceRegime=ParetoOnly, PortfolioMode=Archive, CharacteristicSpaceRef(d=3, characteristics=CHR‑typed), ArchiveConfig(grid, res=32×32×16, K=1, InsertionPolicyRef=elite‑replace, DistanceDefRef.edition=v1), EmitterPolicyRef=v2, Budgeting{eval=1e6}, TelemetryHooks{PathSliceId=…}`.
*Binding.* Selector may return an **archive**; **coverage and illumination** are **reported** but **excluded** from dominance (default). Any change of `DistanceDefRef.edition` or Emitter policy is **editioned** and logged in SCR.

**D. Open‑ended environment generation (POET‑class).**
*ProblemProfile.* `GeneratorIntent{GeneratorFamilyRef=…, EnvironmentValidityRegion=… (CHR‑typed), TransferRulesRef=…, CoverageMetric=…}`, `PortfolioMode=Archive`.
*Binding.* Selector outputs **{environment, method}** pairs that pass Eligibility; **TransferRules** govern cross‑environment policy reuse; telemetry reports **coverage and regret** and **IlluminationSummary** with **edition and policy‑id** when improved.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:7 - Bias‑Annotation (LEX/discipline guards)

* **No minted `U.Type` “Strategy”.** Strategy and policy remain roles inside [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]; keep “strategy” as Plain-register wording where it helps recognition, but do not introduce a new `U.Type` or strategy head.
* **Transdiscipline vs domain.** Comparability flows through **`U.Discipline` CG‑Spec**; “Domain” is a catalog mark stitched to D.CTX + UTS; do **not** attach norms to Domain labels.
* **Plain twins and head selection.** Use Description and Spec morphology correctly (I, D, S; [[E.10.D2 - EntityOfConcern, Description Episteme, and Specification-Use Discipline|E.10.D2]]).

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:8 - Anti‑patterns (normative):
* **AP‑1** Pre‑binding a Method into S2 (“problem as if task”); **Remedy:** keep S2 method‑agnostic; bind only admissible traits.
* **AP‑2** Silent `unknown→false` or `unknown→0` in Eligibility and Acceptance.
* **AP‑3** Cross‑ordinal averaging or ordinal–interval scalar mixes.
* **AP‑4** **DesignRunTag chimera** signatures (mixing stances).
* **AP‑5** **Domain** treated as governance (attach governance to **U.Discipline** and **CG‑Spec**, not Domain).
* **AP‑6** Implicit handling of data‑shift (assume iid); **Remedy:** declare `ShiftClass` (or `unknown`) and gate via Acceptance.
* **AP‑7** Tool or vendor tokens in normative text; **Remedy:** move to Plain‑register note; keep Tech references on CHR and CAL ids (LEX V‑4).

**Remedies:** tri‑state predicates; admissible order relations (lexi, Pareto, median, or medoid); explicit **GateCrossing** visibility through **CrossingBundle** (BridgeCard + UTS row + `CL/Φ` policy‑ids; **[[E.18 - Transformation Flow Structure|E.18]]**, **[[F.9 - Alignment & Bridge across Contexts|F.9]]**, **[[F.17 - Unified Term Sheet (UTS)|F.17]]**, **[[E.17 - Multi‑View Publication Kit|E.17]]**, and **[[A.21 - GateProfilization- OperationalGate(profile) (GateFit core)|A.21]]** where live); Domain stitched to **D.CTX + UTS** only.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:9 - Conformance Checklist (normative)

0. **Minimal S2.** S2 contains only fields necessary for Eligibility, Acceptance, and selection; any extra derived traits remain provenance.
1. **TaskSignature present (S2).** Every exported TaskKind has a TaskSignature with all fields declared and **CHR‑typed**; `unknown` is an admissible value for each.
2. **CHR admissibility proven.** Any numeric comparison or aggregation **cites CG‑Spec** by **Characteristic id** and proves **CSLC admissibility**; **no mean on ordinals; no unit mixing**.
3. **Unknowns propagate.** Unknowns **must** map to {pass|degrade|abstain} in **Acceptance** and **Eligibility**; no implicit coercions; behavior recorded in **SCR**.
4. **Evidence lanes.** **[[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] evidence relations** + **Assurance lanes (TA/VA/LA)** + **freshness windows** recorded; **Γ‑fold** default=weakest‑link unless proved otherwise.
5. **ReferencePlane guarded.**  ReferencePlane noted **per value and per ObjectiveProfile head**; on crossings apply **CL** (and **CL^plane** if planes differ); **Φ(CL)/Φ_plane** are **monotone, bounded, table‑backed and documented in the `CG‑Spec`**; penalties → **R_eff only** (F/G invariant).
6. **Acceptance thresholds live in CAL.** No acceptance-gate thresholds in CHR or code paths; only in **[[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]] AcceptanceClauses**.
7. **Selector admissibility.** Selection uses **admissible (possibly partial) orders**; **weighted sums across mixed scale types are forbidden**; return a **Pareto set** when appropriate.
8. **Crossings visible.** Any cross-stance/cross-Context reuse records **BridgeCard/BridgeDescription + UTS row** with CL notes and (if planes differ) CL^plane + Φ_plane.
9. **UTS twin labels.** All exported cards include **Name Cards** with twin labels; Bridges carry loss notes.
10. **GateCrossing checks.** Exported TaskSignature and any referenced crossings satisfy: (i) stance tagging (if used; informative only), (ii) **CrossingBundle** presence/consistency (**[[E.18 - Transformation Flow Structure|E.18]]**; **[[F.9 - Alignment & Bridge across Contexts|F.9]]**; **[[F.17 - Unified Term Sheet (UTS)|F.17]]**; **[[E.17 - Multi‑View Publication Kit|E.17]]**; **[[A.21 - GateProfilization- OperationalGate(profile) (GateFit core)|A.21]]** when gate checks are live), (iii) **LanePurity** (CL→R only; F/G invariant; Φ tables present), and (iv) **Lexical SD** (**[[E.10 - Unified Lexical Rules for FPF|E.10]]**). Failures are **blocking** under the active GateProfile / GateChecks (**[[A.21 - GateProfilization- OperationalGate(profile) (GateFit core)|A.21]]**).
11. **QD fields (when QD is in scope).** If `PortfolioMode=Archive` or QD heads are present, **CharacteristicSpaceRef** (d>=2), **ArchiveConfig** (topology, resolution, K, `InsertionPolicyRef`, `DistanceDefRef.edition`), and **EmitterPolicyRef** **SHALL** be present and CHR-typed; characteristics declare **ReferencePlane**.
12. **DominanceRegime default.** `DominanceRegime` **defaults to `ParetoOnly`**; inclusion of illumination in dominance **MUST** be enabled by a **CAL.Acceptance policy**; the policy id **SHALL** be recorded in SCR.
13. **Telemetry.** **PathSliceId**, **decay and refresh policy ids**, and **edition counters** for **CharacteristicSpaceRef**, **DistanceDefRef**, and **EmitterPolicyRef** **SHALL** be recorded; any illumination increase **SHALL** log the **policy-id** that triggered it.
14. **GeneratorIntent (when OEE is in scope).** `GeneratorIntent` **SHALL** cite **`EnvironmentValidityRegion`** and **`TransferRulesRef`** (ids resolvable in G.5/C.23); absence => `Abstain` for OEE generator-family use.
15. **Budgets.** `Budgeting` (evaluation, time, and batch) **SHALL** declare units and E/E-LOG exploration budget id when used.
16. **Archive admissibility.** `DistanceDefRef.edition` and any novelty measures **SHALL** be CSLC-admissible and **editioned**; inadmissible operations => **Abstain**.
17. **Planes.** **ReferencePlane** **SHALL** be declared for all QD heads or characteristics; plane crossings apply **Phi\_plane** (penalty to **R** only).
18. **Unknowns.** Unknown QD fields **map** to `{degrade|abstain|sandbox}`; no coercions.

19. **Specialization claims referenced.** Any declared specialization on this TaskSignature **SHALL** name the task family/work target, named work-measure threshold target, adaptation budget, freshness or provenance basis for reuse, and enough attachment detail for the same claim to remain admissible in [[C.22.1 - Task-family adaptation signature|C.22.1]], [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]], and [[G.9 - Parity and Benchmark Harness|G.9]] use.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:10 - Interfaces & Data Paths

*Inputs.* `ProblemProfile` (...Description), CG-Spec ids, Evidence Graph Ref ([[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]]), D.CTX; CharacteristicSpaceRef, ArchiveConfig, and EmitterPolicyRef configs when QD is live; GeneratorIntent when OEE is live.
*Produces.* `TaskSignature` under a declared `Context` field (S2) with provenance; **SCR-visible** fields; UTS Name Cards for any minted traits; archive, `PortfolioMode` semantics, and telemetry hooks declared when QD is live. Do not introduce `TaskSignature@Context` as a separate kind.
*Used by.* **[[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]** (Eligibility and Selection kernel), **[[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]]** (Acceptance and Evidence), **[[C.23 - MethodFamily Evidence & Maturity (Method‑SoS‑LOG)|C.23]]** (admit, degrade, and abstain rules and method-family maturity checks).

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:11 - Consequences (informative)

* **Admissible selection.** Selection is **explainable** and **review-ready**; every reason in/out cites TaskSignature fields, CG-Spec rows, and Gamma-fold contributors.
* **Local first, portable later.** Context-local semantics are primary; Bridges make portability **deliberate and costed** (penalties to **R** only).
* **Frictionless downstream.** G.1-G.5 use one **single, typed** TaskSignature; thresholds are cleanly separated into **Acceptance**; unknowns are not guessed.
* **QD and OEE-ready.** Typed QD and GeneratorIntent fields make **declared returned-set structure** and **open-ended** generation contexts **explicit**, with admissible dominance, editioned distances, and policy-aware illumination.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:12 - Relations
**Builds on:** **[[C.16 - Measurement & Metrics Characterization (MM‑CHR)|C.16]] MM-CHR**, **[[G.0 - Frame Standard and Comparability Governance - CG‑Spec|G.0]] CG-Spec**. **Coordinates with:** **[[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]] Acceptance**, **[[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] Selector**, **[[C.18 - Open‑Ended Search Calculus (NQD‑CAL)|C.18]] NQD-CAL**, **[[C.19 - Explore-Exploit Governor (E-E‑LOG)|C.19]] E/E-LOG**, **[[C.23 - MethodFamily Evidence & Maturity (Method‑SoS‑LOG)|C.23]] Method-SoS-LOG**. **Constrained by:** **[[E.10 - Unified Lexical Rules for FPF|E.10]] (selected `EntityOfConcern`, Description-episteme, specification-use, and publication-lane wording)**, **[[E.18 - Transformation Flow Structure|E.18]] (GateCrossing visibility and publication gating)**.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:13 - Practical use checks

- If two candidate approaches are answering different `TaskKind`s or different `ScopeSlice(G)` cuts, a direct comparison is not admissible yet.
- If specialization is the live specialization question, the task-family reference, threshold target, adaptation budget, and provenance basis should already be recoverable from the attached `TaskSignature`.
- If crossing, normalization, or missingness changes what comparison means, state that in the signature and its cited refs rather than hiding it in code, local memory, or later prose.
- If `QD` or `OEE` heads are in scope, archive and generator fields belong in the same typed signature rather than in a detached explanatory appendix.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:14 - Goldilocks hook (design‑time)

When generating candidate solutions for a **TaskKind**, aim for **“goldilocks”** slots (feasible‑but‑hard) so that the TaskSignature is informative (neither trivial nor impossible); this aligns with **[[G.1 - CG‑Frame‑Ready Generator|G.1]]** (goldilocks target, abductive provenance) and ensures the **TaskSignature is informative** (neither trivial nor impossible) for **[[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]** selection.

## [[C.22 - Problem Typing & TaskSignature Assignment (Problem-CHR)|C.22]]:End
