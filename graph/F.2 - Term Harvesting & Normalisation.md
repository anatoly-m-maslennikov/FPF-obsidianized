---
type: "fpf-pattern"
context:
  - "FPF"
page_type: "fpf-pattern"
mode: "canonical-generated"
fpf_id: "F.2"
title: "Term Harvesting & Normalisation"
part: "[[FPF - Part F — The Unification Suite (U‑Suite)- Concept‑Sets, SenseCells & Contextual Role Assignment]]"
parents:
  - "[[FPF - Part F — The Unification Suite (U‑Suite)- Concept‑Sets, SenseCells & Contextual Role Assignment]]"
source_file: "FPF-Spec.md"
source_lines:
  - 72534
  - 72830
status: "generated"
terms:
  - "U.BoundedContext"
  - "U.Types"
generated_on: "2026-06-15"
generated: true
---


**“Harvest words *inside Contexts*, name them in the Context’s own idiom, and stop there.”**
**Status.** Architectural pattern.
**Depends on.** [[E.10.D1 - Lexical Discipline for “Context” (D.CTX)|E.10.D1]] **Lexical Discipline for “Context” (D.CTX)**; **[[F.0.1 - Contextual Lexicon Principles|F.0.1]] Contextual Lexicon Principles** (Source - Local Meaning - Bridge‑Only Crossing); [[A.7 - Strict Distinction (Clarity Lattice)|A.7]] **Strict Distinction**; [[A.11 - Ontological Parsimony (C‑5)|A.11]] **Ontological Parsimony**.
**Coordinates with.** [[F.1 - Domain‑Family Landscape Survey|F.1]] **Context Map via Context Cards**; [[F.3 - Intra‑Context Sense Clustering|F.3]] **Intra‑Context Sense Clustering**; [[F.4 - Role Description (RCS + RoleStateGraph + Checklists)|F.4]] **Role Description**; [[F.9 - Alignment & Bridge across Contexts|F.9]] **Alignment & Bridge Across Contexts**.
**Aliases (informative).** *context‑local harvesting*; *Local normalisation*.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:1 - Intent & applicability

**Intent.** Provide a **conceptual** (notation‑free) discipline for turning *Context‑internal usage* into **context‑local lexical units** ready for later reasoning—without Cross‑context merging and without slipping into governance or tooling. The result is a **small, auditable set of context‑local names and glosses** that faithfully reflect how the canon speaks.

**Applicability.** Use whenever a unification line (from [[F.1 - Domain‑Family Landscape Survey|F.1]]) needs **actual words** to be referenced by patterns in Part C (Extention patterns) or by Role Descriptions ([[F.4 - Role Description (RCS + RoleStateGraph + Checklists)|F.4]]). Re‑enter [[F.2 - Term Harvesting & Normalisation|F.2]] when a canon/edition changes or when a new Context is admitted in [[F.1 - Domain‑Family Landscape Survey|F.1]].

**Non‑goals.** No global labels; no Cross‑context equivalence; no workflow or role descriptions; no storage/API talk. [[F.2 - Term Harvesting & Normalisation|F.2]] specifies **how to think**, not how to “run a pipeline”.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:2 - Problem Frame

Even with Contexts fixed ([[F.1 - Domain‑Family Landscape Survey|F.1]]), three mistakes recur:

1. **Word‑centrism.** Treating a string as if it carried its meaning across Contexts (*process*, *role*, *service*).
2. **Over‑normalisation.** Forcing one spelling/morphology across different canons, erasing Context‑specific cues.
3. **Premature structure.** Smuggling behaviour, deontics, or type structures into what should remain **lexical**.

[[F.2 - Term Harvesting & Normalisation|F.2]] prevents these by **localising** meaning and **naming** strictly **inside** each Context.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:3 - Forces

