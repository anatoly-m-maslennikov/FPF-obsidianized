---
type: "fpf-pattern"
context:
  - "FPF"
page_type: "fpf-pattern"
mode: "canonical-generated"
fpf_id: "G.2"
title: "SoTA Harvester & Synthesis"
part: "[[FPF - Part G – Discipline SoTA Patterns Kit]]"
parents:
  - "[[FPF - Part G – Discipline SoTA Patterns Kit]]"
source_file: "FPF-Spec.md"
source_lines:
  - 80242
  - 80745
status: "Stable"
normativity: "Normative *(unless explicitly marked informative)*"
generated_on: "2026-06-15"
generated: true
---


> **Type:** Architectural (A)
> **Status:** Stable
> **Normativity:** Normative *(unless explicitly marked informative)*
>
> **Purpose.** Provide a repeatable, auditable way to **discover**, **triage**, and **synthesize** state‑of‑the‑art (SoTA) across competing `Tradition` lineages *before* minting CHR/CAL/LOG assets for a `CG‑Frame`.
> The primary output is a **`SoTA Synthesis Pack@CG‑Frame`** that feeds:
>
> * naming/publication (UTS),
> * CHR authoring ([[G.3 - CHR Authoring for a CG‑Frame- Characteristics, Scales, Levels, Coordinates|G.3]]),
> * CAL authoring ([[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]]),
> * method/generator registries and dispatch ([[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]).
>
> **Scope note.** This pattern **governs** the harvesting + synthesis *generator* in Part G. Shipping governing-definition assignment is in **[[G.10 - SoTA Pack Shipping|G.10]]**, refresh orchestration governing-definition assignment is in **[[G.11 - Telemetry-Driven Refresh & Decay Orchestrator|G.11]]**.
>
> **Terminology note (normative).** In normative clauses below, **`Tradition`** refers to the *Tech* token `Tradition` (a plural lineage with internally coherent commitments). Plain “tradition” is allowed only as a 1:1 synonym.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:1 - Problem frame

A team extends FPF into a new `CG‑Frame`. The relevant literature is typically:

* **plural** (multiple `Tradition` lineages with incompatible commitments),
* **context‑sensitive** (results depend on `U.BoundedContext` and declared `entityOfConcern`),
* **method‑heterogeneous** (different evidence styles, operator sets, and validity regions),
* **time‑sensitive** (rapid drift post‑2015; frequent benchmark/protocol shifts).

Downstream Part‑G work (CHR/CAL/selection/shipping/refresh) depends on the team producing **consumable, citation‑ready artefacts** without collapsing semantic boundaries across contexts or planes.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:2 - Problem

How can we systematically assemble a SoTA view that is:

1. **pluralist but comparable** (plurality preserved; comparability is achieved only via explicit crossings),
2. **evidence‑addressable** (claims cite auditable evidence surfaces and anchors),
3. **actionable** (produces inventories and cards that G.3/G.4/G.5 can consume),
4. **refreshable** (editions/policies/windows are pinned so RSCR/refresh can re‑audit and re‑run without semantic drift)?

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:3 - Forces

* **Pluralism vs. consolidation.** Consolidation is valuable, but unqualified fusion destroys meaning.
* **Breadth vs. load‑bearing depth.** Too broad becomes shallow; too deep misses rival lineages.
* **Recency vs. stability.** Freshness matters, yet durable “backbone” claims must be identified and kept visible.
* **Pedagogy vs. rigour.** Outputs must be teachable enough to support review, while remaining audit‑ready.
* **Authoring vs. operations.** This pattern lives in the authoring plane; operational runs and decisions belong to Work planes and to governing patterns.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:4 - Solution

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.1 - [[G.Core - Part G Core Invariants|G.Core]] linkage (normative)

**Builds on:** [[G.Core - Part G Core Invariants|G.Core]] (Part‑G core invariants; citation/delegation hub)

**GCoreLinkageManifest (normative).**
*(Canonical form, Nil‑elision, and Expansion rule are defined in [[G.Core - Part G Core Invariants|G.Core]].)*

`GCoreLinkageManifest := ⟨
  CoreConformanceProfileIds := {
    GCoreConformanceProfileId.PartG.AuthoringBase,
    GCoreConformanceProfileId.PartG.UTSWhenPublicIdsMinted
  },
  RSCRTriggerSetIds := {GCoreTriggerSetId.SoTAHarvestSynthesis},
  CorePinSetIds := {GCorePinSetId.PartG.CrossingVisibilityPins},

  CorePinsRequired := {
    // Scope pins ([[G.2 - SoTA Harvester & Synthesis|G.2]]‑specific)
    CG-FrameContext,
    Tradition[],
    entityOfConcern := ⟨GroundingHolon, ReferencePlane⟩,
    SoTA_SetId,
    SoTAPaletteDescriptionId,

    // Evidence / provenance pins ([[G.2 - SoTA Harvester & Synthesis|G.2]]‑specific)
    CorpusLedgerId,
    FlowRecordId,
    EvidenceAnchorRef[],
    EvidenceGraphId?,

    // Crossing / synthesis pins (delta beyond CorePinSetIds; only when used)
    GammaEpistSynthId[]?,

    // Edition / policy pins (only when used)
    HarvestPolicyRef?,
    DistanceDefRef.edition?,
    InclusionCriteriaId?,
    ScreeningRubricId?
  },

  DefaultsConsumed := ∅,
  TriggerAliasMapRef := ∅
⟩`

*(RSCR payload pins: `ClaimSheetId[]`, `SoTA_SetId`, `SoTAPaletteDescriptionId`, `BridgeMatrixId?`, `GammaEpistSynthId[]?`, `UTSRowId[]?`, `DistanceDefRef.edition?`, `HarvestPolicyRef?`, `InclusionCriteriaId?`, `ScreeningRubricId?`, `PathId/PathSliceId?` when path‑citable evidence or a stable freshness window is pinned.)*

**Pattern‑local default rules (governed by this pattern; not a Part‑G‑wide `DefaultId`).**

`FamilyCoverageFloorK := 3` *(unless explicitly overridden by `HarvestPolicyRef` and recorded in `FlowRecord`)*

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.2 - Kit: `SoTA Synthesis Pack@CG‑Frame` (surface governed by this pattern)

A conforming [[G.2 - SoTA Harvester & Synthesis|G.2]] publication produces a **notation‑independent pack** whose internal organisation is free, but whose exported **named components and views** are stable and citable:

Each named component is addressable via a stable **pack‑local identifier** (e.g., `CorpusLedgerId`, `ClaimSheetId`, `FlowRecordId`) for citation and RSCR scoping. If any component is minted/evolved as a **public id**, it is published and cited via `UTSRowId[]` per `CC‑GCORE‑UTS‑1` (delegation).

0. **`SoTA_Set@CG‑Frame`** *(export view; “M2 output” consumed downstream)*
   A read‑optimised view over the harvested candidate set that downstream generator/selector work treats as the “harvester output set”.
   **Constraint (normative):** `SoTA_Set@CG‑Frame` **MUST** be reconstructible from pack components by id (no “hidden extra set”).

1. **`G.2a CorpusLedger`**
   Ledger of candidate sources with Context and triage status (e.g., include / park / retire) and explicit rationale hooks.

2. **`G.2b ClaimSheets[Tradition]`**
   Typed Claim Sheets per `Tradition`, each with:

* explicit `U.BoundedContext` and `entityOfConcern`,
* explicit evidence anchors/citations ([[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] and/or EvidenceGraph refs when available),
* explicit freshness window notes and risk/trust cues *(cite [[B.3 - Trust and Assurance Calculus (F-G-R with Congruence)|B.3]] governing definitions when using trust/decay language)*.

3. **`G.2c OperatorAndObjectInventory`**
   Inventory of candidate CHR terms (characteristics/scales/coordinates) and candidate CAL operators/flows *as stubs* for downstream authoring.

4. **`G.2d BridgeMatrix`**
   A citable alignment/divergence surface across `Tradition`×`Tradition`, with explicit losses and row scopes.
   If any row asserts substitution or fusion across sources or across `Tradition` records, the pack **MUST** attach a `GammaEpistSynthId` record (alias: **`G.2‑F`**) per `G.2:Ext.GammaEpistSynthesis` (no silent fusion).

5. **`G.2e MicroExamples`**
   Worked micro‑examples for load‑bearing claims, each citing [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] carriers, declaring context + `entityOfConcern`, and annotating assurance type(s) (`TA`/`VA`/`LA`, where applicable).

6. **`G.2f UTSProposals`**
   Draft Name Cards + Minimal Definitional Sheets (MDS) + alias proposals (incl. concept‑set linkage where applicable), with the required publication pins.

7. **`G.2g entityOfConcern Map`**
   Map from key terms/claims/public ids to `GroundingHolon`, `ReferencePlane`, and minimal reference cues for later CHR/CAL authoring.

8. **`G.2h PRISMA Flow Record`**
   A screening/eligibility trail for how sources entered the pack (method‑profile is allowed; see Extensions).
   *(Name is historical; the artefact remains notation‑independent.)*

9. **`G.2i SoSIndicatorFamilies`**
   Indicator *families* as variants (windows/constraints/assumptions) **with explicit Acceptance branches per variant** (branch ids/labels only; threshold semantics belong to CAL governing definitions).

10. **`G.2j MethodFamilyCards`**
    Candidate method families with a shared signature and a plurality of implementations, each with validity regions, cost/complexity notes, and known failure modes.
    When the pack targets downstream registry/dispatch, MethodFamily cards **SHOULD** include the declared refs and pins [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] needs (eligibility predicate refs, assurance profile cues, and the pack ids that justify the family).

11. **`G.2k GeneratorFamilyCards`** *(if applicable)*
    Candidate generator families for environment/task generation with declared validity regions and transfer hooks.

12. **`G.2l Annexes`** *(optional; governing-definition-cited; see Extensions)*
    For example: QD/NQD annexes, discipline‑specific indicator annexes, interop forms.

**SoTAPaletteDescription** *(export view; required downstream)*
A view‑friendly description object (pack‑local `SoTAPaletteDescriptionId`) that binds together:
* the `SoTA_Set@CG‑Frame` view,
* `ClaimSheetId[]`, `OperatorAndObjectInventory`, `BridgeMatrixId?`,
* `SoSIndicatorFamilies` (with variant/branch structure),
* `MethodFamilyCards` / `GeneratorFamilyCards?`,
* `MicroExamples`, `UTSProposals`,
* and the `entityOfConcern Map` for citation and later CHR/CAL authoring.
**Note (normative intent):** this is the primary “consumable surface” for `G.3/G.4/G.5`; it prevents downstream patterns from scraping free prose.

**Editorial template: 1‑page “SoTA Sheet” per Tradition (informative).**
When authoring `ClaimSheets[Tradition]`, teams often benefit from a single‑page template: scope + claims + evidence anchors + validity region + failure modes + freshness window + cross‑Tradition reuse notes + pointers to micro‑examples.

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.3 - Harvester loop (conceptual choreography; pattern-governed)

A conforming [[G.2 - SoTA Harvester & Synthesis|G.2]] pack publication is built by iterating the following conceptual loop until the declared gates are satisfied:

1. **Declare scope and plurality.**
   Declare `CG-FrameContext`, the initial `Tradition` set, and the `entityOfConcern` surface for each intended claim region. Record these declarations in the pack pins (not as implicit assumptions).

2. **Discover and triage sources (ledger‑first).**
   Populate `CorpusLedger` via:

* seed sources,
* expansion via citation chaining and keyword family exploration,
* pruning using load‑bearing relevance tests tied to the declared CG‑Frame scope.

3. **Distill claims per `Tradition`.**
   For each `Tradition`, author a Claim Sheet that preserves internal commitments and cites evidence anchors. Do not fuse cross‑`Tradition` claims at this stage.

4. **Inventory operators/objects for downstream authoring.**
   Extract candidate measurement terms and operator stubs for later CHR/CAL authoring (without asserting legality or thresholds locally).

5. **Build alignment/divergence surfaces.**
   Where reuse across `Tradition` is desired, author Bridge‑backed alignment records and explicit loss notes in `BridgeMatrix`. Any consolidation is explicitly marked as requiring alignment proof.

6. **(Alias: [[G.2 - SoTA Harvester & Synthesis|G.2]]‑F) Produce Γ_epist synthesis records when fusion/substitution is asserted.**
   If a [[G.2 - SoTA Harvester & Synthesis|G.2]] pack publication asserts fusion or substitution across sources or across `Tradition` records (beyond mere “parallel divergent claims”), it **MUST** emit `GammaEpistSynthId` records per `G.2:Ext.GammaEpistSynthesis` (provenance union + explicit object alignment refs + assurance tuple refs), and it **MUST** keep penalties routed to `R_eff` only by delegation (`CC‑GCORE‑PEN‑1`).

7. **Publish teachable micro‑groundings.**
   Attach worked micro‑examples to load‑bearing claims, each tied to [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] carriers and declaring context + `entityOfConcern`.

8. **Apply gates and record repairs.**
   Enforce `FamilyCoverageFloorK` (and any optional diversity‑by‑distance gate). If a gate fails, the pack **MUST**:
   * record the failure and the repair iteration in `FlowRecord` and `CorpusLedger`,
   * pin the updated `HarvestPolicyRef` / criteria ids (if changed),
   * iterate the loop rather than silently weakening the gate.

9. **Emit hand‑off manifests and export views.**
   Produce explicit manifests to:

* [[G.3 - CHR Authoring for a CG‑Frame- Characteristics, Scales, Levels, Coordinates|G.3]] (CHR authoring),
* [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]] (CAL authoring),
* [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] (registry/dispatch),
  so that downstream work can cite pack components by id rather than re‑authoring them.
   The pack **MUST** also export `SoTA_Set@CG‑Frame` and `SoTAPaletteDescription` as the default downstream consumption surfaces (ids pinned).

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.4 - Interfaces (minimal I/O Standard)

| Interface         | Consumes                                                      | Produces                                                                    |
| ----------------- | ------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **[[G.2 - SoTA Harvester & Synthesis|G.2]]‑1 Harvest** | `CG-FrameContext`, initial `Tradition[]`, `HarvestPolicyRef?`  | `SoTA Synthesis Pack@CG‑Frame` (G.2a–G.2l)                                  |
| **[[G.2 - SoTA Harvester & Synthesis|G.2]]‑2 Extend**  | existing Pack + new sources/anchors + updated policy pins     | updated Pack + RSCR‑relevant trigger emissions (canonical kinds)            |
| **[[G.2 - SoTA Harvester & Synthesis|G.2]]‑3 HandOff** | Pack                                                          | `CHR‑handoff` (to [[G.3 - CHR Authoring for a CG‑Frame- Characteristics, Scales, Levels, Coordinates|G.3]]), `CAL‑handoff` (to [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]]), `Registry‑handoff` (to [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]) |

