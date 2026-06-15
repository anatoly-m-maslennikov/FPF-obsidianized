---
type: "fpf-pattern"
context:
  - "FPF"
page_type: "fpf-pattern"
mode: "canonical-generated"
fpf_id: "A.2.9"
title: "`U.SpeechAct` (Communicative Work Object)"
part: "[[FPF - Part A - Kernel Architecture Cluster]]"
parents:
  - "[[FPF - Part A - Kernel Architecture Cluster]]"
source_file: "FPF-Spec.md"
source_lines:
  - 5585
  - 5876
status: "Stable"
normativity: "Normative (unless explicitly marked informative)"
terms:
  - "U.SpeechAct"
  - "U.Work"
  - "U.Work.kind"
generated_on: "2026-06-15"
generated: true
---


> **Type:** Definitional (D)
> **Status:** Stable
> **Normativity:** Normative (unless explicitly marked informative)
> **Placement:** Part A → **[[A.2 - Role Taxonomy|A.2]] Roles & Agency Kernel**
> **Refines:** [[A.2 - Role Taxonomy|A.2]] (Role Taxonomy)
> **Builds on:** [[A.2.1 - U.RoleAssignment- Contextual Role Assignment|A.2.1]] (RoleAssignment), [[A.2.6 - Unified Scope Mechanism (USM)- Context Slices & Scopes|A.2.6]] (`Γ_time` / windows), [[A.7 - Strict Distinction (Clarity Lattice)|A.7]] (EntityOfConcern / Description episteme / carrier), [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] (SCR/RSCR carrier discipline), [[A.15.1 - U.Work|A.15.1]] (`U.Work`)
> **Purpose (one line):** Provide a minimal, lintable kernel object for **communicative enactments** (approvals, authorizations, revocations, notices, declarations, publications) as **`U.Work`**, explicitly separating the **act** from its **utterance descriptions** and **evidence carriers**, so governance and gating can cite `SpeechActRef` without “contract soup” or episteme‑as‑agent mistakes.

> FPF already treats communicative acts as observable events used in role-state checklists and grounding (“presence of act: AuthorizationSpeechAct exists…”, and `U.SpeechAct` is listed as an observable basis for state assertions).
> The spec’s micro-examples and conformance gates distinguish **communicative Work** (“performed a SpeechAct”) from **operational Work** (“executed Work”) while keeping both inside `U.Work` (cf. CC‑A15‑10 GateSplit).
> [[F.18 - Local‑First Unification Naming Protocol|F.18]] currently frames `U.SpeechAct` as the “utterance” label in the promise/utterance/commitment triad; [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]] keeps that as **naming intuition** while putting the ontology and conformance discipline in Part A where it can be linted and reused.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:1 — Problem frame

FPF repeatedly needs to reference “someone said/did the approving/authorizing/declaring thing”:

* Role eligibility and enactability checklists often depend on the **presence of an approval/authorization act** within a freshness window.
* Governance patterns and boundary writing ([[A.6 - Signature Stack & Boundary Discipline|A.6]] stack) need **provenance**: “this obligation/commitment/permission was instituted by *that* act”.
* Operational patterns need auditable **notices** (“depletion notice”, “override invoked”) whose existence and timing matter.

Without a **first‑class kernel object** for such communicative events, authors tend to:

* attribute agency to descriptions (“the spec approves…”, “the interface guarantees…”),
* collapse “utterance text” and “speech act event”,
* leave provenance dangling as “if modeled”,
* encode gates as prose obligations, or treat obligations as gates.

This pattern makes “speech act” an explicit, queryable **Work‑kind** with clear boundaries to `U.Commitment` and to utterance surfaces.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:2 — Problem

How can FPF represent communicative enactments so that:

