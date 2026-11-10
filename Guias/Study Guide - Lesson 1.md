# SOFTWARE ENGINEERING I
## Master Exam Study Guide | ESPOL, 2026

**Course alignment:** Lectures 1b, 2, 3a, and 3b of Dra. Villavicencio and Dr. Carlos Mera Gomez, combined with the assigned books by Sommerville, Cohn, Rubin, Wiegers & Beatty, Leffingwell, and the International Scrum Institute.

**Purpose:** An exam-oriented reference, not an official answer key. All numerical thresholds, scenario details, and story estimates in the worked examples are **illustrative assumptions**, not claims about an actual ESPOL system. They are stated so they can be challenged and validated as requirements.

### How to study this guide

1. Learn the **definition**, **mechanism**, **trade-off**, and **failure mode** of each process model, not only its name.
2. For every requirement, identify **who**, **trigger**, **system response**, **constraints**, **measurement**, and **test oracle**.
3. For agile questions, separate **value/priority**, **size/estimate**, **effort-hours**, and **delivered story points**.
4. Attempt each problem independently; then compare your reasoning with the fully worked solution.
5. Treat lecture terminology as the primary vocabulary for this course; note separately where textbook editions or contemporary terminology differ.

### Source map and chapter corrections

| Source | What it directly supports | Examination caution |
|:--|:--|:--|
| Lecture 1b, *Software Processes* (PDF pp. 4-33) | Software crisis, layered software engineering, processes, Sommerville vs. Pressman, SDLC | Process activities are not the same as SDLC phases. |
| Lecture 2, *Software Process Models* (PDF pp. 4-78) | Waterfall, V, incremental, prototypes, spiral, concurrent, CBSE, RUP, agile-vs-plan decisions and Boddy profile | The course's Boddy diagram is qualitative, not a universally specified numeric scoring algorithm. |
| Lecture 3a, *Requirements Engineering* (PDF pp. 4-43) | User/system levels, elicitation problems, ten communication principles, FR/NFR taxonomy and metrics, library drill | Quantitative quality attributes may induce additional functional requirements. |
| Lecture 3b, *Scrum Framework* (PDF pp. 4-53) | 3 roles, 3 artifacts, sprint events/activities, task <=16h rule, burndown, six principle families | Lecture values and team-size convention differ from later Scrum Guide terminology. |
| Kenneth S. Rubin, *Essential Scrum* | Ch. 2 = framework; Ch. 4 = Sprints; Ch. 5 = requirements/user stories; **Ch. 6 = product backlog**; Ch. 3 = Scrum principles | The request's attribution of Product Backlog to Ch. 5 is inaccurate. |
| Mike Cohn, *User Stories Applied* | Ch. 1 overview; Ch. 2 writing stories/INVEST; **Ch. 3 user-role modeling**; Ch. 7 guidelines for good stories; **Ch. 8 estimating**; Ch. 12 what stories are not; Ch. 13 why stories; Ch. 14 story smells | User-role modeling and estimation are not in Chs. 13 and 7, respectively. SPIDR is an additional later heuristic, not Cohn's chapter heading. |
| Wiegers & Beatty, *Software Requirements*, 3rd ed. | **Ch. 7 elicitation**; Ch. 10 documenting requirements; Ch. 11 writing excellent requirements; **Ch. 12 analysis models/diagrams** | Chs. 10-11 are the assigned reading, while Chs. 7 and 12 supply the requested extensions. |
| Dean Leffingwell, *Agile Software Requirements* | Ch. 6 user stories; Ch. 7 stakeholders, personas, UX; **Ch. 13 WSJF and feature prioritization** | WSJF is not in Ch. 7 of this uploaded edition. |
| International Scrum Institute, *The Scrum Framework*, 3rd ed. | Scrum roles, cards, planning poker, DoD, sprint backlog, burndown, planning/review/retro/refinement | Use as supplementary course-era vocabulary, not as a replacement for the slides. |

---

# MODULE 1 - SOFTWARE PROCESSES AND SDLC LIFE-CYCLE MODELS

## 1.1 The intellectual foundation: why software engineering exists

**The problem in individual programming.** A personal utility may have one programmer and its only user may be its author. Professional software is usually built by a team for other users, becomes part of organizational work, requires coordinated interfaces, and must evolve for years. Success therefore includes not just executable code but requirements agreement, dependability, security, cost control, deployment, maintenance, and traceable decisions. In Lecture 1b (PDF pp. 4-5), these are the distinctions between individual and large-system programming.

**Software crisis (1968 NATO conference, Garmisch).** Growing system size and interdependence exceeded ad-hoc development practices, producing cost and schedule overruns, unreliable programs, and difficulties making changes. The lesson is not that programming failed, but that the discipline needed repeatable engineering methods, management, independent verification, and measurement. An elaborate process is not always superior: it must be tailored to problem, team, risk, and organizational environment (Lecture 1b, PDF pp. 7-10, 29).

**Software engineering as layered technology (Pressman/Maxim, presented in Lecture 1b, PDF pp. 16-18):**

| Layer, bottom-up | Function | Failure if neglected |
|:--|:--|:--|
| Quality focus / organizational commitment (foundation) | Establishes quality goals, standards, improvement and accountability. | Fast delivery of a poorly defined or unsafe product. |
| Process | Defines management and engineering framework, milestones and controls. | Disconnected technical work and unpredictable coordination. |
| Methods | Techniques for elicitation, models, architectures, design, programming and testing. | Teams perform a process ceremonially without sound engineering. |
| Tools | Automate or support methods and process: CI, version control, static analysis, issue tracking. | Manual inefficiency or unrepeatable evidence; note that tools never substitute for methods. |

**Important exam distinction:** quality *underpins* the process; tools sit at the top as enablers. A process model is an abstract representation and not a rigid prescription for every application (Lecture 1b, PDF pp. 29, 32).

## 1.2 The two process-activity taxonomies are different views

**Sommerville's four fundamental activities** (Lecture 1b, p. 25; Sommerville, *Software Engineering*, Ch. 2): (1) **Specification:** establish required services and constraints; (2) **Development:** design and implement; (3) **Validation:** check software against specifications and users' intended needs; (4) **Evolution:** change the software in response to new needs and conditions. These activities recur in iterative models; they are not required to occupy one uninterrupted time block each.

**Pressman and Maxim's five generic framework activities** (Lecture 1b, pp. 27-28): (1) **Communication:** work with stakeholders to understand objectives and needs; (2) **Planning:** estimate work, resources, risks and schedules; (3) **Modeling:** analyze requirements and design the solution; (4) **Construction:** code and test; (5) **Deployment:** deliver, support and receive feedback. This framework often embeds umbrella activities such as risk management, quality assurance, configuration management, measurement and reviews.

| Sommerville (what must happen to a software product) | Related Pressman activities (how engineering work is organized) | Why not equivalent one-to-one |
|:--|:--|:--|
| Specification | Communication + requirements part of Modeling | Specification includes analysis and constraints; conversation alone is insufficient. |
| Development | Architecture/design in Modeling + code in Construction | Pressman places design in Modeling, unlike a simplistic "development = construction" mapping. |
| Validation | Tests in Construction + evaluation during Deployment; reviews across all activities | Validation is cross-cutting, not exclusively a final stage. |
| Evolution | Feedback at Deployment, then renewed Communication/Planning/Modeling/Construction | Pressman's generic framework describes a repeating cycle rather than naming evolution as one of the five. |

**Exam trap:** neither list is a universal sequence of five/six waterfall phases. Do not confuse *fundamental activities* with *life-cycle models*, *technical tasks*, or *Scrum events*.

## 1.3 Eight SDLC models in operational detail

### A. Waterfall - sequential, plan-driven development

**Canonical flow:** requirements definition -> system/software design -> implementation and unit testing -> integration/system testing -> operation/maintenance (Lecture 2, PDF pp. 4-9; Sommerville, Ch. 2).

1. Capture and baseline substantially stable requirements; approve a requirements specification.
2. Derive architecture, interfaces, detailed design and test plans; record traceability.
3. Implement modules; verify locally.
4. Integrate and evaluate the system; resolve defects, including rework to prior documents.
5. Deliver and maintain; new requirements typically enter formal change control.

**Strengths:** predictable phase gates, contractual deliverables, management visibility, documentation and independent audits. **Weaknesses:** users see working software relatively late; upstream misunderstandings cause costly rework; schedules may create false confidence if documents are treated as proof of product quality. The lecture says it may suit embedded, critical and multi-organization engineering systems because hardware and regulatory evidence impose up-front decisions (Lecture 2, p. 7). It is not appropriate merely because managers desire certainty.

### B. V-Model - a waterfall family with corresponding test levels

The left branch progressively decomposes and specifies the product; the right branch provides testing and assurance corresponding to each specification level (Lecture 2, pp. 10-11).

| Left: definition / design | Right: corresponding check | Example |
|:--|:--|:--|
| Stakeholder/user needs | Acceptance testing / validation | Does the medical device support the required clinical workflow? |
| System requirements/specification | System testing | Does the fully integrated device meet end-to-end response and safety limits? |
| High-level architecture/subsystem design | Integration testing | Do pump controller, alarm and sensor interfaces interact correctly? |
| Detailed module design | Unit/component testing | Does dose-limit calculation handle invalid input and boundaries? |
| Bottom of V | Coding / implementation | Build the elements subjected to subsequent tests. |

Test **planning** should begin on the left branch, even though test execution often occurs on the right. **Verification:** does the implementation satisfy specified models? **Validation:** does the resulting system meet genuine user needs? Both matter in the V-Model. **Pitfall:** strong traceability does not rescue an incorrect original specification; late user feedback remains expensive.

### C. Incremental - usable capability in successive releases

Plan a core product and partition remaining outcomes into **vertical, usable increments** (Lecture 2, pp. 13-17). Increment 1 might allow a customer to search books and see a loan; increment 2 adds renewal; increment 3 adds notifications. Every increment runs a mini cycle: specify -> design -> implement -> test -> deploy -> learn. Subsequent plans incorporate user feedback, but a stable architectural skeleton and reasonably understood high-level scope are helpful.

**Benefits:** earlier value, lower exposure per release, frequent real feedback, prioritization of the most important capabilities and more repeated testing of core features. **Risks:** poorly chosen increments depend on each other, integration overhead accumulates, and neglecting refactoring erodes architecture. **Incremental vs. evolutionary:** incremental emphasizes planned slices of a system; evolutionary emphasizes learning and shaping the solution across iterations. A project can do both.

### D. Prototyping - learn through a simplified representation

Cycle: stakeholder objectives -> quick plan -> quick design of uncertain aspects -> construct prototype -> user evaluation -> clarify requirements -> repeat (Lecture 2, pp. 21-24).

- **Throwaway/exploratory prototype:** a disposable mock-up or proof of concept used to discover misunderstood requirements. The final production implementation is engineered separately.
- **Evolutionary prototype:** a deliberately engineered initial product that is refined into the operational system. Requires production-quality architecture, tests and maintainability discipline.
- **Horizontal prototype:** many user screens with little backend functionality; useful for workflow understanding.
- **Vertical prototype:** narrow but end-to-end slice of UI, data, service and integration; useful for proving architectural feasibility.

**Key risk:** customers mistake a polished-looking mock-up for a finished product; technical shortcuts in experimental code are carried into production. Specify whether the artifact is disposable and what decision the experiment will resolve.

### E. Boehm's Spiral - risk-driven process generator

The Spiral is not merely "waterfall repeated four times." Boehm's distinctive contribution is that **the nature and amount of work in a loop follow its dominant risks** (Lecture 2, p. 26). A typical loop proceeds:

1. **Determine objectives, alternatives, constraints:** e.g., preserve patient safety, evaluate sensor A vs. sensor B, and meet latency constraints.
2. **Identify, analyze and resolve high-priority risks:** estimate probability/severity/exposure; use a simulation, prototype, benchmark, expert review, or independent safety analysis.
3. **Develop and verify the selected next-level product:** architecture proof, requirement baseline, subsystem or operating increment, depending on the loop.
4. **Plan next loop and obtain stakeholder commitment:** confirm the risk is sufficiently controlled, decide what to fund and build next.

**Risk exposure (illustrative):** RE = probability of loss x magnitude of loss. A 0.10 chance of a $200,000 loss gives RE = $20,000. This prioritizes inquiry; it is not proof that a risk is acceptable, especially for safety hazards.

**Anchor-point milestones** (expanded Boehm theory, beyond the brief slide): **LCO** (Life-Cycle Objectives: viable concept/business case), **LCA** (Life-Cycle Architecture: architecture and major risks justified), **IOC** (Initial Operational Capability: deployable operational readiness). Their purpose is evidence-based stakeholder commitment. If uncertainty persists, choose another risk-reduction loop rather than blindly proceeding. **Best fit:** high-uncertainty, high-consequence, technologically novel systems with capable risk-analysis staff. **Pitfall:** costly overhead, poor risk identification, or cycles with no objectively reduced uncertainty.

### F. Concurrent development - activities progress through states

Instead of a single whole-project "design stage," each activity (communication, modeling, construction, etc.) has a state, and events trigger state changes (Lecture 2, pp. 28-30). A typical state vocabulary is **Inactive, Under Development, Awaiting Changes, Under Revision, Under Review, Baselined, Done**.

**Example trace for architecture:** Inactive -> Under Development -> Under Review -> Awaiting Changes (stakeholder finds a compliance conflict) -> Under Revision -> Under Review -> Baselined -> Done. At the same time, unrelated tested components may be in Construction, and acceptance planning may have begun. **Benefit:** parallelism and explicit rework visibility. **Risks:** coordination overhead, inconsistent concurrent versions, integration conflicts and dependencies that prevent genuine parallel progress. A state diagram tells you *which activity is where*, not which SDLC model is always best.