| Force                      | Tension to resolve                                                               |
| -------------------------- | -------------------------------------------------------------------------------- |
| **Uniformity vs locality** | Desire for consistent names vs Context‑specific idioms that must be preserved.      |
| **Parsimony vs recall**    | Keep the harvested set small vs keep rare but pivotal terms that unlock bridges. |
| **Didactics vs fidelity**  | Two‑register labels (tech/plain) vs fidelity to the canon’s own phraseology.     |
| **Speed vs safety**        | Move fast to enable F.3/F.4 vs avoid any Cross‑context conclusion in [[F.2 - Term Harvesting & Normalisation|F.2]].           |

## [[F.2 - Term Harvesting & Normalisation|F.2]]:4 - Core idea (didactic)

**Harvest *inside* each Context; name *in that Context’s idiom*; do not cross Contexts.**
For every Context (a **U.BoundedContext** from [[F.1 - Domain‑Family Landscape Survey|F.1]]), you gather **attested phrases** as *thought‑cues*, choose a **Local Normal Form (LNF)** that matches the Context’s idiom, attach a **two‑register label** (Tech/Plain), and write a **one‑sentence gloss**. That’s all. You do **not** claim sameness with any other Context; you do **not** embed behaviour or deontics; you do **not** mint U.Types here. These *local lexical units* will become **Local‑Senses** in [[F.3 - Intra‑Context Sense Clustering|F.3]] and later addressable **SenseCells** (Context × Local‑Sense).

## [[F.2 - Term Harvesting & Normalisation|F.2]]:5 - Minimal vocabulary (this pattern only)

* **Context** — Tech‑register alias for **U.BoundedContext** (per [[E.10.D1 - Lexical Discipline for “Context” (D.CTX)|E.10.D1]]).
* **Attested phrase** — A short, verbatim cue from the canon that shows how a word is used **in this Context** (citation idea, not a record format).
* **Local Normal Form (LNF)** — The Context‑specific canonical surface you will use when referring to the term in this Context (minimal editing: spelling/hyphenation/casing per the canon).
* **Two‑register label** — **Tech** (engineer‑facing) and **Plain** (pedagogic) forms for the same Context‑local meaning.
* **Gloss (one‑sentence)** — A **Context‑faithful** description of how the canon uses the term, at **minimal generality**.
* **Local lexical unit** — The quintet *(Context, LNF, Tech, Plain, Gloss)*. This is [[F.2 - Term Harvesting & Normalisation|F.2]]’s only outcome.
* **Homonymy (signal)** — Awareness that the **same string** has **different local lexical units** across Contexts (no relation asserted).
* **SenseCell** *(appears downstream)* — Address **(Context × Local‑Sense)** minted in [[F.3 - Intra‑Context Sense Clustering|F.3]]; mentioned here so you know what you’re preparing.

> *Everything above is a way of thinking. None of it implies a database, statuses, or roles.*

## [[F.2 - Term Harvesting & Normalisation|F.2]]:6 - Solution — three mental moves (notation‑free)

### [[F.2 - Term Harvesting & Normalisation|F.2]]:6.1 - Move A — **Localise the word**

**Question to ask.** *“In which Context am I hearing this word?”*
**Action (mental).** Point to a specific **Context** (from [[F.1 - Domain‑Family Landscape Survey|F.1]]). Grab 1–2 **attested phrases** that are representative **in this Context**.
**Outcome.** You stop thinking “global word” and start thinking “context‑local usage”.

*Micro‑cue.* If you cannot name the Context, do not harvest the word.

### [[F.2 - Term Harvesting & Normalisation|F.2]]:6.2 -Move B — **Name it in the Context’s idiom**

**Question to ask.** *“How would this Context itself write it?”*
**Action (mental).** Choose the **LNF** (Context‑conformant spelling/hyphenation). Then write the **two‑register label** and a **one‑sentence gloss** that says **what the canon means here**—nothing more.
**Outcome.** You have a **local lexical unit** *(Context, LNF, Tech, Plain, Gloss)*.