*Note:* Orchestration of re‑runs is governed by [[G.11 - Telemetry-Driven Refresh & Decay Orchestrator|G.11]]; this pattern only defines what a conforming (re)harvest produces and what pins it must expose.

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.5 - Extensions (pattern‑scoped; non‑core)

`Extensions` are pattern‑scoped annexes. They do not introduce Part‑G‑wide norms; they declare the additional pins required when those semantics are active and cite the corresponding governing patterns.

##### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.5.1 - GPatternExtension: GammaEpistSynthesis

**PatternScopeId:** `G.2:Ext.GammaEpistSynthesis`
**GPatternExtensionId:** `GammaEpistSynthesis`
**GPatternExtensionKind:** `GeneratorSpecific`
**GoverningPatternId:** [[G.2 - SoTA Harvester & Synthesis|G.2]]
**Uses:** `{[[G.Core - Part G Core Invariants|G.Core]], [[B.3 - Trust and Assurance Calculus (F-G-R with Congruence)|B.3]], [[F.9 - Alignment & Bridge across Contexts|F.9]], [[G.6 - Evidence Graph & Provenance Ledger|G.6]]}` *(penalty routing + trust/decay cues + bridges/CL + evidence path citation when used)*
**⊑/⊑⁺:** `∅`
**RequiredPins/EditionPins/PolicyPins (minimum):**