### G. Component-Based Software Engineering (CBSE) and COTS

A component is independently deployable, encapsulates implementation, and exposes its functionality through defined interfaces. **Provides interface:** operations/services a component offers. **Requires interface:** operations/services it needs from another component. If PaymentUI *requires* `Charge(amount, currency)` and Gateway *provides* a compatible contract, they can be composed; incompatible data formats, security properties or versions may require an **adapter** (Lecture 2, PDF pp. 33-43).

**Operational CBSE workflow:** (1) derive candidate services; (2) search, evaluate and select components/COTS; (3) revise negotiable requirements if justified by available components; (4) architect for reuse and design adapters; (5) build missing functionality; (6) integrate, configure, test interfaces, license restrictions, security, performance and upgrade strategy. The lecture explicitly includes component analysis, requirements modification, design with reuse, and development/integration (p. 38).

**Benefits:** less custom code, faster delivery, lower implementation risk if component quality is established. **Hidden costs:** licensing, lock-in, external vulnerabilities, API incompatibilities, inability to control vendor changes, and pressure to weaken business requirements to fit a package. CBSE is a reuse strategy that can coexist with incremental/RUP/agile processes; not necessarily an exclusive project-wide sequence.

### H. Rational Unified Process (RUP) - iterative, incremental and disciplined

**Four life-cycle phases** answer *when is the project mature enough to advance?*: **Inception** (vision, business case, scope, preliminary risks); **Elaboration** (validate architecture, mitigate top risks, refine requirements); **Construction** (build integrated, tested capability in iterations); **Transition** (beta, deployment, training, stakeholder acceptance). Each phase can contain multiple iterations, and each iteration performs multiple engineering disciplines. The lecture's RUP diagram (Lecture 2, PDF p. 45) shows nine disciplines as colored waves across the same four phase columns; it does **not** assign each discipline exclusively to one phase.

**Illustrative RUP discipline-by-phase activity matrix.** H = comparatively intensive; M = moderate; L = usually lower, **not absent**. This is a conceptual interpretation of the lecture graphic, not fixed percentages:

| Discipline (9) | Inception | Elaboration | Construction | Transition |
|:--|:--:|:--:|:--:|:--:|
| Business Modeling | H | M | L | L |
| Requirements | H | H | M | L |
| Analysis & Design | M | H | H | L |
| Implementation | L | M | H | M |
| Test | L | M | H | H |
| Deployment | L | L | M | H |
| Configuration & Change Management | M | H | H | H |
| Project Management | H | H | H | H |
| Environment | H | M | M | L |

**Exam contrast:** *phase* = lifecycle milestone and business decision; *discipline* = recurring type of work. Architecture is risk-driven in Elaboration, not prohibited elsewhere. **Pitfall:** turning RUP into heavyweight document gates and losing iteration benefits.

## 1.4 Comparative decision matrix: all requested models

| Model | Best use cases | Requirement changes | Risk management | Customer involvement | Primary pitfall |
|:--|:--|:--|:--|:--|:--|
| Waterfall | Stable contracts, hardware-constrained, audit-heavy projects | Formal baselines and costly downstream change | Up-front specification/design reviews and stage gates | High at definition and acceptance, often low mid-build | Late discovery; expensive rework |
| V-Model | High-assurance, safety/security and traceability | Controlled; tests/specifications updated together | Explicit verification mapped to each definition level | Needs thorough early and final validation | Correct tests against wrong needs |
| Incremental | Partitionable products needing early usable releases | Reprioritize later increments; protect architecture | Smaller releases and user feedback | Repeated per increment | Poor increments; architectural erosion |
| Prototyping | UI uncertainty, novel workflows, feasibility questions | Expected through iterative feedback | Fast experiments target knowledge gaps | Very high during evaluation | Prototype mistaken for product |
| Spiral | High-risk, novel, long-lived, expensive systems | Revisited as risks are reduced | Explicit risk identification, resolution, anchor milestones | High at each commitment point | Excessive analysis; weak risk expertise |
| Concurrent | Parallel workstreams / time-critical coordination | Event-driven activity state changes | Surface dependencies and review loops | Variable by active workstreams | Integration/configuration chaos |
| CBSE/COTS | Reusable components, integration portfolios | Negotiation constrained by component capabilities | Component qualification, interface and vendor evaluation | Medium: select/evaluate candidate components | Lock-in, mismatch, dependency risk |
| RUP | Medium/large iterative projects needing governance | Managed within phase/iteration baselines | Architecture-first Elaboration, iterative risk reduction | Regular iteration reviews and milestones | Bureaucratized "waterfall in disguise" |

### Plan-driven vs. agile: evaluate three families of factors

| Family | Questions to ask (Lecture 2, pp. 63-68) | Likely implication |
|:--|:--|:--|
| **System** | Scale? embedded/real-time/safety critical? expected lifetime? regulator? | Large/long-lived/regulated systems need durable architecture, traceability, tests and evidence. |
| **Team** | Skills? co-located or distributed? outsourced? CI/testing/configuration tools? | Experienced, tightly collaborating teams with automation can adapt rapidly; distributed suppliers benefit from interface baselines. |
| **Organization** | Fixed-price/specification contracts? delivery and feedback access? change-tolerant culture? | External contracts and unavailable end users favor stronger planning; accessible owners and frequent delivery support incremental adaptation. |

**David Boddy project profile tool (lecture interpretation):** Lecture 2, PDF pp. 74-75, depicts a graph with uncertainty of requirements on the horizontal axis, uncertainty of resources on the vertical axis, and broad zones favoring **Waterfall** (low-low), **Incremental** (moderate), and **Evolutionary** (high). It adds that *core projects and projects with outside links tend toward incremental rather than purely evolutionary cycles*. This is qualitative guidance, not an official 1-to-5 decision algorithm. For the exercises below, a 1-to-5 rating is an explicit classroom **adaptation** for communication, not a claim that Boddy published these numerical thresholds.

## 1.5 Worked decision exercise 1 - regulated infusion-pump controller

**Problem.** A medical equipment producer must develop a pump controller that will operate for 15 years. Hardware and alarm interfaces must be frozen before manufacturing; software failures can seriously injure patients. Fifty engineers across four organizations will participate. Regulators and hospital safety evaluators require traceability, architecture justifications and documented tests. Clinical workflows are relatively stable; an experimental occlusion-detection algorithm remains uncertain. Choose a primary model and justify the treatment of that uncertainty. Evaluate plausible alternatives and provide an adapted Boddy profile.

**Step 1 - profile the project.** Requirements uncertainty **2/5** overall (stable clinical functions, one unknown algorithm); resource/technology uncertainty **3/5** (algorithm/hardware interaction); consequence of failure **very high**; outside links **many** (hardware vendors, hospitals, regulators); team **large/distributed**; contract/change freedom **low**; evidence and lifetime needs **very high**.

**Step 2 - read Boddy's graph.** Low-to-moderate uncertainties lean toward a planned baseline; external interfaces and project criticality motivate **controlled increments** rather than unrestricted evolution. Boddy alone cannot determine whether independent safety certification needs extra quality gates.

**Step 3 - select and justify.** Choose **V-Model assurance as the primary development/test structure**, used within a **controlled incremental delivery strategy**. Trace each user hazard and system requirement to architecture, code, unit/integration/system/acceptance tests. Prototype the *specific unknown algorithm* early; if high risk remains, run a **Spiral-style risk-reduction loop** before committing the architecture. Maintain configuration baselines and formal change impact analysis.

**Step 4 - reject insufficient alternatives.** Pure Waterfall has traceability but does not inherently make verification relationships as explicit as V-Model. Pure evolutionary prototyping is inappropriate as the final assurance process because fast feedback cannot replace formal safety evidence. RUP could organize multi-iteration architecture, but by itself is not a safety test argument. CBSE could integrate qualified components but cannot eliminate vendor and interface risk.

**Step 5 - exit criteria.** Before construction: approved hazards, interfaces, architecture and traceability; algorithm experiment meets measurable false-negative/latency targets. Before release: required test evidence complete, independent reviews signed, no unaccepted critical safety defects. **Final answer:** V-Model with controlled increments and risk-targeted prototyping, explicitly explaining why the combination addresses safety and uncertainty.

## 1.6 Worked decision exercise 2 - campus ordering platform

**Problem.** Six experienced co-located developers have ten weeks to build a campus food-ordering service. Student preferences and menu operations may change after pilots. A product owner is available every day and can test a working release weekly. Cloud CI and automated tests exist. Payment is supplied by an external payment service; a fixed delivery date is important, but functionality may be prioritized. Select the best model and an integration strategy.

**Step 1 - profile.** Requirements uncertainty **4/5**; resources/technology uncertainty **2/5** (known cloud stack, external payment integration); consequence **moderate**; outside link **one critical provider**; team **small/co-located/skilled**; owner participation **high**; contract flexibility **high**.

**Step 2 - Boddy placement.** Moving right on the uncertainty-of-requirements axis favors **evolutionary learning**, but the outside payment interface makes an **incremental** architecture and early technical contract useful (Lecture 2, pp. 74-75).

**Step 3 - choose.** Use **incremental/agile delivery with Scrum**, assisted by short exploratory **prototypes** for navigation and checkout and **CBSE/COTS** for a qualified payment gateway. Release 1: menus + selection; release 2: reservation and pricing; release 3: external payment and status; release 4: ordering notifications/feedback. Sequence based on dependency and user value; arrange a vertical payment proof early to resolve integration risk before promising the final increment.

**Step 4 - risk and testing.** Risks: payment service timeouts, underestimated peak load, late owner feedback. Responses: gateway sandbox contract tests, load benchmark, weekly usable demos and backlog reordering. Keep a complete Definition of Done for each released increment.

**Step 5 - compare options.** Waterfall hides evolving UX until too late; a heavyweight V-Model is disproportionate; Spiral may over-invest in formal risk management for this modest system; unrestricted throwaway prototypes do not produce a durable payment-integrated product. **Final answer:** Incremental/agile primary, with targeted prototyping and component reuse as complementary techniques.

## Module 1 - rapid examination checks

1. **Question:** Can RUP have Requirements work during Construction? **Answer:** Yes: phase and discipline axes are orthogonal; intensity varies.
2. **Question:** Is Spiral merely prototyping every iteration? **Answer:** No: it selects risk-reduction activities according to the dominant risks and uses stakeholder commitment milestones.
3. **Question:** Does a provides interface invoke a requires interface? **Answer:** A consumer **requires** a contract and a supplier **provides** it; the binding must be compatible.
4. **Question:** Why is a working prototype not proof of a production-ready product? **Answer:** Experimental implementation can omit resilience, testing, security and maintainability.

**Sources for Module 1:** Lecture 1b, PDF pp. 4-33; Lecture 2, PDF pp. 4-78, especially pp. 10-11 (V), 26 (Spiral), 30 (concurrency diagram), 35 (interface diagram), 38-39 (CBSE), 45 (RUP discipline graph), and 74-75 (Boddy); Sommerville, *Software Engineering*, Chs. 2, 3 and 16; Pressman/Maxim framework as reproduced in Lecture 1b.

---
# MODULE 2 - REQUIREMENTS ENGINEERING, FUNCTIONAL AND NON-FUNCTIONAL REQUIREMENTS

## 2.1 Requirements engineering (RE): problem before solution

A **requirement** states a capability a system must provide or a constraint it must obey. **Requirements engineering** is the systematic discovery, analysis, specification, validation and management of stakeholder needs (Lecture 3a, pp. 4-6; Sommerville, Ch. 4). The **problem domain** concerns users, work practices, outcomes, data meaning and constraints: *what problem must be solved and why?* The **solution domain** concerns behavior, interfaces, components and operational realization: *what will the system do to solve it?* A proposed user-interface widget is usually a solution candidate, not evidence that the underlying need is understood.

**Example, university library:**

- **Business goal:** reduce librarian handling time and make valid loan renewals available remotely.
- **User requirement UR-01 (problem-oriented):** "A borrower shall be able to request renewal of one of their eligible current loans without visiting the library." This is intelligible to nontechnical stakeholders, but still needs policy details.
- **System requirement SR-01a (precise behavior):** "When an authenticated borrower selects 'Request renewal' for their active loan, the system shall obtain that loan's due timestamp, renewal count and reservation status from the loan service."
- **SR-01b:** "The system shall approve a renewal only if the request timestamp is no later than the due timestamp, the renewal count is below two, and no other borrower has an active hold for that copy."
- **SR-01c:** "For an approved request, the system shall advance the existing due timestamp by seven calendar days, increment the renewal count once and store an audit record atomically."
- **SR-01d:** "For a denied request, the system shall leave the due date unchanged and display the specific applicable denial reason."

The one user goal **refines into multiple system requirements**. The lower-level statements are not automatically a complete design: they specify observable behavior and business rules; architecture may still be open. Requirements should carry IDs, sources, rationale, priority, dependencies, status and associated verification methods (Wiegers & Beatty, Chs. 10-11).

**RE stages and deliverables:** elicitation (interviews, observed work, source documents) -> analysis/negotiation (conflicts, priorities, feasibility, models) -> specification (structured user/system requirements, use cases, stories) -> validation (reviews, acceptance criteria, prototypes) -> ongoing management (baseline, traceability, versioning and change impact). These stages are iterative, not permanently separated.

## 2.2 The core difficulties and the ten communication principles