1. **Agency is explicit:** a concrete accountable subject performs the act (role/role‑enactor), not a document/spec/interface.
2. **The act is locatable in time:** the act has an explicit Window (and thus freshness can be evaluated).
3. **The act is locatable in meaning:** the act is recognized inside a declared **bounded context** (the `U.Work` judgement context), not via `U.ClaimScope` (which expresses applicability of claims/commitments, not the judgement context for Work occurrences).
4. **The act is auditable:** it has at least one declared utterance description and/or evidence carrier when used for gating or governance.
5. **Institutional effects are linkable:** the act can institute (or update/revoke) commitments, role assignments, statuses, etc., by reference.
6. **Ambiguity is handled pragmatically:** the model supports multi‑function / multi‑party communication without requiring full linguistic pragmatics.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:3 — Forces

| Force                  | Tension                                                                                                                 |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Minimality             | Needs to be light enough for routine modeling and linting; not a full pragmatics or legal-contract system.              |
| Auditability           | If used as a gate, it must be evidence-backed; but not all communicative acts are equally observable or retainable.     |
| Context locality       | Meaning and “institutional force” are context-local; cross-context reuse must remain explicit (Bridge-only discipline). |
| Multi-party reality    | Many real boundaries are multiparty (protocols, organizations); dyadic “speaker-hearer” is too narrow.                  |
| Multi-function reality | One utterance can carry multiple recognizable functions; “one act = one force” is often false.                          |
| Separation discipline  | Must preserve [[A.7 - Strict Distinction (Clarity Lattice)|A.7]] splits: **act object** ≠ **utterance description** ≠ **carrier/traces**.                              |

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:4 — Solution

`U.SpeechAct` is a **kernel Work object**: a recorded communicative enactment performed by an accountable role‑enactor within a bounded context, optionally addressed to others, that is **recognized** (in that context) as updating an information and/or governance state. The act is **not** the utterance text; it points to utterance descriptions and evidence carriers.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:4.1 — Normative definition

A **`U.SpeechAct`** is a **`U.Work`** occurrence whose primary (intended) effect is **communicative**: it places an utterance into a context in a way that is recognized by that context’s institutional semantics (policies, procedures, protocol rules) as potentially:

* asserting/informing,
* requesting/directing,
* promising/committing (as an instituting act),
* declaring/authorizing/revoking (status-changing acts),
* notifying (event announcement relevant for downstream work).

Per [[A.7 - Strict Distinction (Clarity Lattice)|A.7]], `U.SpeechAct` is an **object/event**; its **utterance descriptions** are descriptions (epistemes/spec clauses/messages‑as‑content), and its **carriers** are utterance carriers, publication carriers, or traces that support observation and audit. *(Note: “Surface” is reserved for MVPK publication/interoperability surfaces; do not use it here.)*

Whether a given `actType` institutes commitments/permissions/status changes is **entirely context‑policy dependent**. Absent an explicit policy, treat a `U.SpeechAct` as a communicative Work occurrence with observable provenance only; do not infer deontic bindings from the act by default.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:4.2 — Minimal structure (normative)

A conforming `U.SpeechAct` **SHALL** be representable by the following minimal record (field names are illustrative; the constraints are normative):

```
U.SpeechAct <: U.Work

Invariant: U.Work.kind = Communicative

U.SpeechAct ::=
  U.Work
  & {
      actTypes: set<SpeechActTypeRef>,               // ≥1 act types (supports multi-function)
      addressedTo: optional<set<AddresseeRef>>,      // optional: who is addressed / audience
      utteranceRefs: optional<set<DescriptionRef>>,  // where the utterance description is stated or recorded ([[A.7 - Strict Distinction (Clarity Lattice)|A.7]]: Description)
      carrierRefs: optional<set<CarrierRef>>,        // evidence carriers/traces ([[A.7 - Strict Distinction (Clarity Lattice)|A.7]]: Carrier; use [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]] when evidentiary)
      institutes: optional<InstitutedEffects>,       // references to objects/claims instituted/updated by this act
      notes: optional<InformativeText>               // explicitly informative
    }

DescriptionRef ::=
  ClaimIdRef | EpistemeRef
  // Pointer to an utterance description (e.g., spec clause claim ID, a policy episteme, a message-content episteme).

SpeechActTypeRef ::=
  ContextLocalTokenRef
  // Must be defined/recognized in the Work’s judgement context (bounded context).

AddresseeRef ::=
  PartyRef | RoleRef | RoleAssignmentRef

InstitutedEffects ::=
  {
    commitments: optional<set<CommitmentIdRef>>,
    roleAssignments: optional<set<RoleAssignmentRef>>,
    statusClaims: optional<set<ClaimIdRef>>,         // e.g., “StandardStatus=Approved” if modeled as claims
    other: optional<set<ObjectIdRef>>
  }
```