*Micro‑cues.*
• Prefer the canon’s head noun; keep canonical hyphens; avoid invented compounds.
• The **Plain** label should help a non‑specialist; the **Tech** label should match engineers’ eyes.
• The **Gloss** must fit on a single line; put details in [[F.3 - Intra‑Context Sense Clustering|F.3]].

### [[F.2 - Term Harvesting & Normalisation|F.2]]:6.3 - Move C — **Fence it off**

**Question to ask.** *“What must I refuse to conclude here?”*
**Action (mental).** Explicitly **refuse** to: (1) compare across Contexts, (2) fold morphology that the canon treats as meaningful, (3) embed behaviour, deontics, or type structure.
**Outcome.** A clean, **context‑local** lexical unit that will be safe to cluster in [[F.3 - Intra‑Context Sense Clustering|F.3]] and safe to bridge (or not) in [[F.9 - Alignment & Bridge across Contexts|F.9]].

## [[F.2 - Term Harvesting & Normalisation|F.2]]:7 - Guard‑rails (normative, lightweight)

1. **context‑locality.** Every local lexical unit **MUST** cite a Context (U.BoundedContext from [[F.1 - Domain‑Family Landscape Survey|F.1]]).
2. **Context‑idiom normalisation.** LNF **MUST** respect the Context’s idiom (spelling/hyphenation/casing) and use **minimal edits**.
3. **Two registers.** Each unit **SHOULD** carry both **Tech** and **Plain** labels for didactics; if one is missing, justify.
4. **Minimal generality (G‑1).** The gloss **MUST** be as specific as the Context’s canon requires—no broader.
5. **EntityOfConcern / Description / specification-use hygiene ([[A.7 - Strict Distinction (Clarity Lattice)|A.7]]).** **MUST NOT** include behaviour equations, deontic rules, measurement math, or type axioms; those belong to patterns.
6. **No Cross‑context claims.** **MUST NOT** assert equivalence, subsumption, or similarity with terms in other Contexts ([[F.9 - Alignment & Bridge across Contexts|F.9]] only).
7. **Edition honesty.** If the Context’s canon has multiple editions with shifting usage, treat them as distinct Contexts in [[F.1 - Domain‑Family Landscape Survey|F.1]] before harvesting.
8. **Parsimony.** Prefer **few, telling** lexical units over long tails; keep head terms that will power F.3/F.4/F.9.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:8 - Micro‑examples (illustrative, context‑local)

> Each line is *one* local lexical unit. No relations are implied across lines.

* **Context:** *BPMN 2.0 (2011)* — **LNF:** `process`
  **Tech:** `process` - **Plain:** `workflow process`
  **Gloss:** “Directed graph of flow nodes and sequence flows enacted by participants.”

* **Context:** *PROV‑O (2013)* — **LNF:** `activity`
  **Tech:** `activity` - **Plain:** `temporal occurrence`
  **Gloss:** “Time‑bounded occurrence that uses and generates entities and is linked to agents.”

* **Context:** *ITIL 4 (2020)* — **LNF:** `service‑level‑objective`
  **Tech:** `service‑level‑objective` - **Plain:** `service target`
  **Gloss:** “Target value for a service characteristic within a service promise vocabulary.”

* **Context:** *NIST RBAC (2004)* — **LNF:** `role`
  **Tech:** `access‑role` - **Plain:** `permission role`
  **Gloss:** “Named grouping of permissions assignable via sessions.”

* **Context:** *SOSA/SSN (2017)* — **LNF:** `observation`
  **Tech:** `observation` - **Plain:** `measurement act`
  **Gloss:** “Act applying a procedure to a feature of interest to produce a result.”

* **Context:** *IEC 61131‑3* — **LNF:** `task`
  **Tech:** `task` - **Plain:** `runtime program execution`
  **Gloss:** “Cyclic or event‑driven execution unit for control programs.”

## [[F.2 - Term Harvesting & Normalisation|F.2]]:9 - Didactic heuristics (informative)