* `GammaEpistSynthId[]` *(pack‑local ids of synthesis records; emitted iff fusion/substitution is asserted)*
* `EvidenceAnchorRef[]` *(provenance union; [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] carriers)*
* `BridgeMatrixId` and `BridgeCardId[]` *(explicit object alignment references when crossing is involved)*
* `CL/CL^plane` + `Φ/Ψ/Φ_plane policy-ids` *(ids only; semantics governed by cited definitions; penalties → `R_eff` only by delegation)*
* `PathId/PathSliceId?` *(only when citing via [[G.6 - Evidence Graph & Provenance Ledger|G.6]])*

**RSCRTriggerKindIds:** `{RSCRTriggerKindId.EvidenceSurfaceEdit, RSCRTriggerKindId.CrossingBundleEdit, RSCRTriggerKindId.ReferencePlaneEdit, RSCRTriggerKindId.PenaltyPolicyEdit, RSCRTriggerKindId.PolicyPinChange, RSCRTriggerKindId.EditionPinChange}`

**Notes (normative intent; duplication‑avoidant):**
* `Γ_epist^synth` is an auditable record that binds: (i) provenance union, (ii) explicit object alignment refs, (iii) assurance tuple refs (via existing governing definitions) for each asserted fusion/substitution.
* This extension **does not** redefine `Γ‑fold`, `Φ`, or penalty semantics; it only requires the pins/refs needed for replayability and auditability (see [[G.Core - Part G Core Invariants|G.Core]] delegations).

##### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.5.2 - GPatternExtension: HarvestProtocols

**PatternScopeId:** `G.2:Ext.HarvestProtocols`
**GPatternExtensionId:** `HarvestProtocols`
**GPatternExtensionKind:** `Phase3Seed`
**GoverningPatternId:** [[G.2 - SoTA Harvester & Synthesis|G.2]]
**Uses:** `{[[B.3 - Trust and Assurance Calculus (F-G-R with Congruence)|B.3]], [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]]}` *(for freshness/decay and provenance anchors, when protocol requires them explicitly)*
**⊑/⊑⁺:** `∅`
**RequiredPins/EditionPins/PolicyPins (minimum):**

* `HarvestPolicyRef` *(declares the chosen protocol family and its parameters)*
* `FlowRecordId` *(protocol‑specific profile id or rubric id may be attached here)*
* `InclusionCriteriaId` / `ScreeningRubricId` *(ids only; semantics remain local to the protocol family)*

**RSCRTriggerKindIds:** `{RSCRTriggerKindId.PolicyPinChange, RSCRTriggerKindId.EditionPinChange, RSCRTriggerKindId.FreshnessOrDecayEvent}`

