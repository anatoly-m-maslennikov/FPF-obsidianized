---
type: fpf-knowledge-page
context:
  - FPF
page_type: fpf-knowledge-page
mode: canonical-generated
title: First Practical Entries
part: "[[FPF - First Principles Framework (FPF) Readme]]"
parents:
  - "[[FPF - First Principles Framework (FPF) Readme]]"
source_file: FPF-Spec.md.breaks.my.obsidian.bak
source_lines:
  - 454
  - 589
status: generated
generated_on: 2026-06-15
generated: true
---


A first practical entry is the first useful way to enter FPF from a real working project. Choose it by the project question you are trying to settle, not by the order of patterns in the specification.

The entries below are not a required sequence. They are common places where FPF can start paying rent in a project.

## 1. Develop or review architecture

Use this when you need to design, explain, review, or improve the architecture of a product, organization, technical system, document system, AI-agent setup, research program, or other thing with important internal structure.

FPF helps you ask what is being architected, which structures matter, what property of the architecture is being changed or judged, and which description, diagram, view, promise, decision, evidence, or implementation task is a different matter. It gives you language for selected structures, structural views, architecture characteristics, modularity, interfaces, scale, interlevel tensions, and architecture-changing moves.

Typical first result: a short architecture question note that says what is being architected, which structures matter, which architecture characteristic is at stake, what description or view is needed, and what decision or implementation work is still not settled by the architecture statement.

First inspect: [[00_C.30 - Grounded Architecture and Selected-Structure Adequacy|C.30]], [[00_A.22 - Structure and Structural Views (STRUCT-CAL)|A.22]], [[04_C.30.ASV - Architecture Structural View Adequacy (ASV)|C.30.ASV]], [[01_C.30.AD - Architecture Description Adequacy|C.30.AD]], [[00_C.31 - Modularity and Reusable Structure Characteristics|C.31]], [[12_A.06.M - Module Relation Repair|A.6.M]], and the relevant architecture precision-restoration patterns when wording hides the kind of structure being discussed.

## 2. Write rules, methods, and work-process documents

Use this when you need to write or review technical regulations, procedures, method descriptions, operating instructions, work-process descriptions, standards-like project documents, API documents, contracts, SLAs, protocols, permissions, or compliance wording.

FPF helps you keep the described method separate from the method itself, a plan separate from performed work, responsibility separate from permission, an interface contract separate from implementation, and a published document separate from actual execution. It can also describe chains of methods when the chain itself is the subject, while keeping actual work occurrences separate from the document that says how work should be done.

Typical first result: a cleaned method, regulation, or interface outline that names what is being governed, the method or interface being described, the roles and responsibilities involved, the expected work result, and any evidence, gate, permission, or compliance claim that the document does not yet justify.

First inspect: [[00_A.06 - Signature Stack & Boundary Discipline|A.6]], [[02_A.06.B - Boundary Norm Square (Laws - Admissibility - Deontics - Work-Effects)|A.6.B]], [[03_A.06.C - Contract Unpacking for Boundaries|A.6.C]], [[00_A.15 - Role-Method-Work Alignment (Contextual Enactment)|A.15]], [[01_A.15.01 - U.Work|A.15.1]], [[02_A.15.02 - U.WorkPlan|A.15.2]], [[03_A.15.03 - SlotFillingsPlanItem|A.15.3]], [[04_A.15.04 - Work-Relevant Source Restoration|A.15.4]], [[00_E.18 - Transformation Flow Structure|E.18]], [[01_E.18.01 - Principles-to-Work Carry-Through|E.18.1]], [[00_E.08 - FPF Authoring Conventions & Style Guide|E.8]], and [[00_E.19 - Pattern Quality Gates- Review and Refresh Profiles|E.19]].

## 3. Compare alternatives and make a local choice

Use this when a team needs to compare technologies, vendors, designs, policies, research paths, implementation options, or architecture moves without jumping to one favorite too early.

FPF helps you state what is being compared, which characteristics matter, which candidates are still in play, what evidence is missing, when a local choice is justified, and how to publish a selected set without hiding the comparison logic.

Typical first result: a comparison note with declared characteristics, candidate set, evidence gaps, the present scope of the choice, and what a selected-set publication may and may not be used to decide.