* **Keep the Context prefix in your inner speech.** Say “*process (BPMN)*”, “*activity (PROV)*”.
* **Prefer head nouns.** If the canon says “service‑level objective”, do not shorten it to “objective”.
* **Resist elegance that erases signal.** Hyphens and case often carry the Context’s culture; keep them.
* **Gloss from use, not from opinion.** Quote in your mind, then compress; avoid importing definitions from neighbouring Contexts.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:10 - Anti‑patterns & remedies

| #       | Anti‑pattern                 | Symptom (in thought or prose)                                        | Why harmful                                                  | Remedy (conceptual move)                                                                                |
| ------- | ---------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| **A1**  | **Global normal form**       | One “canonical” label reused across Contexts.                           | Erases local meaning; invites stealth bridges.               | Keep **LNF per Context**; any Cross‑context relation belongs to **[[F.9 - Alignment & Bridge across Contexts|F.9]]** only.                                 |
| **A2**  | **String = meaning**         | Assuming identical strings denote one concept across Contexts.          | Homonym collision (*process*, *role*, *service*).            | Always prefix mentally with the **Context**; treat same string in different Contexts as **different units**.  |
| **A3**  | **Over‑normalisation**       | Folding hyphens/case/morphology “for consistency”.                   | Loses the canon’s idiom; breaks citations.                   | **Minimal edits** toward the Context’s idiom; never toward a global house‑style.                           |
| **A4**  | **Headless multiword**       | Truncating to a head (“objective” for “service‑level objective”).    | Ambiguity; collapses scope.                                  | Preserve canonical **head‑modifier** as LNF when meaningful.                                            |
| **A5**  | **Premature structure**      | Embedding behaviour, deontics, units, or type axioms into the gloss. | EntityOfConcern / Description / specification-use mixing (violates [[A.7 - Strict Distinction (Clarity Lattice)|A.7]]); biases later patterns.          | Gloss **usage**, not calculus; structural content belongs to Extention Patterns in Part C.                   |
| **A6**  | **Cross‑context folding**       | “BPMN workflow ≈ PROV activity” written inside [[F.2 - Term Harvesting & Normalisation|F.2]].                   | Hidden bridge; unpriced losses.                              | No Cross‑context claims in [[F.2 - Term Harvesting & Normalisation|F.2]]; write the **itch to bridge** for **[[F.9 - Alignment & Bridge across Contexts|F.9]]**.                                  |
| **A7**  | **Edition blur**             | “BPMN” without year/profile; mixing excerpts across editions.        | Silent sense shift; unrepeatable reasoning.                  | Treat distinct editions as **distinct Contexts** in [[F.1 - Domain‑Family Landscape Survey|F.1]], then harvest.                                     |
| **A8**  | **Vendor‑dialect elevation** | Treating a DSL/keyword list as “the domain”.                         | Projectionism; narrow idiom dominates.                       | If needed, model the DSL as **one context among others**; keep heterogeneity from [[F.1 - Domain‑Family Landscape Survey|F.1]].                     |
| **A9**  | **Tail chasing**             | Harvesting hundreds of rare terms.                                   | Cognitive overload; dilutes signal.                          | Keep **head terms** that feed F.3/F.4/F.9; justify rare units by their bridging value.                  |
| **A10** | **Fake symmetry**            | Tech and Plain labels are identical jargon.                          | Didactic failure.                                            | Make **Plain** genuinely explanatory; keep **Tech** faithful to the canon.                              |
| **A11** | **Temporal fudge**           | Using run‑time words in design Contexts (or vice versa).                | Category drift; later contradictions.                        | Respect the Context’s **DesignRunTag** from its Card ([[F.1 - Domain‑Family Landscape Survey|F.1]] §7.2).                                      |
| **A12** | **Cross‑language collapse**  | Merging bilingual terms as one unit.                                 | Erases idiom‑specific signals; hides normative mapping gaps. | Treat each language edition as its **own Context** unless the canon declares a normative mapping.          |
| **A13** | **Alias inflation**          | Inventing new local names “for clarity”.                             | Strays from the canon; hinders bridging.                     | Prefer the canon’s idiom; keep invented phrasings to the **Plain** register only.                       |
| **A14** | **Role/status conflation**   | RBAC “role” glossed as behavioural role.                             | Cross‑family bleed; wrong assignment later.                         | Call out the Context in the label: **access‑role (RBAC)** vs **participant (BPMN)**; keep senses disjoint. |