**Why RE is hard** (Lecture 3a, pp. 8-10): people struggle to articulate implicit practices; different stakeholder classes disagree; innovative products are difficult to imagine; needs change; teams prematurely design the solution; analysts falsely assume they know a domain better than its practitioners; stakeholders describe desirable features without stating exceptions; and completeness is difficult to prove. Separate *elicited claim*, *tested assumption*, *negotiated decision*, and *validated requirement*.

**All ten communication/negotiation principles** (Lecture 3a, pp. 12-14, Pressman/Maxim):

| # | Principle | Engineering application |
|:--:|:--|:--|
| 1 | **Listen** | Allow stakeholders to finish; ask clarifying questions rather than arguing with first answers. |
| 2 | **Prepare before communicating** | Study the organizational workflow, legacy reports, and domain vocabulary before interviewing. |
| 3 | **Have a facilitator** | Use a moderator to manage time, attendance, conflicts and decisions. |
| 4 | **Prefer face-to-face communication where practical** | Combine direct discussion with sketches, prototypes, screen shares and models. |
| 5 | **Take notes/document decisions** | Record rules, rationale, open items, owners and action deadlines. |
| 6 | **Strive for collaboration** | Co-create examples and success criteria, not adversarial demands. |
| 7 | **Stay focused/modularize discussion** | Handle a checkout workflow separately from data retention policy. |
| 8 | **Draw a picture if unclear** | Use a DFD, state model, workflow or sample screen to expose inconsistent assumptions. |
| 9 | **Move on after agreement or documented impasse** | Resolve, park or assign the issue so one disagreement does not derail the workshop. |
| 10 | **Negotiate for a win-win outcome** | Explore priorities and trade-offs; neither side should treat the meeting as a contest. |

## 2.3 Elicitation and analysis: techniques from Wiegers & Beatty

**Chapter accuracy:** the uploaded *Software Requirements*, third edition, places elicitation techniques in **Chapter 7** and diagrammatic analysis in **Chapter 12**. Assigned **Chapters 10-11** concentrate on how requirements are documented and written clearly. These chapters complement, rather than replace, the practical methods below.

| Technique | How to execute | Best for | Bias/limitation | Output / validation step |
|:--|:--|:--|:--|:--|
| **Semi-structured interviews** | Select representatives across user classes; start with goals and recent concrete cases; probe exceptions; read back notes. | Private needs, decision rules, tacit concerns and domain vocabulary. | Social desirability, leading questions, a nonrepresentative expert. | Interview notes -> candidate requirements -> confirmation by interviewee. |
| **Facilitated workshops / JAD** | Invite conflicting roles, set agenda/decision rights, map workflow jointly, negotiate and log disagreements. | Cross-functional processes and resolving contradictory rules quickly. | Loud participants dominate; costly to coordinate. | Agreed workflow/rules, decision log and open-issue list. |
| **Document/interface analysis** | Inspect policies, regulations, contracts, forms, reports, APIs, previous incident logs. Extract rules and verify that they remain current. | Compliance, required data, legacy integration and existing conventions. | Documents may be obsolete or describe an idealized process rather than reality. | Rule catalog, data dictionary, traceable source excerpts. |
| **Observation / contextual inquiry** | Watch a real user do typical and exceptional tasks; ask what prompted each action; separate workarounds from approved policy. | Tacit knowledge, exception handling, ergonomics and actual timings. | Hawthorne effect, privacy constraints and unusual observed days. | Observed workflow, timing distribution, discrepancy list. |
| **Prototypes / storyboards** | Show a low-cost representation; ask user to attempt tasks; capture misunderstood concepts, not mere color preferences. | Ambiguous user interactions and novel processes. | Apparent completeness, design fixation. | Revised scenarios and acceptance criteria. |
| **Interface analysis and focus groups** | Study external services and/or facilitate themed user feedback while distinguishing opinion from fact. | Integration contracts and broad reactions. | Feedback may miss edge cases or minority roles. | API contract, comparative findings, validation experiment. |

**Worked elicitation mini-example:** Stakeholder A says "students can always renew"; librarian B says "not when a book is reserved". Interview both about actual cases -> inspect circulation policy -> draw states/guards -> facilitate agreement on cutoff, holds and renewal count -> write one precise decision table -> test it with boundary examples. **Do not simply concatenate the two contradictory sentences into the specification.**

## 2.4 Modeling tool 1: Data Flow Diagrams (DFDs)

A **DFD** describes the movement and transformation of data, not control flow or order of UI clicks (Wiegers & Beatty, Ch. 12). Core notation: **external entity** (source/sink outside the system), **process** (transformation named with a verb phrase), **data flow** (named information), **data store** (persistent logical data). A DFD process should have meaningful incoming/outgoing data, and the levels should be **balanced**: external inputs and outputs at Level 1 must match those at the parent context diagram (unless intentionally refined and explained).

**University renewal context diagram:**

```
[Borrower] -- renewal request --> (0: Library Renewal System)
[Borrower] <-- decision, new due date -- (0: Library Renewal System)
[Librarian] -- policy updates --> (0: Library Renewal System)
[Librarian] <-- exceptions report -- (0: Library Renewal System)
```

**Illustrative Level-1 decomposition:**

```
[Borrower] --> (1.0 Authenticate & identify loan) <--> D1 Borrower/Loan Records
(1.0) --> (2.0 Evaluate eligibility) <--> D2 Holds and Renewal Policy
(2.0) --> (3.0 Update loan) <--> D1 Borrower/Loan Records
(2.0)/(3.0) --> (4.0 Compose decision) --> [Borrower]
[Librarian] --> (5.0 Maintain policy) <--> D2 Holds and Renewal Policy
(5.0) --> (6.0 Prepare exceptions report) --> [Librarian]
```

**Checks:** (1) data stores do not flow directly to one another without a process; (2) an external entity does not directly modify an internal store; (3) processes have meaningful names; (4) the context and decomposition retain the same external inputs/outputs; (5) access control and error paths are captured as requirements even if not all are shown at the highest level. **Exam trap:** a DFD is not a UML activity diagram, and an arrow should label **data**, not just "yes" or "no".

## 2.5 Modeling tool 2: state transition diagrams and decision tables

A **state-transition model** characterizes permissible object/system states, triggering events, guard conditions and transition effects. It is especially useful when "approve/reject" hides policy constraints (Wiegers & Beatty, Ch. 12).

**Loan state machine - simplified example:**

| Current state | Event and guard | Action | New state |
|:--|:--|:--|:--|
| Active loan | Renewal requested AND eligible | Add seven days; increment renewal count; log approval. | Active loan (updated attributes) |
| Active loan | Renewal requested AND not eligible | Preserve due date; log rejection; show reason. | Active loan (unchanged) |
| Active loan | Due timestamp passes before return | Mark overdue; possibly apply rule-driven penalties. | Overdue |
| Active loan or Overdue | Copy returned and inspected | Close loan; record actual return time. | Returned |
| Returned | Renewal requested | Reject: no active loan. | Returned |

For rigor, a denied renewal is often **an event/action, not a persistent loan state**. "Rejected" could instead be a state of a separate **renewal request entity**. Identify the modeled entity before adding states.

**Decision table for eligibility** (assumed policy):

| Before/equal due time? | Fewer than 2 past renewals? | No active hold? | Result |
|:--:|:--:|:--:|:--|
| Yes | Yes | Yes | Approve, extend by 7 calendar days. |
| No | - | - | Reject: due date already passed. |
| Yes | No | - | Reject: renewal limit reached. |
| Yes | Yes | No | Reject: reserved by another borrower. |

The `-` means "don't care for this rule". To be deterministic if multiple failures occur, define **reason precedence** (e.g., expired due date, then limit, then hold). **Boundary tests:** request one second before/equal/after due time; renewal counts 1 and 2; hold created while request is processing. Atomic updates prevent two concurrent renewals from bypassing the count limit.

## 2.6 How to write a measurable Functional Requirement (FR)

An FR specifies **behavior**: trigger, actor, information, response, business rule and failure behavior. Use one observable obligation per statement when practicable. Prefer *shall* for mandatory behavior and unambiguous conditions; avoid "quickly," "usually," "user-friendly," "as needed," "etc.," and unexplained "and/or." A strong template is:

> **[ID]** When **[trigger and precondition]**, the system **shall [observable action and output]**, subject to **[precise constraint]**; otherwise it **shall [defined error behavior]**.

**Weak FR:** "The system should show recent book loans." **Better FR:** "When an authenticated borrower opens 'My Loans,' the system shall list all loans whose return timestamp is null, ordered by due timestamp ascending, displaying title, copy ID and local due date/time; it shall display 'No active loans' if the result is empty." The NFR for 95th-percentile loading time is a separate requirement linked to this FR.

**Quality checklist** (Wiegers & Beatty, Chs. 10-11): correct, necessary, feasible, unambiguous, complete within scope, consistent, verifiable, prioritized, atomic enough to change, traceable, implementation-independent unless design constraints are genuine, and explicit about conditions/boundaries. A requirement can be syntactically precise yet wrong because the stakeholder need is misunderstood. Validation asks both **is the text precise?** and **is it the right need?**

## 2.7 Sommerville's NFR hierarchy - exact lecture categories and deeper implications

An **NFR** constrains qualities, operating conditions, development constraints or compliance. Many NFRs apply system-wide rather than to a single use case. Lecture 3a (PDF p. 21) groups them into **Product**, **Organizational**, and **External**. The lecture depicts Security as a Product branch and also discusses security as an aspect of dependability; in practice, overlapping tags are appropriate if the principal classification and rationale are documented.

### A. Product requirements

**Efficiency** has **performance** and **space** dimensions: throughput, response-time percentiles, concurrent-user capacity, CPU/memory budgets, startup/refresh time, disk space and network usage. The load profile must be part of the requirement: "2 seconds" for one user and for 5,000 users are different claims.

**Usability** concerns effectiveness, efficiency and user satisfaction within a defined population: training time by role, success rate for critical workflows, median task duration, task error rate, accessibility conformance, and help availability. "Easy to use" is not measurable without participant selection, tasks and success criteria.

**Dependability** includes, as appropriate, **availability** (service is operational when needed), **reliability** (correct operation without failure over a period/demand), **safety** (avoid unacceptable harm), **security** (resist unauthorized access and misuse), **resilience** (maintain/recover service under disturbance), **repairability** (restore after failure), **maintainability** (modify efficiently), **robustness** (handle abnormal inputs/environment), and **error tolerance** (limit impact of faults and human errors). Slide pp. 22, 25-28 discuss these facets, while their boundaries can overlap.

**Security** is sufficiently important to analyze separately using **confidentiality, integrity, availability**, authentication, authorization, auditability, threat modeling and abuse scenarios. A security constraint can generate new FRs: login, role management, access denial, audit records, token expiration, encryption key rotation and breach alerts (Lecture 3a, pp. 29, 37, 39). NFRs are not synonyms for "non-testable."

### B. Organizational requirements

**Environmental:** target operating systems, hardware, browser versions, deployment platform, middleware and portability rules. **Operational:** delivery/operation constraints, interoperability, backup operations, installation time and integration with organizational processes. **Development:** required languages/toolchains, prescribed methods, internal standards, documentation conventions, quality gates or lifecycle evidence. These are legitimate project constraints but should not be disguised as user-valued functionality (Lecture 3a, pp. 30, 36-38).

### C. External requirements

**Regulatory:** conditions imposed by an external regulatory body. **Legislative:** binding legal rules, including accounting, privacy/security and workplace safety. **Ethical:** societal/professional expectations and acceptable uses of data that may exceed legal minima. Compliance statements should identify the **actual authority/document/version**, applicable jurisdiction, verifiable obligations and evidence owner. A policy number invented for teaching is not a legal requirement.

**Crucial contrast:** "Only staff can access patient records" may be tagged **Product-Security** because it constrains access behavior and **External-Legislative** if an applicable law demands it. Give the primary category, then note secondary drivers rather than pretending the tree makes all requirements mutually exclusive.

## 2.8 NFR properties and quantitative metrics

| Property / category | Exact metric candidates | Example of a fully testable NFR | Measurement method |
|:--|:--|:--|:--|
| **Speed / performance** (Product-Efficiency) | p50/p95/p99 response time (ms), maximum latency, throughput (transactions/sec), transactions completed/min, peak concurrent users | Under **500 simultaneous borrowers** and the specified workload, **p95 renewal API latency <= 2.0 s** over a 60-minute sustained test, with **>= 30 successful transactions/s**. | Fixed environment, calibrated load, percentile distribution, error counter. |
| **Size / space** (Product-Efficiency) | RAM MB/GB, disk MB/record, payload KB, CPU percentage | At 500 users, application processes use **<= 2 GB RAM** at p95; average database growth **<= 4 KB per new loan** excluding backups. | Resource profiler, database growth sample. |
| **Usability** (Product-Usability) | Task success %, median task time, error rate, training hours, accessibility conformance | **>= 90%** of 30 representative first-time borrowers complete a renewal without assistance in **<= 3 minutes** after a 10-minute orientation. | Moderated test with fixed task script and representative cohort. |
| **Reliability** (Product-Dependability) | **MTTF** (time), MTBF for repairable operation, failure rate per hour, **POFOD** (failures/demand), **defects/FP** | Across **100,000 valid renewal requests**, the observed number of incorrect approval decisions shall be **0** (specified acceptance sample; long-term target set separately). | Event logs, independent expected-decision oracle, acceptance sampling. |
| **Availability / repairability** (Product-Dependability) | Availability %, **MTTR** (time), p95 recovery time, minutes of downtime/month | Monthly service availability **>= 99.9%**, excluding only a documented mutually agreed measurement exclusion; **p95 recovery <= 15 min** for tested recoverable failures. | Synthetic probes, incident timestamps, restore exercises. |
| **Robustness / resilience** (Product-Dependability) | Incorrect/corrupt transactions %, recovery time, max lost transactions, performance under fault injection | After a payment provider timeout, **0 duplicate charges in 10,000 fault-injection cases**; safe user-visible retry path within **5 s**. | Fault-injection and concurrency tests, invariant checks. |
| **Portability** (Organizational-Environmental in lecture) | Number of supported platforms, adaptation time, platform-dependent code %, test suite pass rate | A build shall pass **100% of mandatory regression tests** on approved Linux and Windows releases, with **<= 2 engineer-days** of platform-specific build adaptation. | CI matrix with version-pinned images, controlled change trial. |
| **Maintainability** (Product-Dependability) | Median lead time for defined change class, mean time to repair, defect density | For a defined *simple* business-rule change, median implementation-through-deployment time **<= 2 working days** over at least 10 sampled changes. | Tracked issues labeled with pre-agreed complexity rubric. |
| **Security** (Product-Security) | Unauthorized access successes/attempts, critical vulnerabilities, patch lead time, audit completeness | **0 unauthorized reads** in a pre-approved 1,000-case negative-access test suite; all sensitive read operations create a tamper-evident audit record. | Penetration/authorization suite, audit review, independent verification. |