**Normative constraints:**

* **(SA‑C0) Work conformance applies.** Because `U.SpeechAct <: U.Work`, a speech‑act record **MUST** satisfy `U.Work` conformance ([[A.15.1 - U.Work|A.15.1]]), including the required anchors (`isExecutionOf`, `performedBy`, `executedWithin`, `window`, and state‑plane / judgement‑context anchoring). A speech act **MUST** have at least one `affected` referent (the thing it is *about/updates*), even if it is purely governance‑state.
* **(SA‑C1) PerformedBy must be an accountable actor.** `performedBy` **MUST** resolve to a `RoleAssignmentRef` whose holder is an accountable system or party in the named scope. It **MUST NOT** resolve to a specification episteme, interface-description episteme, or document-carried episteme.
* **(SA‑C2) ActTypes are required and context-local.** `actTypes` **MUST** contain at least one `SpeechActTypeRef` recognized in the Work’s judgement context (local meaning). Free‑text verbs are nonconformant unless registered as a context token.
* **(SA‑C3) Time honesty.** `window` **MUST** be explicit (or inherited from the parent `U.Work` record) so freshness rules can be evaluated.
* **(SA‑C4) If used for gating/audit, it must be observable.** If a speech act is used as a checklist criterion, guard condition, or provenance hook for a `U.Commitment`, the model **SHALL** include at least one observable handle: `utteranceRefs` and/or `carrierRefs`. When the act is used as evidence, at least one carrier reference **SHOULD** be SCR/RSCR‑resolvable per [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]].
* **(SA‑C5) Institutional effects are references, not paraphrases.** When the act is intended to institute/update commitments, role assignments, or statuses, `institutes.*` **SHOULD** reference the corresponding object IDs/claim IDs rather than restating content.
* **(SA‑C6) Cross-context use is Bridge-only.** If a `SpeechActRef` is used for checking/gating/provenance in a **different bounded context** than the act’s judgement context, the referencing object **MUST** satisfy the spec’s cross-context discipline by citing an explicit Bridge/policy that licenses the interpretation (and surfacing congruence vs loss where applicable), rather than assuming equivalence by label.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:4.3 — `SpeechActRef` discipline (normative)

A **`SpeechActRef`** is a reference to `U.SpeechAct.id`.

* If another object (e.g., `U.Commitment.source.speechActRef`) cites a `SpeechActRef`, the referenced `U.SpeechAct` **MUST** satisfy **SA‑C0…SA‑C4** (and SA‑C6 when used cross‑context).
* A `SpeechActRef` **MUST NOT** be replaced by an `EpistemeRef` (“see the document”) when provenance is needed; the episteme is an utterance description, not the act.
* If a system cannot record a full `U.SpeechAct`, it may record a **stub** that still satisfies **SA‑C0…SA‑C4** (minimal `actTypes`, performer, judgement context, window, `affected`, plus at least one observable handle). When a required `U.Work` anchor is unknown, the stub **MUST** use an explicit placeholder (e.g., an “AdHocCommunication” MethodDescription) rather than omitting the field.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:4.4 — Separation rules with `U.Commitment` and `U.PromiseContent` (normative)

1. **Speech act is not the deontic binding.**
   A speech act may **institute** a `U.Commitment`, but the deontic relation itself is the `U.Commitment` object ([[A.2.8 - U.Commitment (Deontic Commitment Object)|A.2.8]]). Do not encode obligations/permissions inside `U.SpeechAct` as prose; instead, create/point to `U.Commitment` IDs in `institutes.commitments`.