## [[F.2 - Term Harvesting & Normalisation|F.2]]:11 - Worked examples (context‑local only)

> Each line is a **local lexical unit** *(Context, LNF, Tech, Plain, Gloss)*.
> No Cross‑context relation is implied. Later clustering ([[F.3 - Intra‑Context Sense Clustering|F.3]]) and bridges ([[F.9 - Alignment & Bridge across Contexts|F.9]]) may connect them.

### [[F.2 - Term Harvesting & Normalisation|F.2]]:11.1 Enactment + sensing

* **Context:** *BPMN 2.0 (2011)* — **LNF:** `process`
  **Tech:** `process` - **Plain:** `workflow process`
  **Gloss:** “Directed graph of flow nodes and sequence flows enacted by participants.”

* **Context:** *PROV‑O (2013)* — **LNF:** `activity`
  **Tech:** `activity` - **Plain:** `temporal occurrence`
  **Gloss:** “Time‑bounded occurrence that uses and generates entities and links to agents.”

* **Context:** *SOSA/SSN (2017)* — **LNF:** `observation`
  **Tech:** `observation` - **Plain:** `measurement act`
  **Gloss:** “Act applying a procedure to a feature of interest to produce a result.”

* **Context:** *ITIL 4 (2020)* — **LNF:** `service‑level‑objective`
  **Tech:** `service‑level‑objective` - **Plain:** `service target`
  **Gloss:** “Target value for a service characteristic within a service promise vocabulary.”

*Thinking pay‑off:* you can phrase “compare **observation** to **service‑level‑objective**” without importing workflow or provenance semantics.

### [[F.2 - Term Harvesting & Normalisation|F.2]]:11.2 Sys‑CAL / LCA‑CAL + services

* **Context:** *State‑space control texts* — **LNF:** `actuation`
  **Tech:** `actuation` - **Plain:** `control output`
  **Gloss:** “Signal applied to the plant to influence state or output.”

* **Context:** *IEC 61131‑3* — **LNF:** `task`
  **Tech:** `task` - **Plain:** `runtime program execution`
  **Gloss:** “Cyclic or event‑driven execution unit for control programs.”

* **Context:** *ITIL 4 (2020)* — **LNF:** `incident`
  **Tech:** `incident` - **Plain:** `reported disruption`
  **Gloss:** “Unplanned interruption or reduction in the quality of a service.”

*Thinking pay‑off:* avoids calling a plant fault an “incident” unless you **cross Contexts later** with an explicit bridge.

### [[F.2 - Term Harvesting & Normalisation|F.2]]:11.3 Kind-CAL + Method‑CAL + KD‑CAL

* **Context:** *OWL 2 (profiles)* — **LNF:** `subclass‑of`
  **Tech:** `subclass‑of` - **Plain:** `is‑a (type hierarchy)`
  **Gloss:** “C ⊑ D: every instance of C is an instance of D.”

* **Context:** *FCA corpus* — **LNF:** `formal‑concept`
  **Tech:** `formal‑concept` - **Plain:** `extent–intent node`
  **Gloss:** “Maximal (objects, attributes) pair under a Galois connection.”

* **Context:** *SPEM 2.0 / ISO 24744* — **LNF:** `method`
  **Tech:** `method` - **Plain:** `abstract way of doing`
  **Gloss:** “Abstract how‑to independent of specification or execution.”

* **Context:** *SOSA/SSN (2017)* — **LNF:** `procedure`
  **Tech:** `procedure` - **Plain:** `measurement recipe`
  **Gloss:** “Specification guiding how an observation is produced.”