**Metrics must be interpreted correctly.** MTTF is the *mean operating time until failure* for a relevant defined system/failure class. MTBF is *mean time between failures* for repairable systems; definitions must be explicit. MTTR is the *mean restoration/repair time*. **POFOD** = failed demands / total valid demands; it is appropriate for demand-driven functions. **Defect density** can be defects per Function Point (FP); function points measure functional size, not elapsed time. The slide enumerates MTTF, POFOD-related indicators, restart time, corruption probability and defects/FP (Lecture 3a, p. 28), though not every metric appears with the same abbreviation.

### Quantitative examples with solutions

**Example A - approximate steady-state availability.** If MTTF = 1,000 operating hours and mean restoration time MTTR = 2 hours, simplified availability is:

`A ~= MTTF / (MTTF + MTTR) = 1000 / 1002 = 0.998004 = 99.8004%`.

This relationship assumes an appropriate steady-state repairable-system model; it does not account for all correlated failures, planned maintenance rules or disaster dependencies. At **99.9% monthly availability**, a 30-day month has 43,200 minutes, so maximum counted downtime is `43,200 x (1 - 0.999) = 43.2 minutes`. At **99.95%**, the budget is 21.6 minutes. Availability is a fraction of time; POFOD is a fraction of *demands*.

**Example B - probability of failure on demand.** If 3 failures occur in 100,000 independent validated demands, empirical `POFOD = 3/100,000 = 0.00003 = 3 x 10^-5`. This is a point estimate, not automatically a statistically justified safety guarantee. To claim an upper confidence bound, specify the assumed distribution, sample size and confidence method.

**Example C - defect density.** A release has 14 confirmed defects over 280 Function Points. `Defect density = 14 / 280 = 0.05 defects/FP`. A numerator must define whether it counts open, escaped, severe or all verified defects; otherwise comparisons mislead.

## 2.9 How an NFR creates new functional requirements

**Top-level NFR:** "Only currently authorized librarians may access loan-history records." Primary category: **Product-Security**; potential additional External-Legislative driver. This tells you *what must be true* but not all the supporting behavior.

1. **Derived FR-SEC-01:** The system shall authenticate librarians with a unique organizational account before offering loan-history functions.
2. **Derived FR-SEC-02:** Before every loan-history read, the system shall check that the active identity possesses `LoanHistory.Read`; otherwise it shall deny the operation without returning the protected record.
3. **Derived FR-SEC-03:** An authorized administrator shall be able to add/revoke librarian roles; the change shall take effect for new requests within 60 seconds.
4. **Derived FR-SEC-04:** The system shall log identity, record ID, decision, timestamp and source for every loan-history read attempt while excluding sensitive record contents from the event.
5. **Derived FR-SEC-05:** A session revoked by an administrator shall fail subsequent protected requests.

**Traceability chain:** threat/organizational need -> NFR-SEC -> FR-SEC-01..05 -> architecture decisions -> acceptance/security tests -> operational audit. **Key point:** classifying an NFR does not remove the obligation to design functional mechanisms that enforce it (Lecture 3a, p. 39).

## 2.10 Worked exercise A - identify eight defects and rewrite six User Requirements

**Original ambiguous specification** (adapted from the exact library-renewal prompt in Lecture 3a, PDF p. 19):

> "A student will be able to extend the loan period for borrowed books at any time. The system can approve or reject an extension and must notify the lender of its decision. The system must be available at all hours."

**Task:** list **eight** independent ambiguities, conflicts or omissions and rewrite the passage into **six clear user-level requirements**. Declare any new assumptions.

**Step 1 - defect inspection:**

| # | Defective expression or missing condition | Why it is defective; question to resolve |
|:--:|:--|:--|
| 1 | "A student" | Any enrolled student, authenticated student, or current borrower? Can a student renew a different borrower's copy? |
| 2 | "borrowed books" | Does the loan need to be active, physically circulating, renewable, or from a special short-loan collection? |
| 3 | "at any time" | Does this mean 24/7 request submission, or eligibility even after the original due time? |
| 4 | "extend the loan period" | For how many days, counted from what timestamp, and with how many total renewals? |
| 5 | "can approve or reject" | Based on which deterministic policy: reservation holds, fines, overdue status, limits or staff approval? |
| 6 | Missing concurrency behavior | What if two renewal submissions race or a hold appears while a request is processing? Could renewal counts or due dates be corrupted? |
| 7 | "notify the lender" | Lender may be the library, not the student borrower. Who must be informed, by what channel, how quickly, with which information? |
| 8 | "available at all hours" | Absolute 100% availability is unrealistic; no measurement period, outage exclusions or service-level threshold is defined. |

**Step 2 - state explicit business assumptions** (do not pretend these were in the original text): an authenticated student may renew only their own **active** loan; a request at or before the stored due timestamp is timely; each loan allows at most **two** renewals; approval adds **seven calendar days to the previous due timestamp**; another borrower's active hold blocks renewal; denial reasons are evaluated in order *late -> renewal limit -> active hold*; a single transaction performs the count/date change atomically; student's email has been verified. All timestamps are stored unambiguously and displayed in local time. These policies require customer validation.

**Step 3 - rewrite exactly six unambiguous User Requirements:**

**UR-LIB-01 - Loan visibility and scope.** "An authenticated student shall be able to view only that student's currently active book loans and see for each loan the book title, copy identifier, due date/time and remaining renewal allowance."

**UR-LIB-02 - Submit renewal.** "A student shall be able to submit a renewal request for one of their active loans through the library portal at any time of day, including weekends; the portal shall display an acknowledgement for each submission."

**UR-LIB-03 - Eligibility determination.** "A student shall receive approval of a renewal if, at the system's authoritative decision time, the loan has not passed its due timestamp, fewer than two renewals have been approved for that loan, and no other borrower has an active hold on the copy."

**UR-LIB-04 - Approved outcome.** "For an approved renewal, the student shall see the due date/time advanced by exactly seven calendar days from the previous due timestamp and the remaining renewal allowance reduced by one; repeated or simultaneous processing of the same request shall not grant multiple extensions."

**UR-LIB-05 - Denied outcome.** "For a denied renewal, the student shall see the original due date/time unchanged and exactly one displayed reason, using priority order: overdue loan, renewal limit reached, or copy reserved by another borrower."

**UR-LIB-06 - Decision notification.** "After every renewal decision, the student borrower shall see the decision immediately in the portal and receive an email within 60 seconds containing the book title, approval/denial status, applicable due date/time and, for denials, the reason."

**Step 4 - separate quality from function.** The phrase "available at all hours" is better specified by an **associated NFR**, for example: "The renewal portal shall achieve >=99.9% service availability in each calendar month, measured by a successful renewal-status probe every minute from two independent monitors." (Clarify probe success logic, exclusions and maintenance contract.) UR-LIB-02 describes a *supported 24-hour submission workflow*, not an impossible promise of continuous perfect availability. This distinction explains why there are **six user requirements** plus a separate cross-cutting NFR.

**Step 5 - check completeness with test cases.** (a) borrower renews their own eligible copy exactly at due timestamp -> approved; (b) 1 second after -> denied; (c) count = 2 -> denied; (d) copy on hold -> denied; (e) two concurrent clicks -> one extension; (f) user accesses another user's loan -> denied; (g) failed email service -> queue/retry design needed; (h) portal outage -> availability metric applies. Items (g) and (h) reveal additional system-level requirements beyond these six user-level statements.

## 2.11 Worked exercise B - five NFR classification and quantification drills

**Task:** classify each of five vague statements into the lecture's Product / Organizational / External hierarchy, refine it into an objective metric, and say how to verify it. Proposed thresholds are **exercise assumptions** that need stakeholder agreement.

| Raw statement | Primary taxonomy | Quantified specification | Verification |
|:--|:--|:--|:--|
| **1. "The search must be fast."** | **Product -> Efficiency -> Performance** | Under the agreed catalog of 1 million records and 400 concurrent users, p95 search-response time **<=1.5 s** and error rate **<=0.1%** during a 60-min steady test. | Load generator + server telemetry; count successful searches. |
| **2. "The service should almost never fail."** | **Product -> Dependability -> Availability/Reliability** | Measured monthly API availability **>=99.95%**; among 50,000 valid renewal decisions, **zero observed erroneous acceptances**. | Synthetic availability probes + independently labeled decision cases. |
| **3. "It must run everywhere."** | **Organizational -> Environmental** | Mandatory workflows shall pass the regression suite on **Windows 11 and the two explicitly listed supported Linux distributions**, each at pinned release versions, with **>=99% test pass rate** and **zero release-blocking failures**. | Release CI platform matrix with recorded software images. |
| **4. "We must comply with data-protection rules."** | **External -> Legislative** (also Product-Security mechanisms) | For **100%** of documented personal-data export/deletion cases identified by the organization's legal requirements matrix, corresponding automated tests and review evidence shall pass before release; log the applicable legal instrument and exception handling. | Legal sign-off + traceability matrix + evidence checks; do not invent statutory deadlines. |
| **5. "The team must develop maintainable code."** | **Organizational -> Development** (also impacts Product-Maintainability) | Every change to main shall pass the organization's defined lint, security and automated regression gates; **>=80% statement coverage** on newly added application decision logic, without suppressing critical alerts. | Versioned CI policy, build history, coverage review; coverage alone is not proof of quality. |

**Step-by-step diagnosis:** (1) Find the *constraint's target*: end-product quality, organization's environment/method, or external obligation. (2) Select primary subtype. (3) Determine the *measurement unit*, *population/workload*, *time window* and *pass/fail threshold*. (4) Define an executable review or test method. (5) Add secondary tags and any required security/administration FRs. (6) Document assumptions and obtain stakeholder validation.

**Why other answers can be partly correct:** "runs everywhere" can be viewed as product portability in other taxonomies, but the **lecture** places platform/portability under Organizational-Environmental (Lecture 3a, p. 30). The test expects the lecture's classification; explain the alternative only as a secondary property.

## Module 2 - rapid examination checks

1. **FR or NFR:** "Every invalid password must be rejected and recorded." This is an **FR** that implements a **security NFR**.
2. **Ambiguity:** "Quickly" is ambiguous without percentile, units, workload and measurement method.
3. **State vs. flow:** *Borrower*, *RenewalRequest* and *Loan* may have different state machines; a DFD instead maps data transformations.
4. **Reliability vs. availability:** Low error probability per operation does not guarantee constant uptime, and vice versa.
5. **Validation vs. verification:** A perfectly tested incorrect renewal rule is verified against the wrong requirement, but the intended business need was not validated.

**Sources for Module 2:** Lecture 3a, PDF pp. 4-43, especially pp. 12-14 (communication), 19 (ambiguity exercise), 21-31 (taxonomy and metrics), 39 (derived FRs), 41 (library NFR exercise); Sommerville, *Software Engineering*, Ch. 4; Wiegers & Beatty, *Software Requirements*, Chs. 7, 10, 11, 12 and 14; SWEBOK v4.0a, Knowledge Area: Software Requirements (supplementary terminology).

---
# MODULE 3 - AGILE REQUIREMENTS, USER STORIES AND BACKLOG MANAGEMENT

## 3.1 User stories: small requirements for conversation and validation

A **user story** is a concise description of a desired capability from a user's or customer's viewpoint. It intentionally leaves room for face-to-face or direct discussion; it is not a miniature exhaustive Software Requirements Specification. A useful template is:

> "As a **[specific user role]**, I want **[observable capability]**, so that **[valuable outcome]**."

For example: "As a borrower with an eligible active loan, I want to renew that loan online, so that I can keep the book without visiting the library." The final clause helps test whether work is *valuable* and detect implementation-only tasks masquerading as user stories (Cohn, *User Stories Applied*, Chs. 1-2; Rubin, *Essential Scrum*, Ch. 5; Leffingwell, *Agile Software Requirements*, Ch. 6).

**Stories are a communication technique; acceptance tests and supplementary material still matter.** A complex safety rule, regulation or integration contract may require structured models, explicit system requirements and external evidence in addition to a story. User stories do not make NFRs disappear: cross-cutting reliability, accessibility and confidentiality constraints apply to each relevant completed increment.

### Ron Jeffries' 3 Cs, presented by Cohn