**Notes (extension discipline):**
* This extension binds a declared protocol profile to the pack’s `FlowRecord` without redefining evidence semantics.

##### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.5.3 - GPatternExtension: DHCAlignmentHooks

**PatternScopeId:** `G.2:Ext.DHCAlignmentHooks`
**GPatternExtensionId:** `DHCAlignmentHooks`
**GPatternExtensionKind:** `DisciplineSpecific`
**GoverningPatternId:** [[C.21 - Field Health & Structure (Discipline-CHR)|C.21]] *(DHC semantics are governed by [[C.21 - Field Health & Structure (Discipline-CHR)|C.21]])*
**Uses:** `{[[C.21 - Field Health & Structure (Discipline-CHR)|C.21]], [[G.6 - Evidence Graph & Provenance Ledger|G.6]], [[G.7 - Cross‑Tradition Bridge Calibration Kit (BridgeMatrix → BridgeCards + BCT-Sentinels)|G.7]]}` *(DHC series + evidence path citations + bridge/CL regimes when alignment density is claimed)*
**⊑/⊑⁺:** `∅`
**RequiredPins/EditionPins/PolicyPins (minimum):**

* `DHCMethodRef.edition`
* `WindowRef?` *(if the DHC series is windowed)*
* `DHCSenseCellId[]` *(pack‑local ids for emitted DHC SenseCells; if any are public, cite via `UTSRowId[]`)*
* `UTSRowId[]?` *(only if any DHC SenseCells / series ids are minted/evolved as public ids)*
* `PathId[]` / `PathSliceId[]` *(when alignment summaries cite evidence paths via [[G.6 - Evidence Graph & Provenance Ledger|G.6]])*

**RSCRTriggerKindIds:** `{RSCRTriggerKindId.EditionPinChange, RSCRTriggerKindId.EvidenceSurfaceEdit, RSCRTriggerKindId.TelemetryDelta}`

**Notes (extension discipline):**
* If DHC alignment summaries are emitted, this extension ensures the DHC method edition and the cited evidence paths are visible.
* Units/constraints (governing pattern: [[C.21 - Field Health & Structure (Discipline-CHR)|C.21]]) must be **pinned, not redefined** here (e.g., `bridges_per_100_DHC_SenseCells`, `CL_min = 2` for cross‑Context counting, and the “CL=3 implies free substitution” interpretation when used).

##### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.5.4 - GPatternExtension: NQDAnnex

**PatternScopeId:** `G.2:Ext.NQDAnnex`
**GPatternExtensionId:** `NQDAnnex`
**GPatternExtensionKind:** `MethodSpecific`
**GoverningPatternId:** [[C.18 - Open‑Ended Search Calculus (NQD‑CAL)|C.18]] *(NQD-CAL semantics are governed by [[C.18 - Open‑Ended Search Calculus (NQD‑CAL)|C.18]]; explore/exploit logging is governed by [[C.19 - Explore-Exploit Governor (E-E‑LOG)|C.19]] when used)*
**Uses:** `{[[C.18 - Open‑Ended Search Calculus (NQD‑CAL)|C.18]], [[C.19 - Explore-Exploit Governor (E-E‑LOG)|C.19]]}`
**⊑/⊑⁺:** `∅`
**RequiredPins/EditionPins/PolicyPins (minimum):**

* `DescriptorMapRef.edition`
* `DistanceDefRef.edition`
* `InsertionPolicyRef` *(policy‑id/ref)*
* `EmitterPolicyRef` *(policy‑id/ref)*
* `TaskSignatureRef?` *(when QD mode is trait‑gated)*

**RSCRTriggerKindIds:** `{RSCRTriggerKindId.EditionPinChange, RSCRTriggerKindId.PolicyPinChange, RSCRTriggerKindId.TelemetryDelta, RSCRTriggerKindId.FreshnessOrDecayEvent}`

**Notes (extension discipline):**
* This extension only pins the required references for replayability; it does not redefine QD semantics, dominance, or acceptance rules.

##### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.5.5 - GPatternExtension: InteropForms

**PatternScopeId:** `G.2:Ext.InteropForms`
**GPatternExtensionId:** `InteropForms`
**GPatternExtensionKind:** `InteropSpecific`
**GoverningPatternId:** [[G.13 - External Interop Hooks for SoTA Discipline Packs (conceptual)|G.13]]
**Uses:** `{[[G.13 - External Interop Hooks for SoTA Discipline Packs (conceptual)|G.13]]}`
**⊑/⊑⁺:** `∅`
**RequiredPins/EditionPins/PolicyPins (minimum):**

* `ExternalIndexRef.edition`
* `ClaimMapperRef.edition`
* `MappingPolicyRef` *(policy‑id/ref)*
* `UTSRowId[]` *(for published external ids/aliases where relevant)*

**RSCRTriggerKindIds:** `{RSCRTriggerKindId.EditionPinChange, RSCRTriggerKindId.PolicyPinChange, RSCRTriggerKindId.TokenizationOrNameChange, RSCRTriggerKindId.EvidenceSurfaceEdit}`

**Notes (extension discipline):**
* Interop affects only representation and citation routes; it must not introduce alternate legality gates or acceptance semantics.

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.6 - Palette first

- `SoTAPaletteDescription` is one plurality-preserving palette.
- It is not by itself one `Front`, one `Archive`, or one `Shortlist`.
- When that palette's members are traditions, `TraditionPalette` is the reader-facing tradition-only palette head over the same palette declaration, not one second governing definition. For methods, hypotheses, or other members, keep `SoTAPaletteDescription` or `Palette + SubjectKind` explicit instead.
- Traditions remain in the palette until a later surface declares comparison, retention, or choice semantics explicitly.
- `TraditionFront` is one derived view over the declared palette under one declared `Q`; the `Q` basis stays pinned separately and the view does not rename `Tradition` or `SoTAPaletteDescription`.
- `TraditionArchive` is one derived retention view over that same palette under one declared reachability or coverage rule; that rule stays pinned separately and the view does not turn the palette into one archive by default.
- When one derived tradition view is shown, keep the base palette recoverable at the same time.
- When comparison or retention needs richer geometry or atlas language, treat that as support for the derivation rather than as the default meaning of the palette.
- A reader should be able to say both `this is the palette` and `this is the derived tradition view currently being shown` without collapsing those two objects.

### [[G.2 - SoTA Harvester & Synthesis|G.2]]:4.7 - Atlas views stay optional neighboring interpretation over one declared palette and declared set results