*Thinking pay‑off:* discourages treating an FCA “concept” as a `U.Type`, or a **procedure** as a **method** without later proof.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:12 - Reasoning primitives (judgement schemas, notation‑free)

> Read each as a **permitted mental move** over the outcomes of [[F.2 - Term Harvesting & Normalisation|F.2]].
> Symbols: `R` = Context (U.BoundedContext), `u` = local lexical unit, `s` = lexical string.

1. **Localisation**
   `heard(s) ∧ R chosen ⊢ localize(s,R)`
   *You decide to hear `s` only **in** Context `R`.*

2. **Context‑idiom normalisation**
   `localize(s,R) ⊢ LNF_R(s) = ℓ`
   *Within `R`, the **Local Normal Form** for `s` is `ℓ`.*

3. **Unit formation**
   `LNF_R(s)=ℓ ∧ labelTech=t ∧ labelPlain=p ∧ gloss=g ⊢ unit(u) = ⟨R,ℓ,t,p,g⟩`
   *A **local lexical unit** is formed (quintet).*

4. **Lexical‑only guard**
   `unit(u) ⊢ lexicalOnly(u)`
   *No behavioural/deontic/type math is attached to the gloss.*

5. **Homonymy signal (Cross‑context)**
   `LNF_Ra(s)=ℓa ∧ LNF_Rb(s)=ℓb ∧ Ra≠Rb ⊢ homonymy(s) ⊇ {Ra,Rb}`
   *Same string across Contexts is flagged as **different** by default.*

6. **Minimal generality check**
   `unit(u) ⊢ minimal(u) ⇔ gloss(u) says no more than the Context’s usage requires`
   *The gloss fits the Context; broader claims are withheld.*

7. **Two‑register adequacy**
   `unit(u) ⊢ didactic(u) ⇔ (tech(u) faithful) ∧ (plain(u) explanatory)`
   *Tech stays canonical; Plain helps non‑specialists.*

8. **No Cross‑context conclusion**
   `unit(u@Ra), unit(v@Rb), Ra≠Rb ⊢ ¬(u ≡ v) (within [[F.2 - Term Harvesting & Normalisation|F.2]])`
   *[[F.2 - Term Harvesting & Normalisation|F.2]] never asserts Cross‑context equivalence.*

9. **Ready‑for‑[[F.3 - Intra‑Context Sense Clustering|F.3]] signal**
   `lexicalOnly(u) ∧ minimal(u) ∧ didactic(u) ⊢ readyF3(u)`
   *A unit is suitable input for **intra‑Context clustering** in [[F.3 - Intra‑Context Sense Clustering|F.3]].*

## [[F.2 - Term Harvesting & Normalisation|F.2]]:13 - Relations

**Builds on:**
**[[F.1 - Domain‑Family Landscape Survey|F.1]]** (Contexts fixed; heterogeneity/parsimony in place).
**[[E.10.D1 - Lexical Discipline for “Context” (D.CTX)|E.10.D1]] D.CTX** (Context ≡ U.BoundedContext; “Problem Frame” reserved for narrative).
**[[F.0.1 - Contextual Lexicon Principles|F.0.1]]** (Source - Local Meaning - Bridge‑Only Crossing).

**Constrains:**
**[[F.3 - Intra‑Context Sense Clustering|F.3]]** (Intra‑Context Sense Clustering): operates **only** on units **from one Context**; produces Local‑Senses and addressable **SenseCells**.
**[[F.4 - Role Description (RCS + RoleStateGraph + Checklists)|F.4]]** (Role Description Definition): may **cite SenseCells**, not raw strings.
**[[F.9 - Alignment & Bridge across Contexts|F.9]]** (Alignment & Bridge): consumes **homonymy signals**; declares explicit Cross‑context mappings with loss policies.

**Used by.**
Extention patterns in Part C when referencing domain idioms (labels stay **context‑local**).

## [[F.2 - Term Harvesting & Normalisation|F.2]]:14 - Migration notes (conceptual)