First inspect: [[00_A.19 - CharacteristicSpace & Dynamics Hook (A.CHR-SPACE)|A.19]], [[01_A.19.ECS - Evaluation CharacteristicSpace Construction|A.19.ECS]], [[00_C.11 - Decision Theory (Decsn-CAL)|C.11]], [[00_C.18 - Open-Ended Search Calculus (NQD-CAL)|C.18]], [[00_C.19 - Explore-Exploit Governor (E-E-LOG)|C.19]], [[00_G.0 - Frame Standard and Comparability Governance - CG-Spec|G.0]], and [[00_G.05 - Multi-Method Dispatcher & MethodFamily Registry|G.5]].

## 4. Turn a vague situation into a usable problem statement

Use this when a project has complaints, opportunities, risks, anomalies, or strategic pressure, but no clear problem yet.

FPF helps you preserve partly formed concerns without pretending they are already requirements, decisions, causes, evidence, or work items. It can turn a vague situation into a problem card or problem portfolio that later work can use without erasing uncertainty.

Typical first result: a problem card, problem portfolio, or problem note that records what has been accepted, what remains only a cue, which context is involved, and which first pattern family can use the problem statement.

First inspect: [[02_C.22.02 - ProblemCard@Context|C.22.2]], [[04_C.02.2a - U.LanguageStateSpace - Language-state chart over U.CharacteristicSpace|C.2.2a]], [[00_A.16 - Language-State Move Coordination|A.16]], [[02_A.16.01 - U.PreArticulationCuePack|A.16.1]], [[03_A.16.02 - Reopen - SketchBackoff - Respecify|A.16.2]], [[01_B.04.01 - Observe -- Notice -- Stabilize -- Route|B.4.1]], and [[01_B.05.02.00 - U.AbductivePrompt|B.5.2.0]].

## 5. Define what "better" means and run improvement

Use this when you need to improve a product, process, architecture, document, pattern, regulation, research program, or organization, but the improvement criteria are vague or competing.

FPF helps you define characteristics for evaluation, evaluate what is being improved, generate a portfolio of improvement proposals, choose changes that really improve the situation, and repeat the cycle without reducing quality to one score.

Typical first result: a quality-and-improvement note with evaluation characteristics, one evaluation of the object under improvement, a portfolio of proposed changes, and a condition for stopping or reopening the cycle.

First inspect: [[01_A.19.ECS - Evaluation CharacteristicSpace Construction|A.19.ECS]], [[00_E.22 - Improvement-Oriented Quality Evaluation Question Framing|E.22]], [[00_E.23 - Quality Improvement Loop Method|E.23]], [[00_C.16 - Measurement & Metrics Characterization (MM-CHR)|C.16]], [[00_C.25 - Q-Bundle- Authoring --ilities- as Structured Quality Bundles|C.25]], [[00_E.21 - FPF Pattern-Quality Evaluation CharacteristicSpace|E.21]], [[01_E.09.DA - DRR Decision-Adequacy Evaluation CharacteristicSpace|E.9.DA]], and [[01_E.02.DA - FPF Pillar-Adequacy Evaluation CharacteristicSpace|E.2.DA]] when the object is an FPF artifact.

## 6. Prepare evidence, assurance, or gate decisions before commitment

Use this when a project cannot responsibly act yet because evidence, assurance, constraints, gate validity, or decision permission is unclear.

FPF helps you separate what is being claimed from the evidence path, assurance argument, internal constraint validity, gate decision, local choice, and performed work. That separation matters when the cost of acting too early is high.

Typical first result: a commitment-readiness note that lists the claim, the evidence or assurance still needed, the gate or decision condition, and the work that remains blocked until those checks exist.

First inspect: [[00_A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]], [[00_B.03 - Trust and Assurance Calculus (F-G-R with Congruence)|B.3]], [[00_A.20 - U.Flow.ConstraintValidity - Eulerian|A.20]], [[00_A.21 - GateProfilization- OperationalGate(profile) (GateFit core)|A.21]], [[00_C.11 - Decision Theory (Decsn-CAL)|C.11]], [[00_C.28 - CausalUse-CAL- Causal-Use Questions, Causality-Ladder Rungs, Identification and Realizability|C.28]], and the relevant work or architecture pattern if the claim is about planned or performed work.

## 7. Check timing, freshness, rhythm, and action windows

Use this when a project depends on timing: freshness, latency, rate, cadence, action window, synchronization, inertia, aging, or rhythm.