- `TraditionAtlasView` is one declared optional neighboring interpretive view over one palette and any declared front, archive, or shortlist surfaces drawn from it, while the cited substrate-bearing line, the active source set or active set result, and any cited `SearchSpaceRef`, `OutcomeSpaceRef`, or other declared space refs remain recoverable.
- `TraditionAtlasView` is the [[G.2 - SoTA Harvester & Synthesis|G.2]] use-site specialization of `DeclaredSubstrateAtlasView`; keep the generic interpretive-view declaration in [[A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW - Declared-Substrate Interpretive View|A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW]].
- It is not the default meaning of `Tradition` or `SoTAPaletteDescription`.
- Stay palette-first when the harvest or synthesis question can already be judged from the declared palette together with ordinary front, archive, or shortlist surfaces.
- Use `TraditionAtlasView` only when the reader must hold several declared derived views or interpretive qualifiers together to see why one tradition grouping, omission risk, or comparison boundary matters.
- A conforming `TraditionAtlasView` must keep the same atlas-form interpretation declaration that [[A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW - Declared-Substrate Interpretive View|A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW]] requires by value: recoverable base palette, active source set or active set result, `TypedSetViews` when several declared set views are held together, cited `SearchSpaceRef`, `OutcomeSpaceRef`, or other declared space refs, cited declared map refs such as `OutcomeMapRef`, cited qualifiers such as `SpaceMetricRef`, `TransitionRelationRef`, and `BridgeDistortionNote`, and one explicit reason why thinner `DeclaredSubstrateInterpretiveView` is insufficient here.
- It may help explain where one tradition, method family, or retained line sits relative to another, but it should not silently redefine the base palette or one derived front view or archive view.
- If one atlas view uses several typed views over the same source set, keep the active set result, any cited `SearchSpaceRef`, `OutcomeSpaceRef`, or other declared space ref, and any `BridgeDistortionNote` recoverable instead of letting `TraditionAtlasView` hide those choices.
- Treat the atlas layer as optional neighboring interpretation, not as ordinary palette-first core. Use `SpaceMetricRef` or `TransitionRelationRef` only when one declared comparison, reachability, transition, or cross-scale state-change claim actually depends on that formal support; otherwise leave them unstated.
- Use `OutcomeMapRef` only when the atlas must show how one declared set result maps into one outcome-side or effect-side declared space/ref; it does not turn the palette, front, archive, or shortlist into that outcome-side declared space/ref.
- If one atlas reading would materially change the base source-to-outcome relation or distortion posture, reopen the substrate declaration instead of treating that change as one local [[G.2 - SoTA Harvester & Synthesis|G.2]] convenience.
- If one thinner `DeclaredSubstrateInterpretiveView` already keeps the question legible, prefer that thinner interpretation form and leave atlas specialization unused.
- `SearchSpaceRef` and `OutcomeSpaceRef` doctrine, transition-aware novelty, metric-transfer loss, and cross-scale geometry belong to a heavier formal layer: keep them outside ordinary palette-first use unless the current comparison, reachability, transition, or multilevel claim explicitly needs them, and do not pull them in merely because one richer comparative reading is mathematically available.
- If no declared atlas view is needed, stay with the simpler palette-first and declared-derived-view surfaces.
- Different atlas views may rely on different declared spaces, metrics, bridges, or transition supports; keep that plurality visible rather than forcing one geometry monoculture across every neighboring view.
- If several mathematical traditions remain plausible, keep that plurality visible rather than pretending the atlas already fixes one final formalism.
- If the question is naming-side only, use [[F.18 - Local‑First Unification Naming Protocol|F.18]] for that wording choice rather than letting atlas-form interpretation language carry the naming decision by itself.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:5 - Archetypal Grounding (System / Episteme)

| Template element   | `U.System` illustration                                                                                                                                                                                                                                                  | `U.Episteme` illustration                                                                                                                                                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Tell**           | A safety engineering team needs to choose a control stack across multiple engineering “schools” (robust control, learning‑based control, formal verification), under a declared operational context and a concrete `entityOfConcern` (the vehicle + operating envelope). | A research group must synthesize SoTA on “decision quality” across competing lineages (causal decision theory, evidential variants, bounded rationality, and active‑inference‑style formalisms), each with distinct evidence norms and semantics.       |
| **Show (failure)** | The team merges terms across contexts, treats incompatible test protocols as comparable, and collapses multiple partially ordered trade‑offs into one unqualified score. The resulting design cannot explain why a later safety review disagrees.                        | The group produces a single “best” metric of decision quality and retrofits definitions to fit it. Later, conflicting claims cannot be traced because evidence anchors and crossing losses were never made explicit.                                    |
| **Show (repair)**  | A conformant [[G.2 - SoTA Harvester & Synthesis|G.2]] pack keeps parallel Claim Sheets per `Tradition`, publishes explicit alignment/loss notes where reuse is attempted, and emits hand‑offs so CHR/CAL/selection can be authored without re‑inventing semantics.                                          | A conformant [[G.2 - SoTA Harvester & Synthesis|G.2]] pack preserves plural claims, publishes explicit bridge‑backed alignment where justified, represents indicators as families/variants, and makes evidence anchors and freshness windows visible so downstream re‑audits are possible. |

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:6 - Bias-Annotation (informative)

Lenses tested: **Gov**, **Arch**, **Onto/Epist**, **Prag**, **Did**.

* **Selection bias (Gov/Onto).** Any harvesting protocol can over‑represent certain venues, languages, or evidence styles.
  *Mitigation:* pluralism floor + explicit `CorpusLedger` + explicit protocol pins.

* **Consolidation bias (Onto/Epist).** Pressure to “merge” lineages can erase incompatible commitments.
  *Mitigation:* keep Claim Sheets disjoint by default; require explicit alignment proof for fusion; preserve loss notes.

* **Recency bias (Prag).** Overweighting newest papers can hide durable backbone results; underweighting them misses SoTA drift.
  *Mitigation:* publish freshness windows and make them RSCR‑relevant.

* **Didactic bias (Did).** Micro‑examples can steer interpretation toward familiar domains.
  *Mitigation:* require heterogeneous substrates and explicit [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] anchors.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:7 - Conformance Checklist (normative) — **CC‑G2**