1. **New edition appears.** Add a Context in [[F.1 - Domain‑Family Landscape Survey|F.1]]; harvest afresh in [[F.2 - Term Harvesting & Normalisation|F.2]] using that Context; do not overwrite earlier units.
2. **Idiomatic update discovered.** If your LNF fought the canon’s idiom, **re‑LNF** within the same context; keep labels/glosses steady unless the canon itself differs.
3. **Ambiguity inside a Context.** If use splits, **mint two units** with distinct glosses; [[F.3 - Intra‑Context Sense Clustering|F.3]] will sort their relation (same/different Local‑Sense).
4. **Language split.** Treat each language canon as its **own Context**; resist cross‑language merges in [[F.2 - Term Harvesting & Normalisation|F.2]].
5. **Tail pruning.** If units accumulate without feeding F.3/F.4/F.9, drop them from the working set; keep head terms that carry bridges.
6. **DSL quarantine.** If a tool dialect is unavoidable, keep it as one context among others; never let it define the idiom for other Contexts.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:15 - Acceptance tests (SCR/RSCR — concept‑level)

### [[F.2 - Term Harvesting & Normalisation|F.2]]:15.1 - Static conformance (SCR)

* **SCR‑F2‑S01 (context‑locality).** Every unit cites a Context from [[F.1 - Domain‑Family Landscape Survey|F.1]].
* **SCR‑F2‑S02 (Idiomatic LNF).** Each LNF reflects the Context’s spelling/hyphenation/casing with **minimal edits**.
* **SCR‑F2‑S03 (Two registers).** Each unit carries both **Tech** and **Plain** labels; if not, a reason exists tied to didactics.
* **SCR‑F2‑S04 (Lexical‑only).** No gloss contains behaviour, deontics, measurement math, or type axioms.
* **SCR‑F2‑S05 (No Cross‑context claims).** Nowhere does [[F.2 - Term Harvesting & Normalisation|F.2]] assert equivalence/similarity/subsumption across Contexts.
* **SCR‑F2‑S06 (Minimal generality).** Glosses match the Context’s use; no globalisation.
* **SCR‑F2‑S07 (Temporal honesty).** For Contexts with fixed DesignRunTag, units and glosses respect it.

### [[F.2 - Term Harvesting & Normalisation|F.2]]:15.2 - Regression (RSCR)

* **RSCR‑F2‑E01 (Edition split).** Introducing a new edition yields new units under a new Context; earlier units persist unchanged.
* **RSCR‑F2‑E02 (Normaliser stability).** Adjusting an LNF does not silently widen/narrow the gloss.
* **RSCR‑F2‑E03 (Language split).** Adding a second language yields a second Context; no bilingual collapse in [[F.2 - Term Harvesting & Normalisation|F.2]].
* **RSCR‑F2‑E04 (No stealth bridges).** After updates, [[F.2 - Term Harvesting & Normalisation|F.2]] still contains **zero** Cross‑context identity claims; any mapping appears only in [[F.9 - Alignment & Bridge across Contexts|F.9]].
* **RSCR‑F2‑E05 (Head‑term focus).** Periodic check shows the unit set remains small and oriented to F.3/F.4/F.9 needs.

## [[F.2 - Term Harvesting & Normalisation|F.2]]:16 - Didactic distillation (60‑second script)

> “In [[F.2 - Term Harvesting & Normalisation|F.2]] you **harvest inside Contexts**. For each Context, pick the canon’s own phrasing, choose a **Local Normal Form** in that idiom, add **Tech** and **Plain** labels, and write a one‑sentence **Gloss** that matches how that Context talks. Stop there. No bridging, no behaviour, no equations. If the same string appears in another Context, treat it as a **different unit**. These units feed [[F.3 - Intra‑Context Sense Clustering|F.3]], where you’ll sort senses **within** a Context, and [[F.9 - Alignment & Bridge across Contexts|F.9]], where you’ll relate Contexts explicitly. This keeps meaning local, names faithful, and later reasoning clean.”

## [[F.2 - Term Harvesting & Normalisation|F.2]]:End