| C | Concrete meaning | Example for a renewal story | Common mistake |
|:--|:--|:--|:--|
| **Card** | Short *token for a future discussion*, on paper or in a tool. | "As a borrower, renew an eligible active loan remotely." | Treating the 20-word card as the entire finished specification. |
| **Conversation** | Ongoing dialogue establishing rules, exceptions, examples and constraints. | What if a hold exists? Due date passed by 1 second? A retry is duplicated? | Forbidding later clarification because the initial card was "approved." |
| **Confirmation** | Concrete acceptance tests proving the shared understanding. | A Given-When-Then scenario for hold/no-hold and the exact new due date. | Leaving "done" to subjective opinions rather than demonstrable checks. |

The three parts belong together. Cohn credits the mnemonic to Ron Jeffries in Chapter 1. **Exam trap:** A user story is not simply a *sentence format*; its conversations and testable confirmations are central.

## 3.2 INVEST: six criteria for a valuable, workable story

**INVEST** is a checklist popularized by Bill Wake and discussed by Cohn in **Chapter 2**, not Chapter 12 of the uploaded book.

| Criterion | Interpretation and test | If it fails, repair it by... |
|:--|:--|:--|
| **I - Independent** | The story can be prioritized and built with limited dependency on other stories. Complete independence is an aspiration, not an absolute. | Reordering/removing dependencies, splitting by user outcome, isolating a shared prerequisite. |
| **N - Negotiable** | Details can be discussed rather than assumed to be a rigid contract; nonnegotiable safety/legal constraints are still explicit. | Expressing outcome rather than prescribing screen layout/implementation prematurely. |
| **V - Valuable** | Completion yields an outcome valuable to a real user or stakeholder. | Rewriting from a user role and explaining its benefit; bundling nonvaluable technical steps into a vertical slice. |
| **E - Estimable** | Team understands the behavior and risks well enough to give a useful relative estimate. | Asking clarifying questions, prototyping/using a time-boxed research spike. |
| **S - Small** | Can reach the agreed Definition of Done within one Sprint while remaining vertically useful. | Splitting by workflow path, data type, interface, business rule or error condition. |
| **T - Testable** | Has observable acceptance conditions and a pass/fail oracle. | Writing Given-When-Then tests, specifying boundaries and required outputs. |

**Anti-example:** "As a user, I want a beautiful, fast library system with books, analytics, payment and chat." It combines many goals, lacks a specific persona and measurable confirmation, depends on a huge scope and is not small/estimable. **Repair:** identify specific users and outcomes; create a hierarchy from epic -> features -> vertical stories -> acceptance criteria -> engineering tasks.

**Story smells** in Cohn's Ch. 14 include stories that are too small to yield meaningful user value, too large, hard to prioritize or interdependent in ways that obscure progress. The remedy is **not** to make every card a single database or UI task; preserve end-to-end user value.

## 3.3 User Role Modeling - people are not a single generic "user"

**Correct source:** Cohn, Chapter 3 (*User Role Modeling*); additionally Leffingwell, Chapter 7 (*Stakeholders, User Personas, and User Experiences*).

**Repeatable role-modeling procedure:**

1. **Brainstorm people who interact with or are affected by the product.** Separate primary users (execute the task), secondary/support actors (administer it) and beneficiaries/sponsors (care about outcomes). Avoid treating a "payment gateway" as a human persona; it is an external system actor.
2. **Write role cards.** Include primary goal, access privileges, domain experience, frequency of use, environment, distinctive failure risks and what success means.
3. **Consolidate and distinguish roles.** Merge duplicates with the same objectives, but preserve meaningful differences (e.g., student borrower vs. librarian, not simply "student" vs. "staff").
4. **Use personas if helpful.** A persona is a research-grounded representative profile, not a stereotype or replacement for observing actual users. Include accessibility, language and device constraints when relevant.
5. **Map roles to goals and journeys.** Identify missing roles, conflicting policies and different exception cases. Validate the map with representatives rather than relying only on engineers' imagination.
6. **Derive and refine stories.** Prioritize roles and outcomes; write conversations and acceptance tests before Sprint commitment.

**Role map for our exercises:**

| Role | Goal | Context / important constraints | Primary stories |
|:--|:--|:--|:--|
| **Student borrower** | See loans and renew eligible books remotely. | Mobile device, deadline-sensitive, may have overdue/held copies. | L-01, L-02 |
| **Circulation librarian** | Keep renewal eligibility consistent with reservations and policy. | Needs audit trail, exception reasoning, access privileges. | Validates L-01 and L-02; future administrative story. |
| **Study-room requester** | Find and reserve a room for a time window. | Needs accessibility and real-time availability. | R-01, R-02 |
| **Facilities coordinator** | Prevent conflicting reservations and protect room inventory. | Manages open hours, closure exceptions and audit trail. | Validates R-01 and R-02. |
| **Accessibility-needs student** | Complete both workflows with assistive technologies. | Keyboard navigation, screen reader labels, high contrast. | Cross-cutting usability NFR / acceptance checks. |

**Question examiners may ask:** *Why role modeling before drafting stories?* Because identical functionality can have different value, rights and failure consequences across roles. It exposes missing stakeholders and invalid generalizations.

## 3.4 Epic, feature, story, acceptance criteria, task: compare levels

| Work item | Example | Purpose | Usually estimated / validated how? |
|:--|:--|:--|:--|
| **Epic** | "Enable library self-service borrowing." | Broad business goal requiring decomposition. | Roadmap-level sizing and value hypothesis, not necessarily Sprint-ready. |
| **Feature** | "Online book renewal." | Coherent capability spanning one or more user stories. | Release planning, integration and overall acceptance. |
| **User story** | "Eligible borrower renews one current loan." | Small user-valued vertical behavior. | Story points / acceptance scenarios / Definition of Done. |
| **Acceptance criterion** | "If there is an active hold, do not alter due time." | Verifiable condition of satisfaction for one story. | Pass/fail scenario or measurable check. |
| **Engineering task** | "Implement atomic renewal update and negative test." | Technical work to realize a story. | Effort-hours, owner/coordination, updated remaining hours. |
| **Nonfunctional constraint** | "Renewal p95 response <=2 s under 500 users." | Cross-cutting product/system quality. | Load test / measurement / trace to relevant stories. |

**Story vs. use case vs. traditional SRS** (Cohn, Ch. 12; Wiegers & Beatty, Chs. 10-12): a **story** is intentionally compact and conversation-oriented; a **use case** records actor-goal interactions, main and alternate flows, often more completely; an **SRS** consolidates formally controlled, detailed requirements and constraints across the system. These are **complementary representations**, not evidence that one format is invariably superior.

## 3.5 Estimation: story points, ideal days, planning poker and team velocity

**Edition correction:** Cohn's actual chapter dedicated to estimating user stories is **Chapter 8**, while assigned Chapter 7 concerns guidelines for good stories. Rubin and the Scrum Institute also discuss backlog estimation. Study both.

- **Story points:** a *relative* unit for effort/complexity/uncertainty/risk as defined by the team. A five-point story is broadly more demanding than a three-point reference story; points are not automatically engineer-hours or calendar days.
- **Ideal days:** estimated work duration under ideal conditions without interruptions or competing work. They are not the same as elapsed working days in a real environment. Never convert between points, ideal days and hours using an unexamined universal constant.
- **Engineering task hours:** a local breakdown for coordination and tracking **remaining effort** in the Sprint. The ESPOL lecture rule recommends **<=16 hours per task** (Lecture 3b, p. 25).
- **Velocity:** sum of story points of **Done** Product Backlog Items during a Sprint. An 8-point story 90% coded but not Done generally contributes **0** points to that Sprint's completed velocity.

**Planning Poker step by step:**

1. Product Owner explains story goal and acceptance conditions; the team asks questions and names uncertainties.
2. Establish a known reference story, e.g., a simple display story = **2 points**.
3. Each estimator privately selects an agreed scale (e.g., 1, 2, 3, 5, 8, 13); everyone reveals simultaneously to prevent anchoring.
4. Discuss reasoning behind **highest and lowest** estimates: missing error states, integration, unfamiliar code, test data or security.
5. Clarify or split the story if too large; vote again until the team reaches a defensible shared estimate. **Do not average votes mechanically.**
6. Compare with previous Done stories and adjust only when shared understanding genuinely changes.

**Worked estimation example:** Four team members vote **3, 5, 8, 5** for renewing a loan. The 8-point estimator identifies concurrent requests and existing hold checks that others overlooked. The team clarifies that a database transaction is required; after discussion, the new votes are **5, 5, 5, 5**. The agreed relative size is **5 points**. That does *not* specify 5 ideal days or 5 hours.

**Capacity planning example:** Last three Sprint velocities were **12, 15 and 18 points**; arithmetic mean = `(12 + 15 + 18)/3 = 15 points/Sprint`. For a similar-size, similarly staffed Sprint, this supports a **provisional** forecast near 15, not a promise. If planned stories total 17 points (5+8+4), do not claim guaranteed completion. Split or deprioritize the 4-point story, or explicitly acknowledge uncertainty; a selected 5+8 = **13-point** Sprint is closer to observed capacity. Use task-hour capacity separately to expose holidays, support duties and technical constraints.

## 3.6 Prioritization: WSJF, value, cost of delay and backlog discipline

**Correct source:** Leffingwell's *Agile Software Requirements*, Chapter **13**, discusses **Weighted Shortest Job First (WSJF)** using Cost of Delay (CoD) and effort; Chapter 7 instead develops stakeholder/persona/UX understanding. The goal is **economic sequencing**, not predicting development time from story points.

**Basic relative ranking formula:** `WSJF = Cost of Delay / Job Size (or Duration proxy)`. If delaying two features imposes unequal cost, a shorter feature with higher loss per unit wait can deserve earlier implementation. Quantities must use a consistent scale and definition. An often-used later scaled-agile **extension** breaks CoD into user/business value, time criticality and risk reduction/opportunity enablement; label this an extension rather than falsely assigning the exact formula to the requested Chapter 7.

**Worked backlog-priority problem:** The product owner estimates each feature's *relative* delay cost and size consistently:

| Feature | Illustrative CoD score | Job-size score | WSJF = CoD / size | Rank |
|:--|--:|--:|--:|:--:|
| A. Digital library receipts | 20 | 5 | 4.0 | 3 |
| B. Renewal reminders | 18 | 3 | 6.0 | 2 |
| C. Analytics dashboard | 30 | 10 | 3.0 | 4 |
| D. Broken-loan-link fix | 9 | 1 | 9.0 | **1** |

**Solution:** Compute each quotient, sort descending: **D -> B -> A -> C**. C has the largest absolute delay-cost score but is very large; D yields the highest relative urgency per size. **Sensitivity check:** if B is legally blocked or depends on A, the feasible delivery order may change. Revisit scores after new evidence; do not treat WSJF as an algorithm that overrides dependencies, minimum marketable capabilities, safety gates or Product Owner judgment. The numeric values are hypothetical ranking inputs, not monetary forecasts.

**Product Backlog good practice** (Rubin, Ch. 6; Leffingwell, team and product flow): keep **one transparent, ordered, evolving list** of product work; include features, defects, research, technical improvements and quality constraints when they require work; define an owner and clear value/risk; refine near-term items more deeply than distant ones; re-estimate when evidence changes; preserve testability and dependencies; remove obsolete work; manage high-risk external interfaces early. **Ordered** does not mean every item has a unique globally objective dollar value.

**Comparative analysis: estimation and prioritization are not interchangeable**

| Dimension | Story Points | Ideal Days | Task Hours | WSJF |
|:--|:--|:--|:--|:--|
| Answers | How relatively big/uncertain? | How much ideal focused work? | How much engineering effort remains? | Which item has highest estimated economic urgency per size? |
| Primary owner | Estimating delivery team | Estimating delivery team | Delivery team | Product Owner with stakeholders/team evidence |
| Unit | Team-relative points | Ideal workdays | Hours | Ratio of consistent cost-of-delay to size units |
| Useful for | Forecasting with empirical velocity | Work projection if conditions clarified | Sprint execution/burndown | Backlog ordering |
| Cannot legitimately prove | Calendar date by itself | Real elapsed date by itself | User value delivered by itself | Guaranteed value or complete release feasibility |

## 3.7 Fully worked exercise A - two epics, role modeling and four INVEST stories

**Problem:** Refine two epics into **exactly four** small, user-valued stories with explicit Given-When-Then acceptance scenarios. Identify relevant user roles, estimate relative sizes and check INVEST.

**EPIC E1 - Student library self-service.** "Allow students to manage loan renewals remotely." **EPIC E2 - Campus study-space reservations.** "Allow students to find and book available campus study rooms."

**Step 1 - role modeling:** see roles in Section 3.3. **Primary roles** E1: student borrower; **policy validator**: circulation librarian. E2: study-room requester; **inventory/policy validator**: facilities coordinator. A student with screen-reader needs participates in acceptance testing for both. Distinguish *user with a goal* from *administrator who governs the rules*.

**Step 2 - define deliberately limited pilot policy:** library: at most two renewals, +7 days, no active hold, not overdue; room booking: 30-minute slots, 08:00-20:00 campus local time, booking for same or next seven calendar days, maximum one active booking for the same slot; server serializes conflicting booking requests. These are **example assumptions to validate**.

**Story L-01 - Renew an eligible loan (5 SP).**

> As a **student borrower**, I want to **renew one eligible active book loan**, so that I can **keep the book longer without visiting the circulation desk**.

**Acceptance criteria:**