2. **Speech act is not the service promise clause.**
   `U.PromiseContent` / promise contents are promise content; a speech act may be the act of offering/issuing that promise, but the promise content lives in the service/promise content objects and is referenced from the resulting commitments.

3. **Speech act is not the carrier.**
   A “signed approval PDF”, “ticket record”, “Slack message”, or “API call log” is a carrier (and may carry an episteme as utterance content); the speech act is the Work occurrence that produced/issued it.

4. **Publishing a spec is not a commitment by default.**
   **Default interpretation rule (normative).** A conformant model/interpreter **MUST NOT** infer `U.Commitment` objects solely from `Publish`/`Approve` speech acts. Publication MAY institute publication/status claims (e.g., “Published”, “Approved”, “Deprecated”), but any obligations/permissions on implementers/operators/providers **MUST** be modeled explicitly as `U.Commitment` objects ([[A.2.8 - U.Commitment (Deontic Commitment Object)|A.2.8]]). If a Context defines a policy that maps publication acts to commitment-instituting effects (e.g., a named `SpecPublicationPolicy@Context`), that policy **MUST** be named and cited where the implication is used.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:4.5 — Multi-function and multi-party support (normative)

* **Multi-function:** `actTypes` is a **set**. If one utterance performs multiple recognizable acts (e.g., “approve + instruct + warn”), the model may either:

   * represent one `U.SpeechAct` with multiple `actTypes` entries, or
   * represent multiple `U.SpeechAct` records that share the same `carrierRefs/utteranceRefs`.
   In either case, institutional effects must remain referenceable (SA‑C5).

* **Multi-party:** `addressedTo` is a set and may include roles/parties/assignments. If addressees matter for validity (e.g., “approval by CAB chair to deployment bot”), they should be explicit.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:5 — Archetypal Grounding (Tell–Show–Show)

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:5.1 — Tell (universal rule)

When governance or gating depends on “someone said/did X”, model **that saying/doing** as a `U.SpeechAct` (a Work occurrence), and keep the utterance text and carriers separate. If the saying/doing creates obligations, model those obligations as `U.Commitment` objects instituted by the speech act.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:5.2 — Show #1 (system archetype: change-control approval gates a deployment)

**Situation (messy prose):**
“Change is approved, so the pipeline may deploy.”

**Conformant modeling sketch:**

* `U.SpeechAct SA-Approve-4711`

  * `actTypes = {SpeechActTypeRef(Approval@ChangeControl)}`
  * `performedBy = RoleAssignmentRef(CAB_Chair as ApproverRole@ChangeControl)`
  * `isExecutionOf = MethodDescriptionRef(ChangeApprovalProcedure_v3)`
  * `executedWithin = ChangeControlBoardSystem`
  * `window = [t,t]`
  * `affected = {ChangeRequestId(4711), WorkRef(Deploy-4711)}`
  * `utteranceRefs = {EpistemeRef(ChangeTicket#4711)}`
  * `carrierRefs = {CarrierRef(TicketSystemRecord#4711)}`
  * `institutes.commitments = {CommitmentIdRef(D-Deploy-Authorized)}`

* `U.Commitment D-Deploy-Authorized`

  * `subject = RoleAssignmentRef(OpsBot#DeployerRole:CD_Pipeline_v7)`
  * `modality = MAY` (permission to enact)
  * `referents = {A-Gate-Deploy-4711}`
  * `source.speechActRef = SA-Approve-4711`

* Gate predicate `A-Gate-Deploy-4711` may include:
  `exists SpeechAct(type=Approval, affected includes ChangeRequestId(4711), performedBy role=ApproverRole, within 90d)`.

This preserves:

* act vs text vs carrier,
* explicit performer,
* time window for freshness,
* explicit provenance from commitment back to the instituting act.

### [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:5.3 — Show #2 (episteme archetype: publishing a spec edition without making the spec an agent)

**Situation (anti-pattern):**
“The interface spec declares MUST/SHALL requirements.”