FPF helps you separate timing information from evidence, permission, work completion, or vague urgency. It can say what timestamp, interval, cadence, freshness limit, action window, or rhythm claim is being used, and when that claim is no longer current enough for action.

Typical first result: a timing note that names what the timing is about, the relevant time relation or rhythm, the freshness or action-window limit, and the action that remains blocked when the timing claim is stale or underspecified.

First inspect: [[00_C.27 - Temporal Claim Adequacy- State Readings, Temporal Trends, and Intervention-Sensitive Temporal Change|C.27]], [[00_A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]], [[00_A.20 - U.Flow.ConstraintValidity - Eulerian|A.20]], [[00_A.21 - GateProfilization- OperationalGate(profile) (GateFit core)|A.21]], [[00_C.11 - Decision Theory (Decsn-CAL)|C.11]], and the pattern that governs the thing whose timing matters.

## 8. Use causal explanations, interventions, responsibility, and model outputs safely

Use this when a project says that one thing causes another, a model output justifies an action, a change will produce an effect, or a role is responsible for an outcome.

FPF helps you separate causal use, counterfactual use, intervention claims, responsibility claims, model-output reliance, evidence, and decisions. It keeps a plausible explanation, prediction, or dashboard output from becoming permission to act.

Typical first result: a causal-use or model-output-use note that names the claim, the intervention or counterfactual being considered, the evidence or validation still needed, the responsibility limit, and the decision or work that remains blocked.

First inspect: [[00_C.28 - CausalUse-CAL- Causal-Use Questions, Causality-Ladder Rungs, Identification and Realizability|C.28]], [[00_A.10 - Evidence Graph Referring- Claim-Bound Evidence and Provenance Graph|A.10]], [[00_B.03 - Trust and Assurance Calculus (F-G-R with Congruence)|B.3]], [[00_A.20 - U.Flow.ConstraintValidity - Eulerian|A.20]], [[00_A.21 - GateProfilization- OperationalGate(profile) (GateFit core)|A.21]], [[00_C.11 - Decision Theory (Decsn-CAL)|C.11]], and the domain pattern that governs the affected thing.

## 9. Compare descriptions, dashboards, explanations, and views of the same thing

Use this when a project has several descriptions, dashboards, explanations, renderings, model slices, or views and needs to know whether they are about the same thing, serve the same concern, or can be relied on in the same way.

FPF helps you keep the thing being described separate from its description, publication form, rendering, viewpoint, and same-thing claim. It can keep a diagram, dashboard, generated explanation, or view from silently becoming the thing itself, evidence, assurance, or decision.

Typical first result: a description-use note that names what is being described, which description or view is being used, how it is published or rendered, whether the same thing is really being addressed, and what the publication may and may not be used to claim.

First inspect: [[03_E.17 - Multi-View Publication Kit|E.17]], [[00_E.17.00 - U.MultiViewDescribing - Viewpoints, Views & Correspondences|E.17.0]], [[04_E.17.EFP - ExplanationFaithfulnessProfile - explanation-use discipline over existing MVPK faces|E.17.EFP]], [[04_A.15.04 - Work-Relevant Source Restoration|A.15.4]], [[00_A.07 - Strict Distinction (Clarity Lattice)|A.7]], [[01_C.30.AD - Architecture Description Adequacy|C.30.AD]], and the pattern that governs the described thing.

## 10. Give things better names

Use this when project terms are misleading, overloaded, politically convenient, too broad, too local, or hard to translate between teams.

FPF helps you name products, roles, work processes, architecture elements, standards, document types, claims, characteristics, and project objects without treating a catchy label as ontology.

Typical first result: a naming card or term sheet that says what is being named, which local contexts use the name, which candidate names were rejected, which plain and technical names are allowed, and which alternate names are risky.

First inspect: [[00_F.17 - Unified Term Sheet (UTS)|F.17]], [[00_F.18 - Local-First Unification Naming Protocol|F.18]], [[00_F.19 - Ontology-First Plain Technical Rewriting|F.19]], [[00_E.10 - Unified Lexical Rules for FPF|E.10]], [[01_E.10.ARCH - Wording-Use Ontological Precision Restoration Architecture|E.10.ARCH]], and the subject pattern that governs the thing being named.

## 11. Repair wording in technical documents before it changes action