- **Scenario L01-A:** **Given** I am signed in, my loan is active, the due time has not passed, I have used one of my two renewals and there is no hold; **When** I select "Renew" and confirm; **Then** the system advances the stored due timestamp by exactly seven calendar days, increments the renewal count to two, and displays the new date/time.
- **Scenario L01-B:** **Given** another borrower has an active hold; **When** I request renewal; **Then** the system denies renewal, displays "Reserved by another borrower," and does not change the stored due timestamp or count.
- **Scenario L01-C:** **Given** I press confirm twice with the same request token; **When** the second request is processed; **Then** the system returns the same result without extending the due date a second time.

**Story L-02 - Understand a rejected renewal (3 SP).**

> As a **student borrower**, I want to **see why a renewal request was rejected and what due date still applies**, so that I can **return the book on time or seek assistance**.

**Acceptance criteria:**

- **Scenario L02-A:** **Given** my loan is past due and renewal is ineligible; **When** I attempt renewal; **Then** the portal displays "Loan overdue" and the unchanged due timestamp.
- **Scenario L02-B:** **Given** my loan has reached two renewals but is not overdue; **When** I attempt renewal; **Then** the portal displays "Renewal limit reached" and the existing due timestamp.
- **Scenario L02-C:** **Given** my renewal is denied; **When** I reopen the loan detail view; **Then** the denial reason recorded for that attempt and the authoritative due timestamp are shown consistently.

**Story R-01 - Find available rooms (3 SP).**

> As a **study-room requester**, I want to **see rooms available for a selected date and time**, so that I can **choose a feasible study location**.

**Acceptance criteria:**

- **Scenario R01-A:** **Given** two rooms are free and one is booked for 14:00-14:30; **When** I search for that interval; **Then** the result contains the two available rooms and excludes the booked one.
- **Scenario R01-B:** **Given** I select a time outside 08:00-20:00; **When** I submit the search; **Then** the system displays the supported time window and does not present unavailable rooms as bookable.
- **Scenario R01-C:** **Given** no room meets the requested interval; **When** I search; **Then** I see "No rooms available" rather than an empty, unexplained interface.

**Story R-02 - Reserve a selected room (5 SP).**

> As a **study-room requester**, I want to **reserve a free 30-minute room slot**, so that I can **rely on having a place to study**.

**Acceptance criteria:**

- **Scenario R02-A:** **Given** I am signed in and an eligible room/slot is free; **When** I confirm the reservation; **Then** the system creates exactly one reservation, shows its unique confirmation ID and removes that room/slot from others' available results.
- **Scenario R02-B:** **Given** two students try to confirm the same last slot concurrently; **When** both submissions execute; **Then** exactly one succeeds and the other receives "Slot no longer available," with no duplicate active reservation.
- **Scenario R02-C:** **Given** the date is more than seven calendar days ahead; **When** I try to reserve; **Then** the system rejects the request with the allowed booking window and records no reservation.

**Step 3 - explicit INVEST audit:**

| Story | I | N | V | E | S | T |
|:--|:--|:--|:--|:--|:--|:--|
| L-01 | Own renewal transaction; contract can be independently tested | UI details negotiable; policy guards fixed for pilot | Extra borrowing time | Eligible rules and interface known | 5-SP vertical slice | L01-A/B/C |
| L-02 | Independently shows previously recorded denial results; can be tested using seeded denied events | Message wording can be negotiated | Actionable due-date clarity | Known event fields | 3-SP vertical slice | L02-A/B/C |
| R-01 | Search works against seeded schedules without reservation UI | Presentation negotiable | Can choose feasible space | Read-only availability query known | 3-SP slice | R01-A/B/C |
| R-02 | Creates confirmed booking through a documented availability contract | Confirmation appearance negotiable | Reliable place to study | Concurrency policy defined | 5-SP vertical slice | R02-A/B/C |

**Nuance:** R-02 requires room inventory/availability data. "Independent" means it can be implemented/tested without forcing R-01's *interface* to be complete; dependency on a common domain model is acceptable and should be visible. L-02 requires a denied attempt to exist but can use seeded test fixtures and does not require L-01's UI to be deployed first.

**Step 4 - estimate and prioritize:** initial relative estimates L-01=5, L-02=3, R-01=3, R-02=5 (total **16 SP**). The Product Owner may order R-01 before R-02 to reduce integration risk, or L-01 first if exams/semester deadlines increase library urgency. A Sprint historical velocity of 13 suggests **do not automatically select all 16**. The estimates are explanatory examples, not facts about ESPOL development effort.

## 3.8 Fully worked exercise B - split a compound story three ways

**Original overlarge story:**

> "As a student, I want to search campus workshops, register, pay when necessary, receive a QR ticket, join a waitlist for full sessions, and get reminders on web and mobile so that I can attend activities conveniently."

**Diagnosis:** Multiple paths, interfaces, data types, rules and external payment/notification dependencies; likely not Small, Estimable or Independent. UI, backend and database subtasks alone would **not** be vertical user stories.

**SPIDR mnemonic (practical extension, not a chapter title in Cohn):** **Spike** (time-boxed investigation), **Paths** (workflows/alternates), **Interfaces** (channels or integrations), **Data** (different data scopes/types), **Rules** (business-policy variations). A **spike** reduces uncertainty and may produce an experiment/report, but it is not automatically a user-visible feature.

**Technique 1 - split by Paths (P):**

- **P1:** "As a student, I can register for an open **free** workshop so that I secure a confirmed place." Acceptance: available capacity -> confirmed enrollment ID; capacity decremented once.
- **P2:** "As a student, I can enroll in an open **paid** workshop after a successful payment authorization so that I secure a place." Acceptance: successful payment -> enrollment; failed payment -> no confirmed enrollment, no duplicate charge.
- **P3:** "As a student, I can join the waitlist of a full workshop so that I may receive a future offer." Acceptance: full session -> waitlist position; no confirmed seat yet.

**Why this is valid:** each path supports a complete user-visible outcome, not "build checkout backend."

**Technique 2 - split by Interfaces (I):**

- **I1:** "As a student on the responsive web portal, I can view my confirmed workshop enrollment and its QR ticket so that I can present it at check-in."
- **I2:** "As a student in the mobile app, I can view that same confirmed enrollment and QR ticket so that I can check in without web navigation."

**Why valid:** both deliver a real channel-specific journey with authentication, data retrieval, usable display and tests. An API task may be shared internally, but it is not a stand-alone user story.

**Technique 3 - split by Rules (R):**

- **R1:** "As a student, I can register for an open workshop with available seats so that I obtain a confirmed enrollment." Guard: no schedule conflict/duplicate booking within defined policy.
- **R2:** "As a student, when the last seat is taken by another concurrent request, I receive a precise refusal and a waitlist option so that I do not assume I am registered." Guard: single allocation under concurrency.
- **R3:** "As a student, I can cancel a confirmed free-workshop enrollment before the published cutoff so that another student can use the seat." Guard: the explicit cutoff, not unspecified "reasonable time."

**Why valid:** the team can learn from one rule-complete path, then extend into more complex policies; acceptance tests distinguish boundary cases.

**Optional Technique 4 - Data (D):** support workshops with only title/date/venue first, then workshops with prerequisites/material requirements; both cases should keep a complete, useful discover-and-register interaction if they are to be stories.

**Spike (S), if payment API uncertainty is dominant:** "In <= 8 engineer-hours, confirm the provider's sandbox payment-idempotency behavior and document the minimal compatible contract, failure scenarios and go/no-go decision." Output: verified experiment, not an independently sellable user capability. Put the resulting product work into one or more vertical payment stories.

**Step-by-step refinement plan:**

1. Separate the compound outcome into free registration, paid registration, waitlist, ticket and reminder paths.
2. Choose the **minimum valuable walking skeleton**: free workshop search -> register -> view confirmation, with no payment or reminders.
3. Agree on policy and write Given-When-Then scenarios for capacity, duplication and cancellation.
4. Estimate the smaller stories individually. If one remains > Sprint capacity, split again by a legitimate path/rule, not by "frontend vs. backend."
5. Sequence external payment risk early (spike + sandbox contract), without blocking the release of free registration.
6. Ensure each selected story can meet the *whole* Definition of Done, including security, integration and acceptance checks.

**Answer to a common examination challenge:** "Split the feature by database, UI and API" is a **horizontal technical decomposition**, useful *within* a Sprint Backlog but not generally three independent user-valued Product Backlog stories.

## Module 3 - rapid examination checks

1. **Who owns ordering vs estimating?** Product Owner is accountable for Product Backlog ordering; developers collectively estimate implementation size.
2. **Does 5 points mean 5 hours?** No. Relative story points are different from task-hour estimates.
3. **Can a spike be a user story?** It is generally a time-boxed knowledge-acquisition item; identify its learning objective and output, rather than claiming a user-visible increment by itself.
4. **INVEST 'I' absolute independence?** No; minimize hidden dependencies and keep each story demonstrably valuable.
5. **WSJF vs velocity?** WSJF orders *value relative to size*; velocity records *completed story-point volume per Sprint*.

**Sources for Module 3:** Cohn, *User Stories Applied*, Chs. 1, 2, 3, 7, 8, 12, 13, 14; Rubin, *Essential Scrum*, Chs. 5-6; Leffingwell, *Agile Software Requirements*, Chs. 6, 7 and 13; Lecture 2, PDF pp. 58-59 (story context); Lecture 3b, PDF pp. 19, 23-25 (backlogs/task breakdown); International Scrum Institute, sections on stories, Planning Poker and Product Backlog.

---
# MODULE 4 - THE SCRUM FRAMEWORK, EXECUTION AND METRICS

## 4.1 What Scrum is and is not

**Scrum** is a lightweight, empirically controlled framework for addressing complex product work using short, timeboxed Sprints, transparent work, inspection and adaptation. It is **not** a guarantee of on-time/on-budget success, a prohibition on architecture/design/documentation, or a mandate to skip technical engineering. The course slides say teams add appropriate engineering practices to the Scrum framework (Lecture 3b, PDF pp. 4-5); Rubin's *Essential Scrum* supplies the deeper principles and practices. **Empiricism:** make important current information visible (**transparency**), examine results (**inspection**), and change the plan when evidence requires (**adaptation**).