| ConformanceId             | Requirement                                                                                                                                                                                                                                                                                                                                        | Purpose / Notes                                                                     |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **CC‑G2‑CoreRef**         | A conforming [[G.2 - SoTA Harvester & Synthesis|G.2]] artefact **MUST** satisfy the **effective** core obligations declared by the `GCoreLinkageManifest` in `G.2:4.1` (per [[G.Core - Part G Core Invariants|G.Core]] Expansion rule).                                                                                                                                                                                 | Phase‑2 bridge clause: ensures universal invariants are not redefined inside [[G.2 - SoTA Harvester & Synthesis|G.2]]. |
| **CC‑G2‑Pluralism‑1**     | A conforming pack **MUST** include at least **two** `Tradition` lineages and at least **three** distinct declared `U.BoundedContext` entries across the corpus.                                                                                                                                                                                        | Prevents single‑lineage “SoTA” from masquerading as synthesis.                      |
| **CC‑G2‑Ledger‑1**        | A conforming pack **MUST** include `G.2a CorpusLedger` with inclusion/triage status and explicit rationale hooks per entry.                                                                                                                                                                                                                        | Makes discovery/triage auditable.                                                   |
| **CC‑G2‑FlowRecord‑1**    | A conforming pack **MUST** include `G.2h FlowRecord` that traces identification → screening → eligibility → included at a minimum granularity sufficient to reproduce the corpus boundary.                                                                                                                                                         | Prevents “mystery inclusion” and supports refresh.                                  |
| **CC‑G2‑ClaimSheets‑1**   | For each included `Tradition`, a conforming pack **MUST** include a `ClaimSheetId` that declares `U.BoundedContext`, `entityOfConcern`, evidence anchors, and freshness notes; it **MUST NOT** fuse cross‑`Tradition` claims by default.                                                                                                                 | Keeps plurality explicit and prevents hidden crossings.                             |
| **CC‑G2‑Palette‑1**       | A conforming pack **MUST** export `SoTA_Set@CG‑Frame` and `SoTAPaletteDescription` as citable views (via `SoTA_SetId`, `SoTAPaletteDescriptionId`) and ensure both are reconstructible from pack components by id (no hidden extra structure).                                                                                                      | Prevents downstream scraping of prose; keeps “M2 output” explicit.                  |
| **CC‑G2‑Palette‑2**       | If the pack exports one derived tradition view such as `TraditionFront` or `TraditionArchive`, it **MUST** keep `SoTAPaletteDescription` explicit as the default base palette, keep that derivation recoverable, and cite the declared `Q` or reachability/coverage rule that disciplined that view. Derived tradition views **MUST NOT** silently replace the palette's default meaning. | Keeps non-default tradition views recoverable without redefining palette-first semantics. |
| **CC‑G2‑AtlasInterpretation‑1**  | If the pack exports `TraditionAtlasView`, it **MUST** satisfy the same interpretive-view declaration required by [[A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW - Declared-Substrate Interpretive View|A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW]]: keep the base palette and active source set or active set result recoverable, name `TypedSetViews` when several declared set views are held together, cite any active `SearchSpaceRef`, `OutcomeSpaceRef`, or other declared space refs, cite any active `OutcomeMapRef`, `SpaceMetricRef`, `TransitionRelationRef`, or `BridgeDistortionNote` only when they do real explanatory work, state why thinner `DeclaredSubstrateInterpretiveView` is insufficient here, and **MUST NOT** use atlas form when palette-first or thinner `DeclaredSubstrateInterpretiveView` is sufficient. | Keeps the [[G.2 - SoTA Harvester & Synthesis|G.2]] specialization at least as constraining as the general `DeclaredSubstrateAtlasView` declaration and preserves space-role recoverability. |
| **CC‑G2‑entityOfConcernMap‑1** | A conforming pack **MUST** include `G.2g entityOfConcern Map`, mapping (at minimum) each load‑bearing claim family and each minted/evolved public id to `entityOfConcern := ⟨GroundingHolon, ReferencePlane⟩`, and citing the relevant `ClaimSheetId` and evidence anchors ([[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] and/or [[G.6 - Evidence Graph & Provenance Ledger|G.6]] paths when used).                                         | Keeps plane/holon boundaries explicit and citable.                                  |
| **CC‑G2‑Alignment‑1**     | Any cross‑`Tradition` consolidation **SHALL** be presented as either (i) disjoint parallel claims with explicit divergence, or (ii) an explicitly justified alignment proof; any reuse across `Tradition` boundaries **MUST** use explicit crossing bundles per `CC‑GCORE‑CROSS‑1` (delegation).                                                  | Prevents silent semantic leakage.                                                   |
| **CC‑G2‑GammaSynth‑1**    | If the pack asserts **fusion or substitution** across sources or across `Tradition` records (not merely “parallel divergent claims”), it **MUST** emit `GammaEpistSynthId` records satisfying `G.2:Ext.GammaEpistSynthesis` (provenance union + explicit alignment refs + assurance tuple refs). If no fusion or substitution is asserted, the pack **SHALL** state so explicitly. | Restores the load‑bearing synthesis artefact (alias: `G.2‑F`) without shadow specs. |
| **CC‑G2‑Inventory‑1**     | A conforming pack **MUST** include `G.2c OperatorAndObjectInventory`, sufficient for downstream CHR/CAL authoring to begin without re‑harvesting terms.                                                                                                                                                                                            | Ensures the pack is actionable.                                                     |
| **CC‑G2‑Inventory‑2**     | `G.2c OperatorAndObjectInventory` entries **MUST** be treated as **stubs** for downstream authoring: they **MUST NOT** embed acceptance thresholds or claim legality decisions locally. If an entry is not a citation of an already governed CHR/CAL artefact, it **MUST** be explicitly marked as `stub` (typing/lawfulness `TBD`) and **MUST NOT** be used as if lawful. Legality/threshold semantics are governed by [[G.3 - CHR Authoring for a CG‑Frame- Characteristics, Scales, Levels, Coordinates|G.3]] for CHR and [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]] for CAL via explicit ids/pins. | Prevents “shadow CHR/CAL” and preserves lawfulness discipline without redefining it locally. |
| **CC‑G2‑MeasurementLawful‑1** | If any inventory entry is presented as **non‑stub** (i.e., already lawful/typed), the pack **MUST** cite the governing lawfulness discipline (e.g., `A.17–A.19/C.16` as applicable) and provide the minimal evidence anchors needed to justify that typing claim.                                                                                      | Prevents “quietly lawful” measurement claims inside the harvester pack.             |
| **CC‑G2‑MicroExamples‑1** | For every load‑bearing claim family, a conforming pack **MUST** include **at least two** worked micro‑examples on **heterogeneous substrates**, each with explicit [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] carrier anchors, declared context + `entityOfConcern`, and an assurance tag (`TA`/`VA`/`LA`, where applicable).                                                          | Makes the synthesis teachable and anchor‑grounded.                                  |
| **CC‑G2‑UTS‑1**           | If the pack proposes or evolves any public ids, it **MUST** publish UTS proposals *(Name Cards + MDS where applicable)* and cite them via `UTSRowId[]`, satisfying `CC‑GCORE‑UTS‑1` (delegation).                                                                                                                                               | Keeps naming and evolution disciplined.                                             |
| **CC‑G2‑Families‑1**      | SoS indicators and candidate evaluation constructs **SHALL** be represented as **families/variants** (windows/constraints/assumptions) **with explicit Acceptance branch structure per variant** (branch ids/labels only), not as single unqualified scalars; any scalar summary **MAY** be included only as report‑only unless explicitly promoted by governing patterns. *(Set-return discipline is delegated to `CC‑GCORE‑SET‑1`.)* | Prevents covert scalarization and keeps acceptance governed by downstream patterns.                |
| **CC‑G2‑HandOff‑1**       | A conforming pack **MUST** emit hand‑off manifests to [[G.3 - CHR Authoring for a CG‑Frame- Characteristics, Scales, Levels, Coordinates|G.3]], [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]], and [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] that cite pack components by id and identify which families/operators are intended for downstream formalisation or registry entry.                                                                                                                                   | Prevents downstream re‑authoring and drift.                                         |
| **CC‑G2‑CoverageGate‑1**  | The pack **MUST** declare `FamilyCoverageFloorK` and enforce it as a harvesting gate. It **MUST** either (i) specify `k` explicitly in an explicit `HarvestPolicyRef`, or (ii) use the pattern‑local default rule governed by `CC‑G2‑CoverageGate‑1`. *Default rule (pattern-local):* `k=3`. If the gate fails, the pack **MUST** (a) record the repair iteration in `FlowRecord`, and (b) broaden the search radius (new venues/corpora/contexts/traditions) rather than silently weakening the gate; if an exploration policy is used for this broadening, it **MUST** be pinned as a policy id/ref. | Makes “coverage floor” explicit and prevents “silent narrowing” under failure.      |
| **CC‑G2‑DistanceGate‑1**  | If a diversity‑by‑distance gate is used, the pack **MUST** pin `DistanceDefRef.edition` and the declared threshold (δ), and treat edits as RSCR‑relevant per `CC‑GCORE‑TRIG‑*` (delegation). If no such gate is used, the pack **SHALL** explicitly state that it is not used.                                                                     | Avoids implicit distance defaults and improves refreshability.                      |
| **CC‑G2‑RSCR‑1**          | A conforming pack **MUST** emit canonical `RSCRTriggerKindId` causes (not free text) for edits to evidence surfaces, name/tokenization surfaces (e.g., UTS proposals/aliases), crossings, planes, edition pins, and harvesting policy pins (`HarvestPolicyRef`), per `CC‑GCORE‑TRIG‑1…TRIG‑4` (delegation).                                                                                      | Keeps refresh reason codes stable and typed.                                        |
| **CC‑G2‑Ext‑GammaEpist‑1** | If `G.2:Ext.GammaEpistSynthesis` is used (i.e., any fusion/substitution is asserted), the pack **SHALL** expose the required pins listed in that extension and **SHALL NOT** redefine `Γ‑fold/Φ/penalty` semantics locally (cite governing definitions by delegation).                                                                                       | Keeps synthesis auditable without creating shadow specs.                            |
| **CC‑G2‑Ext‑HarvestProtocols‑1** | If `G.2:Ext.HarvestProtocols` is used, the pack **SHALL** expose the required pins/criteria ids listed in that extension and **SHALL NOT** redefine evidence/quality semantics outside the declared protocol profile.                                                                                                                            | Keeps protocol variation explicit and separately citable.                           |
| **CC‑G2‑Ext‑DHC‑1**       | If `G.2:Ext.DHCAlignmentHooks` is used, the pack **SHALL** (a) expose the required pins listed in that extension, including `DHCSenseCellId[]`, and (b) declare the unit/constraint pins required by [[C.21 - Field Health & Structure (Discipline-CHR)|C.21]] (e.g., `bridges_per_100_DHC_SenseCells`, `CL_min=2`) without redefining their semantics locally (governing pattern: [[C.21 - Field Health & Structure (Discipline-CHR)|C.21]]).                                                             | Keeps DHC extension pins auditable and non‑shadowing.                              |
| **CC‑G2‑Ext‑NQD‑1**       | If `G.2:Ext.NQDAnnex` is used, the pack **SHALL** expose the required pins/editions/policies listed in that extension and **SHALL NOT** redefine QD semantics locally.                                                                                                                                                                             | Keeps QD/OEE extension pins replayable and non‑shadowing.                          |
| **CC‑G2‑Ext‑Interop‑1**   | If `G.2:Ext.InteropForms` is used, the pack **SHALL** expose the required interop pins and **SHALL NOT** introduce alternative legality/acceptance semantics.                                                                                                                                                                                      | Prevents “foreign gate” shadowing.                                                  |

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:8 - Common Anti‑Patterns and How to Avoid Them