**Conformant modeling sketch:**

* `U.SpeechAct SA-Publish-API-v12`

  * `actTypes = {SpeechActTypeRef(Publish@APISpecContext), SpeechActTypeRef(DeclareNorms@APISpecContext)}`
  * `performedBy = RoleAssignmentRef(StandardsEditor as PublisherRole@APISpecContext)`
  * `isExecutionOf = MethodDescriptionRef(SpecReleaseProcedure_v12)`
  * `executedWithin = SpecPublicationSystem`
  * `window = [t,t]`
  * `affected = {EpistemeRef(APISpec_v12)}`
  * `utteranceRefs = {EpistemeRef(APISpec_v12)}`
  * `carrierRefs = {CarrierRef(GitTag:v12), CarrierRef(SignedReleaseArtifact:v12)}`
  * `institutes.statusClaims = {ClaimIdRef(D-StdStatus-APISpec_v12-Published)}` (if modeled)

Norms live in the **published utterance surfaces** (spec clauses as L/A/D/E-classified claims), but the **act of publication** is a speech act performed by an accountable role. This avoids “the spec promises/commits” category errors while preserving auditability.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:6 — Bias-Annotation

Lenses tested: **Gov**, **Arch**, **Onto/Epist**, **Prag**, **Did**. Scope: **Kernel universal** for speech-act usage that matters for governance, eligibility, gating, provenance, and protocol boundaries.

* **Gov bias:** favors explicit accountable performers and auditable records; increases clarity but adds modeling overhead.
* **Arch bias:** optimizes evolvability by keeping institutional effects referenceable rather than embedded in prose.
* **Onto/Epist bias:** enforces act≠utterance≠carrier and prevents episteme-as-agent metaphors.
* **Prag bias:** models only what is needed for decisions/audit (not full intention/sincerity/perlocutionary psychology).
* **Did bias:** keeps the record minimal and queryable for state checklists and boundary reviews.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:7 — Conformance Checklist (normative)

1. **CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑1 (Accountable performer).** A normative `U.SpeechAct` record **MUST** identify `performedBy` as an accountable `RoleAssignmentRef` and **MUST NOT** use a specification episteme, interface-description episteme, or document-carried episteme as performer.
2. **CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑2 (ActTypes declared).** A `U.SpeechAct` record **MUST** include at least one `SpeechActTypeRef` recognized in its judgement context.
3. **CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑3 (Window explicit).** A `U.SpeechAct` record **MUST** have an explicit `window` (or inherit a window from its parent work record) so freshness and gating can be evaluated.
4. **CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑4 (Observable when used for gating/provenance).** If a speech act is cited by a checklist/guard or by `U.Commitment.source.speechActRef`, it **SHALL** have at least one `utteranceRef` or `carrierRef` that supports observation/audit in the given context; evidence‑critical uses **SHOULD** anchor at least one carrier via SCR/RSCR per [[A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]].
5. **CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑5 (Effects by reference).** If the act is intended to institute/update commitments/roles or statuses, those effects **SHOULD** be referenced in `institutes.*` by stable IDs.
6. **CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑6 (Bridge-only cross-context use).** If a `SpeechActRef` is interpreted for gating/provenance in a different bounded context than the act’s judgement context, the referencing object **MUST** cite the Bridge/policy that licenses that cross-context interpretation (no “same label implies same force”).

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:8 — Common Anti-Patterns and How to Avoid Them