**High-yield temporal model:** Product Backlog -> Sprint Planning -> Sprint Backlog + Sprint Goal -> Daily inspection and integrated construction/testing -> Done Increment -> Sprint Review (inspect product and stakeholders' needs) -> Sprint Retrospective (inspect way of working) -> next Sprint. **Product Backlog Refinement** occurs continuously and is not a separate official Scrum event.

## 4.2 The three roles: accountabilities and limits of authority

| Role in ESPOL / Rubin vocabulary | Owns or is accountable for | Makes decisions about | Must not be confused with |
|:--|:--|:--|:--|
| **Product Owner** | Maximizing product value; creating/communicating Product Goal/vision; ordering and making Product Backlog transparent | What to prioritize, clarify, accept as product direction; value and trade-offs | A committee whose every member can independently reorder the backlog; a task-assigning line manager |
| **ScrumMaster** | Scrum effectiveness; coaching, facilitating improvement, enabling removal of impediments | How to help team and organization use Scrum; surfacing obstacles | A project manager who assigns engineering tasks or personally approves all code |
| **Development Team** (modern term: **Developers**) | Building a high-quality, usable Done Increment; Sprint planning, task plan and quality | How much work to select within capacity, design/implementation/test approach and day-to-day adaptation toward Sprint Goal | A collection of isolated roles that require Product Owner approval to collaborate |

**Course team size:** Lecture 3b, PDF p. 13, describes **5-9 people in the development team**; this is a lecture-era recommendation, not a law of nature. **Contemporary Scrum Guide terminology (2020) differs:** it speaks of **Product Owner, Scrum Master, Developers** as accountabilities and describes a **Scrum Team typically 10 or fewer people**. If the exam asks "according to the slides," answer 5-9 development-team members and use the slide's role labels; if asked about the current Scrum Guide, use the updated wording. The Product Owner can delegate backlog-item drafting but remains accountable for ordering.

## 4.3 The five events and continuous refinement

| Scrum event (5 official events including the Sprint) | Purpose | Main participants | Timebox in a one-month Sprint | Principal evidence/output |
|:--|:--|:--|:--|:--|
| **Sprint** | Fixed-length container for all work producing a useful, Done Increment; no gap between Sprints | Whole Scrum Team | **1 month or less** | Sprint Goal, Increment; change managed as new learning emerges |
| **Sprint Planning** | Decide why Sprint is valuable (goal), which items can be Done, how work will be achieved | Scrum Team | **Up to 8 hours** | Sprint Goal + selected items + actionable delivery plan = Sprint Backlog |
| **Daily Scrum** | Inspect progress toward Sprint Goal and adapt next 24-hour plan | Developers | **15 minutes** | Updated plan, surfaced dependencies/impediments |
| **Sprint Review** | Inspect working product with stakeholders and adapt Product Backlog/next priorities | Scrum Team + invited stakeholders | **Up to 4 hours** | Product feedback, amended Product Backlog as appropriate |
| **Sprint Retrospective** | Inspect and improve practices, collaboration and quality | Scrum Team | **Up to 3 hours** | Actionable improvement for upcoming Sprint |

Timeboxes for shorter Sprints typically scale down except the Daily Scrum. The Sprint contains the other four events, so a common incorrect answer counts only four events. **Lecture-era Daily Scrum questions** (Lecture 3b, p. 33): What did I do? What will I do? What obstacles exist? These are useful prompts but **not mandatory scripts** in modern Scrum; the Daily is for coordinating work toward the Sprint Goal, not reporting to the Scrum Master.

**Refinement/grooming:** the ongoing act of decomposing and discussing Product Backlog Items, elaborating acceptance criteria, estimating, ordering, identifying dependencies and removing obsolete items (Lecture 3b, pp. 16, 19; Rubin, Ch. 6). Scrum does not prescribe a separate formal "sixth event" named grooming or a universal exact timebox. Avoid overplanning distant, high-uncertainty work; refine near-term candidates until the team can sensibly discuss completing them.

## 4.4 Three artifacts, commitments, and levels of detail

| Artifact (course-era name) | Core contents | Purpose | Related commitment in modern Scrum Guide |
|:--|:--|:--|:--|
| **Product Backlog** | Ordered, evolving list of work needed to improve the product; features, defects, risks, quality/debt work as appropriate | Single transparent view of product work and relative priority | **Product Goal** |
| **Sprint Backlog** | Sprint Goal; selected Product Backlog Items; adaptable plan/tasks to deliver them | Developers' current forecast and plan; updated daily as knowledge grows | **Sprint Goal** |
| **Potentially Shippable Product Increment** (now commonly **Increment**) | Integrated result of all Done work meeting shared quality requirements; usable and verifiable | Makes empirical product inspection possible | **Definition of Done** |

"Potentially shippable" does **not** mean every Sprint must be publicly released, nor that incomplete untested code counts as a finished increment. A usable Increment can be released earlier than the Sprint Review if organizational policies permit. The Sprint Goal gives a reason for the selected work, not a rigid promise that every original task must remain unchanged.

### Definition of Done (DoD) versus acceptance criteria

**Acceptance Criteria:** story-specific conditions that verify a particular outcome. Example: "If a room is concurrently booked by another student, the second request is rejected without a duplicate reservation." These differ between Product Backlog Items.

**Definition of Done:** one shared, product-level quality threshold for *every* increment/PBI, with relevant organizational standards. Illustrative DoD: code reviewed and merged; all mandatory unit/integration/security tests pass; acceptance criteria pass; critical defects resolved or work not declared Done; accessibility requirements met; build integrated and deployable; release notes/operational evidence updated; observability available. **A passing acceptance criterion alone does not establish Done** if integration/security tests fail. Likewise a fully tested technical task does not prove the user story's acceptance criteria are fulfilled.

**Comparison:**

| Property | Acceptance Criteria | Definition of Done | Definition of Ready (optional practice) |
|:--|:--|:--|:--|
| Scope | Specific story / PBI | Every Increment/PBI governed by team/organization standard | Shared entry heuristic before planning |
| Main question | "Does this behavior meet its user rules?" | "Is the integrated result usable and meets the quality bar?" | "Do we understand the item enough to consider it?" |
| Example | New due date = old due date +7 days | Tests green, integrated, reviewed, security/accessibility checked | Role, value, AC and dependencies reasonably clear |
| Status in Scrum | Good supporting technique, not a separate official artifact/commitment | **Official Increment commitment** in current Scrum | **Not required** by formal Scrum; should not become a bureaucratic gate |

## 4.5 Scrum values: lecture vs. modern edition, and six principle families

**The lecture's eight stated values** (Lecture 3b, PDF p. 40) are: **Honesty, Openness, Courage, Respect, Focus, Trust, Empowerment, Collaboration**. These are the values to reproduce if a course question explicitly references that slide. **The modern official Scrum Guide's five values** are **Commitment, Focus, Openness, Respect, Courage**. Do not silently substitute one list for the other; they are different formulations.

**Rubin's six families of Scrum principles**, shown in the slide mind-map at Lecture 3b pp. 42-48, are detailed below. These are **families of principles** rather than the modern Scrum Guide's three pillars of empiricism (transparency, inspection, adaptation).

| Principle family | What the slides visualize | Concrete engineering meaning |
|:--|:--|:--|
| **1. Variability and Uncertainty** | Embrace helpful variability; use iterative/incremental development; leverage variability by inspection/adaptation/transparency; reduce uncertainty early. | Do not pretend to know all requirements/design; use small experiments, early integration and feedback loops. |
| **2. Prediction and Adaptation** | Keep options open; accept you cannot get everything right up front; prefer adaptive exploratory work; embrace economically sensible change; balance predictive up-front and just-in-time work. | Plan enough to manage risk and dependencies, but replan from current evidence; do not cling to a disproved Gantt chart. |
| **3. Validated Learning** | Validate important assumptions fast; leverage multiple concurrent learning loops; organize workflow for fast feedback. | Demonstrations, automated tests, stakeholder review, prototypes and real use generate evidence earlier. |
| **4. Work in Process (WIP)** | Economically sensible batch size; recognize inventory and manage its flow; focus on idle work rather than idle workers; consider cost of delay. | Limit simultaneous unfinished stories, reduce handoffs and queues, finish before starting more work. |
| **5. Progress** | Adapt to real-time information and replan; validate working assets; focus on value-centric delivery. | Count Done, integrated capabilities and verified outcomes, not just consumed hours or "90% coded" labels. |
| **6. Performance** | Go fast but never hurry; build in quality; employ minimally sufficient ceremony. | Engineering discipline, sustainable pace and automation create faster *reliable* flow than rushed low-quality output. |

**Why WIP matters:** If five stories are each 80% finished, users may have zero shippable capability; completing two end-to-end stories creates real progress and shortens feedback delay. **Flow time** tends to worsen when more work is started than can be completed. Avoid the false goal of keeping every engineer 100% busy while high-priority stories wait in review queues.

## 4.6 Burndown, velocity, scope and WIP - do not conflate the numbers

- **Sprint burndown:** remaining *estimated work* on the vertical axis and days on the horizontal axis. It can be measured in **task-hours**, points or item counts, but never mix units on one unlabeled axis. Lecture 3b uses Sprint Burndown examples (PDF pp. 29-31), and the International Scrum Institute has a dedicated section on burndown.
- **Ideal burndown (in hours):** `B_ideal(d) = B0 x (1 - d/D)`, where `B0` is beginning remaining work, `D` is Sprint days and `0 <= d <= D`. It is a guide, not a promised actual profile.
- **Actual remaining work update:** `B_today = B_yesterday - work_completed_on_estimate + added_scope + upward_reestimation - removed_scope - downward_reestimation`. The equation is a *bookkeeping model*; teams must record which causes explain changes.
- **Velocity:** `V = sum(story points for fully Done PBIs in Sprint)`. A Sprint can burn many engineering hours with low velocity if stories fail the DoD. Velocity is not a cross-team productivity ranking.
- **Scope creep vs. re-estimation:** an **added requirement or increased agreed scope** is scope change; discovering an underestimated existing task is **re-estimation**. Both may make the line rise but imply different management actions.
- **Lead time / cycle time:** lead time from a request's entry to delivery; cycle time from active work start to Done. Useful for flow but not the same as velocity or effort.
- **WIP:** work started but not finished; count and age it to identify queues, blocked reviews, integration congestion and context switching.

## 4.7 Worked exercise A - break two stories into tasks of at most 16 hours

**Problem:** The team selects two stories from Module 3: **L-01** (renew eligible book, **5 story points**) and **R-02** (reserve room, **5 story points**). Engineering tasks must be <=16 hours each per Lecture 3b, p. 25. Create actionable tasks that together cover functional behavior, testing, integrations and quality, and calculate estimated remaining work.

**Step 1 - confirm preconditions and Done.** L-01 has approved rules for eligibility, concurrency and due date; R-02 has approved booking window and atomic conflict behavior. The team understands the common identity service, transaction database and required tests. DoD requires reviewed, integrated, tested, accessible and deployment-ready code.

**Step 2 - L-01 task breakdown:**

| Task ID | Engineering task (L-01) | Estimate (h) | Acceptance/quality link |
|:--|:--|--:|:--|
| L1-T1 | Refine policy rules, boundary examples and test data | 4 | L01-A/B/C agreed |
| L1-T2 | Add/polish loan-renewal data fields and migration with rollback | 6 | Due date and count consistent |
| L1-T3 | Implement account ownership and eligibility validation incl. holds | 8 | L01-A/B + authorization |
| L1-T4 | Implement atomic renewal operation with idempotent request key | 8 | L01-C and concurrent retry |
| L1-T5 | Implement renewal action and feedback in accessible borrower UI | 6 | User-visible outcome |
| L1-T6 | Build automated happy-path and negative acceptance tests | 4 | L01-A/B |
| L1-T7 | Perform concurrency/security regression, review and integrate | 4 | L01-C + DoD |
| **TOTAL** | | **40 h** | **5 SP if and only if Done** |

**Step 3 - R-02 task breakdown:**

| Task ID | Engineering task (R-02) | Estimate (h) | Acceptance/quality link |
|:--|:--|--:|:--|
| R2-T1 | Finalize 30-minute policy/confirmation scenarios | 4 | R02-A/B/C |
| R2-T2 | Implement reservation persistence and unique confirmation ID | 6 | R02-A |
| R2-T3 | Implement atomic free-slot check and conflicting booking rejection | 8 | R02-B |
| R2-T4 | Build accessible confirm/cancel-navigation and result UI | 6 | R02-A/C |
| R2-T5 | Write end-to-end, boundary and concurrency test suite | 8 | R02-A/B/C |
| R2-T6 | Run keyboard/screen-reader and permission checks | 4 | DoD, usability/security |
| R2-T7 | Review, CI integration, operational metrics and release notes | 4 | DoD/Increment |
| **TOTAL** | | **40 h** | **5 SP if and only if Done** |

**Step 4 - calculate capacity and scope.** Sprint workload for these two stories = `40 + 40 = 80 task-hours`. Planned story-point value = `5 + 5 = 10 SP`. Every task is **<= 8 hours**, therefore satisfies the lecture's **<=16-hour** recommendation. The 80 hours are *remaining estimated work* at planning, not guaranteed actual clock time. The team should compare these hours with actual effective capacity, dependencies and the Sprint Goal, and reserve capacity for interrupts; points and hours must not be divided to create a universal conversion ratio.

**Step 5 - Sprint Goal:** "Students can reliably renew eligible loans and confirm conflict-free room reservations." Selected stories are coherent as a campus self-service goal, but both must meet the same DoD. Replanning tasks during the Sprint is allowed if the goal remains meaningful.

## 4.8 Worked exercise B - 10-day Sprint Burndown analysis and velocity

**Given:** A 10-day Sprint starts with **80 estimated task-hours** across the two stories from Section 4.7 (each 5 SP). On **Day 5**, the Product Owner and Developers agree to add **12 hours of genuinely new room-confirmation notification work** (for illustration, split into two new 6-hour tasks) without removing existing work. The library story reaches Done by Day 10; the room story has 10 hours remaining and fails DoD. The table measures remaining estimated hours at the end of each day. There are **no other explicit re-estimations or scope removals** in this exercise.

**Dataset:**

| Day | Ideal remaining (h) | Actual remaining (h) | Net daily reduction (h) | Notes |
|:--:|--:|--:|--:|:--|
| 0 | 80 | 80 | - | Sprint start, 80 h baseline |
| 1 | 72 | 76 | +4 | Slow startup/test fixtures |
| 2 | 64 | 70 | +6 | Implementation progresses |
| 3 | 56 | 65 | +5 | Integration work begins |
| 4 | 48 | 65 | **0** | Blocker: test identity environment unavailable |
| 5 | 40 | 68 | **-3** | +12 h agreed new scope; 9 h of work burned |
| 6 | 32 | 58 | +10 | Blocker removed; team swarms on pending work |
| 7 | 24 | 47 | +11 | Integration/test execution |
| 8 | 16 | 35 | +12 | More completed work |
| 9 | 8 | 19 | +16 | Fast progress but still behind baseline |
| 10 | 0 | **10** | +9 | L-01 Done; R-02 not Done |

**Step 1 - calculate the ideal line.** Ten working days with 80h start gives `80/10 = 8h/day` of *ideal aggregate decline*. Therefore Day 4 ideal = `80 - 4 x 8 = 48h`; Day 7 ideal = `80 - 7 x 8 = 24h`; Day 10 ideal = `0h`. This is the straight-line comparison, not a mandate for exactly eight hours every day.

**Step 2 - calculate daily reductions.** For days without scope changes: Day 1 = `80 - 76 = 4h`; Day 2 = `76 - 70 = 6h`; Day 3 = `70 - 65 = 5h`; Day 4 = `65 - 65 = 0h`. On Day 5, remaining effort *rises* by 3h (`68 - 65 = 3h`), but this does **not** mean engineers completed negative work. New scope is 12h, so completed work that day = `65 + 12 - 68 = 9h`. Other days: Day 6 = `68 - 58 = 10h`; Day 7 = `58 - 47 = 11h`; Day 8 = `47 - 35 = 12h`; Day 9 = `35 - 19 = 16h`; Day 10 = `19 - 10 = 9h`.

**Step 3 - reconcile the arithmetic.** Total explicitly planned plus new scope = `80 + 12 = 92h`. Total completed estimated work is `92 - 10 = 82h`. Check by summing daily gross work: `4+6+5+0+9+10+11+12+16+9 = 82h`. Day 10's 10h is **remaining work**, not proof that only 10 hours were used or that the Sprint was "90% successful" in user-value terms.

**Step 4 - calculate *velocity*, not hours.** Planned story points = `5 + 5 = 10 SP`. Actual **Done** story points = **5 SP** from L-01, because R-02 is unfinished and fails DoD. Thus `Velocity = 5 SP / Sprint`, not 82 points, 82 hours, 9.1 points, 10 points or "90% of the scope". R-02's **5 points are not awarded in fractional form** for having only 10 estimated hours left. If R-02 is fully Done in the next Sprint, it counts in that Sprint's velocity under normal completed-item accounting. The new notification work changed effort and may merit new Product Backlog splitting/re-estimation, but does not grant partial points now.

**Step 5 - spot bottlenecks and scope change.** (i) Day 4 flatline indicates a **blocker**; use Daily Scrum to escalate environment access, shift work to unblocked tests and fix the systemic issue in the Retrospective. (ii) Day 5 increase and explicitly recorded +12h indicate **scope expansion**, not a simple unexplained estimate correction. (iii) Days 6-10 show faster aggregate reduction but still miss ideal endpoint; a large late burn may also conceal work-in-progress/testing convergence risk. (iv) Finishing L-01 yielded real value; R-02 being 10h short makes the Increment incomplete for that story.

**Step 6 - practical response.** Protect the Sprint Goal by discussing the added notification change with the Product Owner, removing/reordering less important work where possible rather than quietly expanding commitment. Limit WIP, swarm on integration, prevent environment outages with pre-Sprint readiness checks, and split future complex booking features into independently Done slices. Review source data and differentiate *real completed work* from a downward re-estimate before declaring recovery.

### Diagnostic examination questions and fully worked answers

**Q1. On which day is the largest positive deviation from the ideal curve?** Compute `Actual - Ideal`: Day 4 `65 - 48 = 17h`; Day 5 `68 - 40 = 28h`; Day 6 `58 - 32 = 26h`; Day 7 `47 - 24 = 23h`; Day 8 `35 - 16 = 19h`; Day 9 `19 - 8 = 11h`; Day 10 `10 - 0 = 10h`. **Maximum = Day 5, 28h behind the original ideal line.** This combines delayed work and added scope and is not solely poor execution.

**Q2. How much work was completed by the end of Day 5?** Cumulative = `80 + 12 - 68 = 24h` of estimated work. Cross-check `4 + 6 + 5 + 0 + 9 = 24h`.

**Q3. Why is the remaining-work curve rising on Day 5?** Because the scope increases by 12h and 9h are completed, yielding `+12 - 9 = +3h` net remaining work. Without an annotated scope-change log, a chart alone cannot distinguish that from upward re-estimation.

**Q4. Did the team deliver 90% of its commitments?** In task-hour terms, `82/92 = 89.13%` of the updated estimated work was completed. However **only one of two stories met DoD and only 5 of 10 originally planned points are Done**. The best exam answer distinguishes effort burn from finished, integrated user value; neither percentage automatically represents accepted business outcomes.

**Q5. If a supervisor declares both stories 90% complete and assigns 9 points of velocity, what is wrong?** Scrum velocity counts **Done Product Backlog Items** in full. Partial task progress is not fractional story value; **correct velocity is 5 SP**.

**Q6. What is the naive remaining-time projection from late-Sprint slope?** Across Days 6-10, actual remaining drops from 58h to 10h in four day-to-day intervals, roughly `48/4 = 12h/day`. Linear extrapolation suggests about `10/12 ~= 0.83 working day` of comparable effort. **It is not a release commitment:** the remaining work might require external approval, testing or coordination, and future velocity must be forecast from completed stories rather than mechanically converting hours to points.

**Q7. Who addresses each issue?** Developers update the Sprint Backlog, estimate work, collaborate and complete tests; Product Owner negotiates product value and ordering/scope trade-offs; Scrum Master helps remove systemic blockers and improve Scrum effectiveness; stakeholders assess working functionality in the Review. Retrospective addresses recurrence of the identity-test-environment blocker.

## 4.9 Further applied scenario - confusion among Scrum artifacts

**Question:** The Product Owner brings a new compliance request on Day 7. A developer unilaterally inserts it into the Sprint, another calls a branch "the Increment" although its tests fail, and a manager says the Sprint Review is for rating individual developers. Diagnose.

**Worked answer:** (1) The new compliance request belongs in the **Product Backlog** for transparent ordering; if it affects the Sprint Goal, the Product Owner and Developers discuss adaptation and risk, not silent insertion. (2) A branch with failing DoD criteria is **not part of the Done Increment**; integrate and verify before claiming completion. (3) **Sprint Review** inspects the product and adapts priorities with stakeholders; individual evaluation is not its Scrum purpose. (4) **Sprint Retrospective** is for team/process improvement, including late requirement handling and test discipline. (5) If regulation changes and threatens the goal, reassess feasibility, evidence and stakeholders; agility does not excuse noncompliance.

## Module 4 - rapid examination checks

1. **Five events?** Sprint, Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective. **Refinement is ongoing**, not a sixth official event.
2. **Three artifacts?** Product Backlog, Sprint Backlog, Increment (course: potentially shippable increment). Know their commitments in contemporary terminology.
3. **Who orders backlog?** Product Owner. **Who chooses technical tasks?** Developers collectively.
4. **What do you measure for burndown?** Remaining estimated work in a consistent unit; annotate added/removal/re-estimated scope.
5. **What produces velocity?** Fully Done story points in that Sprint, not task-hour burn or percentage coded.
6. **What is the course task cap?** 16 hours per task (Lecture 3b, PDF p. 25); the course's practical convention, not a universal Scrum rule.
7. **Review vs. Retro?** Product/outcome vs. people/process/quality improvement.
8. **Eight vs. five values?** Give the lecture's eight when asked about its slide; the modern five when asked about the current official Scrum Guide.

**Sources for Module 4:** Lecture 3b, PDF pp. 4-53; Rubin, *Essential Scrum*, Chs. 2, 3, 4, 5 and 6; International Scrum Institute, *The Scrum Framework* (roles, user stories, DoD, backlogs, planning poker, burndown and Scrum meetings); Cohn, *User Stories Applied*, Ch. 15 for Scrum integration (extra extension); modern Scrum Guide terminology is separated explicitly from the lecture-era course framing.

---

# FINAL EXAM - HIGH-YIELD SYNTHESIS AND SELF-CHECK

## A. One-screen distinctions worth memorizing

| Pair often confused | Correct distinction |
|:--|:--|
| Sommerville's 4 vs. Pressman's 5 | Product engineering essentials **Specification/Development/Validation/Evolution** vs. engineering framework **Communication/Planning/Modeling/Construction/Deployment**. |
| Process model vs. process activity | A model organizes how work happens; activity describes a type of work that occurs in most models. |
| Incremental vs. iterative/evolutionary | Incremental adds **usable scope**; evolutionary/iterative **learns/revises** through repeated cycles; they can coexist. |
| Waterfall vs. V-Model | Both plan-driven; V visualizes the corresponding test/QA relationship for each specification/design level. |
| Spiral vs. prototyping | Spiral is **explicitly risk-driven** and milestone-committed; prototyping is one possible risk-reduction technique. |
| RUP phase vs. discipline | **Inception/Elaboration/Construction/Transition** are maturity phases; nine workflows recur across them. |
| Problem vs. solution domain | Stakeholder goals/constraints vs. implementable system behavior/architecture. |
| User vs. system requirement | Stakeholder-readable capability/constraint vs. detailed behavior and operational conditions. |
| FR vs. NFR | **What behavior** vs. quality/development/external constraint; an NFR can generate additional FRs. |
| Availability vs. reliability vs. POFOD | Proportion of time operational vs. time-to-failure behavior vs. probability of failure on a valid demand. |
| Card vs. story | Short card is a placeholder; story = **Card + Conversation + Confirmation**. |
| Acceptance criteria vs. DoD | Per-story satisfaction conditions vs. shared minimum quality bar for Done work. |
| Velocity vs. burndown | Completed story-point volume vs. remaining estimated work over days. |
| WSJF vs. story points | Prioritization ratio reflecting economic delay cost/size vs. team-relative implementation estimate. |
| Scrum Review vs. Retrospective | Inspect/adapt **product** vs. **work system/team practices**. |
| Scope creep vs. estimate revision | New agreed work vs. changed forecast for already agreed work. |

## B. A 15-minute mock oral examination - questions and correct reasoning

1. **A hospital interface is fixed and certified, but the UI is unknown. Which process?** Primary V-Model assurance with incremental delivery, plus a targeted UI prototype; explain why single-label answers can miss the dual need.
2. **Does "Scrum means no documentation" follow?** No. Documentation/traceability must meet product risk, future maintenance and regulation; Scrum does not ban it.
3. **A 99.9%-available service fails 1 in 500 payment decisions. Is it reliable?** Availability alone does not establish transaction correctness. POFOD `1/500 = 0.002` is a separate dependability measure.
4. **"Users must have secure access" - where does it go?** Product-Security NFR; derive precise authentication, authorization, session revocation and audit FRs; add external driver if relevant.
5. **A product owner says to estimate a feature by its commercial value. Correct?** No: team-relative points estimate size/uncertainty; economic value informs ordering, such as WSJF.
6. **Can a prototype be directly deployed?** Only if deliberately built/evolved to the production-quality DoD; throwaway exploratory prototypes are not automatically deployable.
7. **A RUP project is in Construction. May it run tests and refine requirements?** Yes. Disciplines overlap and work iterates.
8. **How does a state transition model differ from a DFD?** State model describes allowable states/events/guards; DFD describes data sources, stores, transformations and outputs.
9. **Is a Sprint a task assignment batch?** No: a timebox with a Sprint Goal and an integrated usable Increment, with Developers self-managing.
10. **Burndown rises; did productivity become negative?** Not necessarily; inspect added scope and re-estimates. Derive net remaining change explicitly.

## C. Formula sheet

- **Availability (simplified steady-state repairable case):** `A ~= MTTF / (MTTF + MTTR)`; with the correct operational definitions, some teams use `MTBF` for mean cycle length instead.
- **Allowed monthly downtime:** `T_total x (1 - A_target)` (only the defined measurement windows count).
- **POFOD:** `failed demands / valid demands` (requires consistent demand definition and statistical qualification for confidence claims).
- **Defect density:** `number of qualifying defects / Function Points` (define numerator's scope).
- **WSJF:** `Cost of Delay / Job Size` (comparability of units and inputs is essential).
- **Velocity:** `SUM(story points of Done PBIs in the Sprint)`; no partial credit for unfinished stories.
- **Ideal remaining hours, day d:** `B0 x (1 - d / number_of_Sprint_days)`.
- **Remaining effort reconciliation:** `new remaining = previous remaining + added scope + upward re-estimates - completed work - removed scope - downward re-estimates`.
- **Simple risk exposure (heuristic):** `probability of loss x loss impact` (qualitative safety decisions also consider severity and unacceptable harm).

## D. Academic bibliography and precise study targets

**ESPOL lecture materials (2026, provided PDFs):**

- Dra. Villavicencio and Dr. Carlos Mera Gomez. *Software Processes*, Lecture 1b. Consult PDF pp. 4-10, 16-18, 24-29, 32-34.
- Dra. Villavicencio and Dr. Carlos Mera Gomez. *Software Process Models / Agile Software Development*, Lecture 2. Consult PDF pp. 4-17, 19-30, 33-48, 61-68, 73-76; **graphics p. 30 (concurrent states), p. 35 (components), p. 45 (RUP matrix), p. 74 (Boddy profile)**.
- Dra. Villavicencio and Dr. Carlos Mera Gomez. *Requirements Engineering*, Lecture 3a. Consult PDF pp. 4-14, 16-31, 33-41; **graphic p. 21 (NFR hierarchy)**, p. 19 (library drill).
- Dra. Villavicencio and Dr. Carlos Mera Gomez. *Scrum Framework*, Lecture 3b. Consult PDF pp. 4-38, 40-51; **graphic p. 7 (practices map)** and **pp. 42-48 (principle mind maps)**.

**Provided textbooks:**

- Sommerville, Ian. *Software Engineering*, 10th ed. Chs. 2-4 and 16 supply the software-process, requirements and CBSE foundations. Additional dependability topics refine NFR discussions.
- Rubin, Kenneth S. *Essential Scrum*. **Assigned** Chs. **2, 4, 5**; **supplementary** Chs. 3 (principles) and 6 (Product Backlog), plus execution chapters as relevant.
- Cohn, Mike. *User Stories Applied*. **Assigned** Chs. **1, 2, 7, 12, 13, 14**; **supplementary** Ch. **3** (role modeling), Ch. **8** (estimating), with splitting examples throughout the book.
- Wiegers, Karl, and Joy Beatty. *Software Requirements*, 3rd ed. **Assigned** Chs. **10-11** (documentation and writing); **supplementary** Ch. **7** (elicitation), Ch. **12** (data-flow/state and other analysis models), Ch. 14 (nonfunctional quality attributes).
- Leffingwell, Dean. *Agile Software Requirements*. **Assigned** Chs. **6-7** (user stories; stakeholders, personas and UX); **supplementary** Ch. **13** (cost of delay and WSJF prioritization).
- International Scrum Institute. *The Scrum Framework*, 3rd ed. User Stories, Estimation/Planning Poker, Definition of Done, Product/Sprint Backlogs, Burndown, Planning, Daily Scrum, Review, Retrospective and Refinement.
- IEEE Computer Society. *SWEBOK Guide*, v4.0a, 2026. Knowledge area: Software Requirements (supporting formal definitions and elicitation/specification/validation distinctions).

**Attribution note:** Pressman and Maxim are referenced through the *course slides*, because a separate full Pressman text was not provided. Boehm anchor milestone names, SPIDR and modern Scrum Guide comparisons are **explicit extensions** rather than quotations from these particular assigned chapters. The scenario policies, numbers, thresholds, planning scores and estimates in the exercises are illustrative classroom assumptions, not real customer agreements or official grading rubrics.

**End of master guide.**