* **AP‑G2‑1: “One true SoTA score.”**
  **Avoid:** selecting a single unqualified scalar metric as “the” SoTA.
  **Do instead:** represent evaluation constructs as families/variants; keep partial orders set‑returning (delegated).

* **AP‑G2‑2: Fusion without explicit alignment proof.**
  **Avoid:** merging rival `Tradition` claims into one statement “by common sense.”
  **Do instead:** preserve parallel Claim Sheets; if consolidation is required, publish explicit alignment proof or keep a divergence record.

* **AP‑G2‑3: Hidden protocol drift.**
  **Avoid:** changing the harvesting protocol (inclusion criteria, windowing, screening rubric) without pins.
  **Do instead:** pin harvesting policy/profile ids and treat changes as RSCR‑relevant.

* **AP‑G2‑4: Unanchored pedagogy.**
  **Avoid:** micro‑examples without carriers (they become folklore).
  **Do instead:** bind micro‑examples to [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] anchors and declare `entityOfConcern`.

* **AP‑G2‑5: Atlas by default.**
  **Avoid:** writing as if every tradition comparison or NQD/OEE note needs `TraditionAtlasView`, or as if atlas wording renames the palette itself.
  **Do instead:** keep the base palette and derived front, archive, or shortlist explicit; use atlas form only when several declared views or interpretive qualifiers must be held together, and prefer thinner `DeclaredSubstrateInterpretiveView` when that is enough.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:9 - Consequences