Use this when standards, specifications, contracts, policies, dashboards, model cards, explanations, or working documents use words that may quietly change what can be claimed or done.

FPF helps you repair wording by first recovering the ontology: what thing, relation, value, evidence path, publication use, gate, decision, work, or architecture claim is actually being made. The repair is not word-policing; it succeeds only when the repaired text still tells someone what can now be used, checked, or named, or which related pattern to apply.

Typical first result: a repaired paragraph, claim register, term sheet row, or non-use decision that says what the text may now be used for and what claim or action remains blocked.

First inspect: [[00_E.10 - Unified Lexical Rules for FPF|E.10]], [[01_E.10.ARCH - Wording-Use Ontological Precision Restoration Architecture|E.10.ARCH]], [[00_F.18 - Local-First Unification Naming Protocol|F.18]], [[00_F.19 - Ontology-First Plain Technical Rewriting|F.19]], [[09_A.06.P - Relational Precision Restoration (RPR) - Kind-Explicit Qualified Relation Discipline|A.6.P]], [[00_C.02.P - Epistemic Precision Restoration|C.2.P]], [[01_C.16.P - Characteristic and Scale Precision Restoration|C.16.P]], [[02_C.16.Q - Quality-Term Precision Restoration|C.16.Q]], [[02_C.30.P - Architecture and Structure Precision Restoration|C.30.P]], [[11_A.06.F - Function and Functional Precision Restoration (RPR-FUNCTION)|A.6.F]], and [[12_A.06.M - Module Relation Repair|A.6.M]].

## 12. Decide whether mathematics or formal modeling would help

Use this when intuition is not enough and a mathematical model, formal declaration, invariant, or explicit structure could make the work easier to review, compare, or improve.

FPF helps with two opposite mistakes: missing useful mathematics, and using mathematics without saying what structure it preserves and what it loses. It keeps mathematical-lens use, formal declarations of the assumed substrate, mechanism import or realization, and first-principles-to-work carry-through as different claims that may need different patterns.

Typical first result: a short modeling note that names what is being modeled, the candidate mathematical lens, any formal declaration that is needed, preserved and lost structure, payoff, validation limit, and next project action.

First inspect: [[00_C.29 - Mathematical Lens Use|C.29]], [[04_A.06.00 - U.Signature - Universal, law-governed declaration for a SubjectKind on a BaseType|A.6.0]], [[05_A.06.01 - U.Mechanism- Law-Governed Operation Algebra over a Subject Kind|A.6.1]], [[01_E.18.01 - Principles-to-Work Carry-Through|E.18.1]], [[00_C.16 - Measurement & Metrics Characterization (MM-CHR)|C.16]], [[00_C.27 - Temporal Claim Adequacy- State Readings, Temporal Trends, and Intervention-Sensitive Temporal Change|C.27]], [[05_C.30.LCA - Control Structure View Adequacy (LCA)|C.30.LCA]], [[06_C.30.ILC - Cross-Scope Architecture Residual Triage|C.30.ILC]], and the domain pattern that governs the modeled claim.

## 13. Build a state-of-the-art or option portfolio

Use this when the project needs the current field of possible solutions, schools of thought, research lines, technologies, or design options, rather than one recommendation.

FPF helps you harvest alternatives, keep novelty and diversity visible, define comparison characteristics, avoid early collapse to one winner, and refresh the portfolio as the field changes.

Typical first result: a SoTA pack, option portfolio, candidate set, archive, or selector-ready publication with declared scope, comparison characteristics, and refresh condition.

First inspect: [[00_G.0 - Frame Standard and Comparability Governance - CG-Spec|G.0]], [[00_G.01 - CG-Frame-Ready Generator|G.1]], [[00_G.02 - SoTA Harvester & Synthesis|G.2]], [[00_G.05 - Multi-Method Dispatcher & MethodFamily Registry|G.5]], [[00_G.10 - SoTA Pack Shipping|G.10]], [[00_G.11 - Telemetry-Driven Refresh & Decay Orchestrator|G.11]], [[00_C.18 - Open-Ended Search Calculus (NQD-CAL)|C.18]], [[00_C.19 - Explore-Exploit Governor (E-E-LOG)|C.19]], [[00_A.19 - CharacteristicSpace & Dynamics Hook (A.CHR-SPACE)|A.19]], and [[01_A.19.ECS - Evaluation CharacteristicSpace Construction|A.19.ECS]].