| Anti-pattern                                                              | Why it fails                         | Repair                                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------ | ---------------------------------------------------------------------------------------- |
| **Episteme-as-actor** (“the spec approves/declares”)                      | assigns agency to descriptions       | represent the publishing/approving act as `U.SpeechAct(performedBy=RoleAssignment)`      |
| **Carrier-as-act** (“the signed PDF is the approval”)                     | conflates carrier with act           | model `U.SpeechAct` and point to PDF as `carrier`/`utteranceSurface`                     |
| **Free-text type** (“type=‘approved-ish’”)                                | not lintable; drifts across faces    | register `SpeechActTypeRef` in the context and use it                                    |
| **Act carries obligations** (obligations embedded as prose in speech act) | collapses act and deontic binding    | model obligations as `U.Commitment` objects instituted by the act                        |
| **Gating without window**                                                 | cannot evaluate freshness            | add explicit `window` and reference it in the guard/checklist                            |
| **Hidden multi-act** (one event silently creates multiple commitments)    | loses traceability; creates disputes | represent multi-function via `actTypes` set or multiple speech acts sharing the same carrier |

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:9 — Consequences

**Benefits**

* Makes approvals/authorizations/notices **first-class and queryable**, enabling clean RSG checklists and guard rules.
* Provides stable provenance: commitments and status transitions can cite the **instituting act** explicitly.
* Prevents recurring category errors: “documents promise”, “interfaces commit”, “logs prove”.

**Trade-offs / mitigations**

* Requires recording a small structured object for communicative events; mitigated by allowing minimal stubs that still satisfy CC‑[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]‑1…4.
* Requires context-local `SpeechActTypeRef` registration; mitigated by starting with a small set (Approve, Revoke, Publish, Notify, Authorize) and extending as needed.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:10 — Rationale

FPF already relies on communicative acts (approvals, notices, overrides) as operationally meaningful events, but without a kernel object they blur into examples, naming choices, or prose. [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]] anchors speech acts where they belong: as a **Work-kind** with explicit performer, scope, and time, and with disciplined links to utterance surfaces, carriers, and deontic bindings (`U.Commitment`).

This also improves modularity:

* **[[F.18 - Local‑First Unification Naming Protocol|F.18]]** can remain a **lexical anchor** for naming (why “SpeechAct/utterance” as a label family is useful),
* while **[[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]** carries the ontology and conformance discipline for how speech acts behave as objects and how they connect to commitments and evidence.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:11 — SoTA‑Echoing (informative; post‑2015 alignment)

> **Informative.** Alignment notes; not normative requirements.

* **Adopt — ISO 24617‑2:2020 / multi-dimensional communicative functions.** Modern dialogue‑act standards treat communicative behavior as potentially multi‑functional. [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]] mirrors this by allowing `actTypes` to be a **set** and by supporting shared carriers across multiple acts.
* **Adapt — commitment-based semantics for communication (multi-agent/protocol practice, 2015+).** A pragmatic way to avoid mental-state modeling is to track communication by its **social/institutional effects**, especially on commitments and protocol states. [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]] reflects this via `institutes.commitments` and explicit links to `U.Commitment` without modeling sincerity or intention.
* **Adopt (warning) — illocutionary pluralism in multiparty discourse (2015+).** One utterance commonly performs multiple recognizable functions. [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]] avoids the “single force” trap by permitting multi‑type acts and/or multiple acts sharing the same utterance and carriers.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:12 — Relations

**Uses / builds on**

* Uses **[[A.15.1 - U.Work|A.15.1]] (`U.Work`)** for the event/work backbone (performedBy + window + stance).
* Uses **[[A.7 - Strict Distinction (Clarity Lattice)|A.7]]** for the strict act≠description≠carrier split.
* Coordinates with **[[A.2.6 - Unified Scope Mechanism (USM)- Context Slices & Scopes|A.2.6]]** for scope/window discipline.

**Used by**

* **[[A.2.8 - U.Commitment (Deontic Commitment Object)|A.2.8]] (`U.Commitment`)** as a concrete target for `source.speechActRef` provenance.
* **[[A.2.5 - U.RoleStateGraph- The Named State Space of a Role|A.2.5]] (RSG checklists/guards)** when “presence of authorization/approval act” is a criterion.
* **[[A.6.C - Contract Unpacking for Boundaries|A.6.C]] (Contract unpacking)** as the “utterance/instituting act” hook that prevents episteme-as-agent claims and improves provenance.

## [[A.2.9 - U.SpeechAct (Communicative Work Object)|A.2.9]]:End