* **Positive:** Downstream CHR/CAL/dispatch work becomes faster and less ambiguous because the pack is citable and structured.
* **Positive:** Plurality is preserved while still enabling disciplined comparability through explicit crossings.
* **Positive:** Refresh becomes tractable because pins and typed causes exist.
* **Negative:** Adds authoring overhead (ledger, flow record, micro‑examples, explicit pins).
* **Negative:** Requires governance discipline to prevent the pack from becoming an uncontrolled “everything bucket”.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:10 - Rationale

SoTA synthesis is a bottleneck for new `CG‑Frame` work: without a disciplined harvest, downstream formalization (CHR/CAL) and operational selection ([[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]]) either (i) inherit hidden semantic collisions, or (ii) re‑invent incompatible “mini‑standards.”
[[G.2 - SoTA Harvester & Synthesis|G.2]] resolves this by treating SoTA work as a **publishable kit**: explicit plurality, explicit crossings, explicit evidence anchors, and explicit hand‑offs.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:11 - SoTA-Echoing (informative)

This pattern aligns its *method options* (via Extensions and authoring practice) with widely used post‑2015 SoTA practices, while keeping FPF’s semantics stable and id‑based:

1. **PRISMA 2020 reporting discipline** (Page et al., 2021)
   *Status:* **Adopt (adapted)** — we adopt the idea of a transparent screening trail as `FlowRecord`, but keep it notation‑independent and concept‑level.

2. **Living systematic reviews** (Elliott et al., 2017 and subsequent living‑review practice)
   *Status:* **Adopt (as optional protocol family)** — the “living” stance is expressed as a harvesting protocol profile (Extension), with explicit freshness windows and RSCR‑relevant change causes.

3. **AMSTAR 2 critical appraisal** (Shea et al., 2017)
   *Status:* **Adapt** — we adapt the idea of structured quality appraisal into Claim Sheet evidence cues, without turning it into a single scalar rating.

4. **Science of Science synthesis** (Fortunato et al., 2018)
   *Status:* **Adopt (as content discipline)** — SoS indicators are treated as families/variants and wired as citable artefacts, not as a single “score”.

5. **Disruption / team‑structure indicators** (Wu, Wang & Evans, 2019 and follow‑on work)
   *Status:* **Adopt (as exemplar family)** — useful as an example of a SoS‑indicator family with material dependence on windowing and corpus definition.

6. **Quality‑Diversity and open‑ended generation** (e.g., Fontaine et al., 2020 for CMA‑ME; Wang et al., 2019 for POET)
   *Status:* **Adopt (as optional annex with explicit pin declarations)** — when QD/OEE is relevant for the `CG‑Frame`, we include generator/method family cards and pin the required edition/policy surfaces via `G.2:Ext.NQDAnnex`, without embedding those semantics into the core pack.

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:12 - Relations

* **Builds on:**

  * [[G.Core - Part G Core Invariants|G.Core]] (core invariants, typed RSCR causes, Default Governing Definition Index)
  * [[E.8 - FPF Authoring Conventions & Style Guide|E.8]] (pattern template discipline)
  * [[E.10 - Unified Lexical Rules for FPF|E.10]] (lexical/ontological rules; strict distinction; kind‑suffix discipline)
  * [[E.19 - Pattern Quality Gates- Review and Refresh Profiles|E.19]] (conformance discipline)
  * [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] (provenance anchors / carriers)
  * [[A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW - Declared-Substrate Interpretive View|A.19.DECLARED-SUBSTRATE-INTERPRETIVE-VIEW]] (generic interpretive-view and atlas discipline when `TraditionAtlasView` is used)
  * [[A.6.P - Relational Precision Restoration (RPR) - Kind‑Explicit Qualified Relation Discipline|A.6.P]] (space/view/publication precision restoration when palette/support claims collapse)
  * [[B.3 - Trust and Assurance Calculus (F-G-R with Congruence)|B.3]] (trust, freshness/decay as cited governing patterns)
  * [[F.9 - Alignment & Bridge across Contexts|F.9]] (bridges and CL as cited governing patterns)
  * [[F.17 - Unified Term Sheet (UTS)|F.17]] (UTS publication discipline; via delegation)
  * [[G.0 - Frame Standard and Comparability Governance - CG‑Spec|G.0]] (CG‑Spec legality gate; cited when legality surfaces are referenced)
  * [[G.6 - Evidence Graph & Provenance Ledger|G.6]] (EvidenceGraph / path citation surfaces when used)

* **Used by:**

  * [[G.1 - CG‑Frame‑Ready Generator|G.1]] (generator chassis consumes harvested SoTA sets)
  * [[G.3 - CHR Authoring for a CG‑Frame- Characteristics, Scales, Levels, Coordinates|G.3]] (CHR authoring consumes operator/object inventory and claim sheets)
  * [[G.4 - CAL Authoring for a CG-Frame- Operators, Acceptance Clauses, Evidence Wiring|G.4]] (CAL authoring consumes operator stubs, acceptance branch scaffolding)
  * [[G.5 - Multi‑Method Dispatcher & MethodFamily Registry|G.5]] (registry/dispatch consumes MethodFamily/GeneratorFamily cards)
  * [[G.10 - SoTA Pack Shipping|G.10]] (shipping cites the pack as payload)
  * [[G.11 - Telemetry-Driven Refresh & Decay Orchestrator|G.11]] (refresh orchestration can re‑invoke harvest via typed causes)

* **Relates to:**

  * [[G.13 - External Interop Hooks for SoTA Discipline Packs (conceptual)|G.13]] (interop surfaces when external indices are used)
  * [[F.18 - Local‑First Unification Naming Protocol|F.18]] (naming-side support wording when the question is label choice rather than synthesis geometry)

## [[G.2 - SoTA Harvester & Synthesis|G.2]]:End

---
