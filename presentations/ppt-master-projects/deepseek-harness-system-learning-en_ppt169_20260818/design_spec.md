<!-- ppt-master-schema: design-spec/v1 -->
# DeepSeek Harness System Learning EN - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | DeepSeek Harness System Learning EN |
| Canvas Format | PPT 16:9 |
| Page Count | 24 |
| Primary Language | en-US |
| Target Audience | Engineering leaders, Agent platform architects, AI developers, and product strategists evaluating global and China markets. |
| Communication Intent | First teach DeepSeek Harness runtime, Cordis, Session, interface, and Plugin mechanisms; then use enterprise-security boundaries and a three-layer market model to support architecture review, technology selection, and follow-on experiments. |
| Desired Audience Outcome | The audience can retell four core questions, explain the key mechanisms and limitations, distinguish runtime, developer product, and enterprise platform, and approve or execute a reproducible 90-day evaluation. |
| Core Message / Ask / Action | DeepSeek Harness is worth studying for its composable control plane and event-driven state; adoption must be decided by enterprise-control evidence and real-task experiments, not stars or a self-hosted label. |
| Delivery Context | Primarily a presenter-led technical session of about 32 minutes; secondarily a reader-led reference for architecture reviews and bilingual cross-team circulation. |
| Artifact Afterlife | A bilingual learning asset, architecture and enterprise-readiness review attachment, market-analysis reference, and hand-off record for comparative experiments. |
| Reading Mode | balanced |
| Content Strategy | Follow the validated 24-page deck-design.json exactly: preserve narrative, order, conclusions, citations, and visual intent; permit only equivalent English localization and PowerPoint implementation adjustments. |
| Design Style | Circuit Atlas: deep-navy chapter pages, light mechanism pages, signal-cyan paths, modular nodes, and editable evidence diagrams. |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy |
| Custom Animations | disabled — final Stage-2 proactive policy |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-08-18 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 13.333 × 7.5 in |
| viewBox | `0 0 1280 720` |
| Margins | 64 px horizontal; 48 px vertical safe area |
| Content Area | x=64–1216, y=48–672 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, pyramid
- **Mode Behavior**: Use instructional sequencing to move from four core questions through runtime, Cordis, Session, interfaces, and plugins; switch to pyramid logic for enterprise boundaries, market position, and the 90-day evaluation by stating the judgment before evidence and action. Titles teach or decide, and chapter transitions explicitly recap what is known and what comes next.
- **Visual style**: custom
- **Visual Style References**: blueprint, dark-tech
- **Visual Style Behavior**: Blueprint supplies thin frames, engineering grids, coordinate-like annotations, and architecture connectors; dark-tech supplies deep chapter-page negative space and localized signal emphasis. Content pages stay light, flat, and shadowless around one principal diagram or evidence structure; glow is only a very subtle current-state cue, with no glass or decorative neon.
- **Theme**: Signal path is the cross-page identity system: cyan lines encode only control, event, or data relationships; at most one primary node is active per slide; chapter pages use a deep field and rising path to reset rhythm.
- **Tone**: Engineered, restrained, explainable, and explicit about evidence levels and system boundaries.

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F7FAFC | Light content pages and readable evidence field |
| Secondary background | #E8EEF7 | Group regions, alternating table rows, and low-priority modules |
| Primary | #101B35 | Deep chapter pages, main titles, and primary nodes |
| Accent | #00C2D7 | Signal paths, current state, and key causal links |
| Secondary accent | #3448A8 | Main series, secondary paths, and structural zones |
| Body text | #101828 | Body copy, labels, and table text |
| Muted text | #475467 | Secondary explanation, sources, and annotations |
| Warning | #D97706 | Boundary reminders and hypotheses requiring validation |
| Risk | #C2415B | High risk, failure boundaries, and public-evidence gaps |
| Success | #15803D | Verified states and passing conditions |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Geometric sans, conclusion-led, compact | Aptos Display | — | Arial, sans-serif |
| Body | Neutral sans for projection and independent reading | Aptos | — | Arial, sans-serif |
| Code | Monospace for contracts, events, and command labels | Cascadia Mono | — | Consolas, monospace |

- **Title stack**: Aptos Display, Arial, sans-serif
- **Body stack**: Aptos, Arial, sans-serif
- **Code stack**: Cascadia Mono, Consolas, monospace
- **Role rationale**: Code repeatedly carries exact identifiers such as `executionMode`, `events.mux`, and `run_id`, separating them from explanatory prose.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Code | 18 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: Read the conclusion title first, then follow one signal path or primary evidence structure from left to right and top to bottom.
- **Composition tendency**: One principal diagram or data structure per page; choose geometry from causality, hierarchy, state, matrix, or action rather than reducing the deck to repeated card walls.
- **Cross-page continuity**: Signal paths, corner codes, one active node, and the footer version line recur; chapter pages switch to deep navy while content pages vary between light and signal surfaces.
- **Spacing posture**: Chapter and conclusion pages breathe; architecture and evidence pages may be dense, but grid, paths, and negative space preserve clear grouping.

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/cpu | Model, runtime, and compute nodes |
| tabler-outline/tool | Tool execution and capability |
| tabler-outline/database | Session, projection, and persistence |
| tabler-outline/shield-lock | Sandbox, governance, and enterprise control |
| tabler-outline/network | Web, transport, and data paths |
| tabler-outline/terminal-2 | CLI, Headless, and ACP |
| tabler-outline/world | Web search, global market, and outbound traffic |
| tabler-outline/plug | Plugin, Provider, and composition |
| tabler-outline/code | SDK, Typert, and contracts |
| tabler-outline/timeline | Event stream, checkpoint, and replay |
| tabler-outline/server | Host, runtime ownership, and deployment |
| tabler-outline/key | Credentials, secrets, and IAM |
| tabler-outline/file-code | Packages, patches, and evidence artifacts |
| tabler-outline/git-branch | Branching, versions, and two-system experiments |
| tabler-outline/chart-bar | Market snapshots and scoring |
| tabler-outline/activity | Runtime state and telemetry |
| tabler-outline/alert-triangle | Risks, boundaries, and unverified claims |
| tabler-outline/arrow-right | One-way control, build, and action paths |
| tabler-outline/check | Verified states |
| tabler-outline/cloud | Cloud and enterprise platforms |
| tabler-outline/lock | Isolation, approval, and access control |
| tabler-outline/settings | Profiles, patches, and policy |
| tabler-outline/x | Not covered, failure, and invalid inference |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P19 | table | comparison_matrix | Compare five Harness anchors, enterprise targets, priority, and public-evidence status |
| P22 | table | comparison_matrix | Compare three China competitive layers, representative products, public-attention metrics, license boundaries, and winning mechanisms |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Layout pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## IX. Content Outline

### Part 1: Opening — why a Harness

#### Slide 01 - DeepSeek Harness: Everything is a Plugin

- **Audience move**: From “another Agent project” to a composable, observable, replaceable control plane.
- **Layout**: Title, two version boundaries, and the three-part lens on the left; Harness control plane on the right with Model, Tool, Session, Sandbox, and UI distributed along one elliptical signal path.
- **Title**: DeepSeek Harness: Everything is a Plugin
- **Core message**: DeepSeek Harness makes the Agent runtime a composable, observable, and replaceable control plane.
- **Content**: From runtime mechanics to enterprise boundaries and global/China competition; Harness v0.1.0-rc.7 · commit 99f6f02; Tianshu ede03b8 · knowledge-to-pptx → ppt-master.
- **Visualization**: One central control-plane node and five plugin nodes form the orbit; the signal path means capabilities compose around the control plane.
- **Fact IDs**: K-001, K-005, K-030
- **Cover impact**: Bind the phrase “Everything is a Plugin” to a control-plane orbit so the slogan becomes an immediate system model.

#### Slide 02 - The hard part is not thinking—it is finishing safely

- **Audience move**: From model reasoning to the Harness responsibility for side effects, evidence, and recovery.
- **Layout**: One causal claim on the left; Model → Harness control plane → Environment on the right, with every execution arrow passing through Harness and evidence returning to Session.
- **Title**: The hard part is not thinking—it is finishing safely
- **Core message**: The model proposes the next move; the Harness turns it into controlled, recorded, and recoverable action.
- **Content**: Model: proposes the next move; Harness: assembles context, Tools, permissions, and policy; Environment: files, processes, networks, and systems create side effects; Session: turns visible inputs and results into recoverable evidence.
- **Visualization**: Context, Policy, Tool, and Session sit inside Harness; Tool causes side effects in Environment, while visible results return to Session.
- **Fact IDs**: K-001, K-002, K-008

#### Slide 03 - Four questions explain DeepSeek Harness

- **Audience move**: From scattered facts to one retellable four-question learning path.
- **Layout**: Runtime, Extensibility, Enterprise, and Market nodes follow an ascending signal path ending at Evidence.
- **Title**: Four questions explain DeepSeek Harness
- **Core message**: Understand the project by asking how it runs, extends, governs, and competes.
- **Content**: 1 · Runtime: how is one Agent turn controlled?; 2 · Extensibility: how does Everything is a Plugin work?; 3 · Enterprise: how far are primitives from a procurement control plane?; 4 · Market: which competitive layer contains each peer?
- **Visualization**: The rising path frames the deck as cumulative evidence rather than a table of contents.
- **Fact IDs**: K-002, K-005, K-018, K-019

### Part 2: Architecture — control, composition, and recoverable state

#### Slide 04 - 01 · Architecture: three flows form the Harness

- **Audience move**: From package counting to understanding control, composition, and event flows.
- **Layout**: Deep chapter field; large `01` and conclusion on the left, three signal paths converging into Harness on the right.
- **Title**: 01 · Architecture: three flows form the Harness
- **Core message**: The architecture is best understood as control, composition, and event flows—not as a package count.
- **Content**: Control flow · Composition flow · Event flow.
- **Visualization**: Agent loop, Profile/Cordis, and Session event stream are the three named paths.
- **Fact IDs**: K-002, K-003, K-008
- **Motion suggestion**: Build the semantic paths in Control → Composition → Event order to preload the chapter's three relationships; this does not activate custom animation execution.

#### Slide 05 - A turn is a barrier-controlled feedback loop

- **Audience move**: From “concurrency means unordered” to the exact exclusive-barrier and ordered-commit boundary.
- **Layout**: Horizontal feedback loop; `executionMode` and exclusive barrier in the center; two Tool-body paths overlap and merge before ordered commit.
- **Title**: A turn is a barrier-controlled feedback loop
- **Core message**: Tool bodies may overlap, but exclusive barriers and ordered commits preserve deterministic model-visible order.
- **Content**: Project context → Policy hooks → Model request; Tool choice → executionMode classification → exclusive barrier; bodies may overlap → post-processing and tool/result commit in model order; Continue / stop / fail; side-effect authority lives in Tool execution, and concurrency does not imply unordered commits.
- **Visualization**: Seven-step loop; only dispatch and Tool bodies occupy the parallel segment, while post-processing and Session commit share one ordered segment.
- **Fact IDs**: K-002, K-008, K-009

#### Slide 06 - Five primitives turn plugin conventions into runtime rules

- **Audience move**: From seeing Cordis as dependency injection to understanding visibility, events, disposal, and ownership.
- **Layout**: Central Plugin runtime with Context, Service, Event, Effect, and Scope around it; a separate warning states that external side effects do not roll back automatically.
- **Title**: Five primitives turn plugin conventions into runtime rules
- **Core message**: Cordis puts capabilities, dependencies, events, and lifecycle in one Context tree.
- **Content**: Context: visibility and lifecycle boundary; Service: stable dependency contract; Event: collaboration and interception; Effect: registration with a disposer; Scope: ownership for one activation; reversible registration ≠ automatic compensation for external side effects.
- **Visualization**: Five primitives collaborate around one runtime; Effect and Scope share a lifecycle relationship, while the external-effect warning sits outside the ring.
- **Fact IDs**: K-003, K-004

#### Slide 07 - Everything is a Plugin unifies lifecycle

- **Audience move**: From valuing package quantity to judging whether capabilities share composition, dependency, event, and disposal semantics.
- **Layout**: Five-layer stack from Host to Interfaces with one cross-cutting mount, event, and dispose axis.
- **Title**: Everything is a Plugin unifies lifecycle
- **Core message**: Plugin value comes from shared composition, dependency, event, and disposal semantics—not from having more packages.
- **Content**: Host and startup surfaces; Agent Preset and Model; Tool, Policy, and Sandbox; Session, persistence, and projection; Web, CLI, ACP, and SDK interfaces; unified composition · explicit dependency · replaceable Provider · disposable Scope.
- **Visualization**: The stack shows breadth, while one lifecycle axis shows the unifying mechanism.
- **Fact IDs**: K-003, K-005, K-010

#### Slide 08 - Presets are shared standing scopes; Sessions are instances

- **Audience move**: From “remount a Preset per Session” to one standing process scope joined through Session parentage.
- **Layout**: Host plane above one standing Agent Preset scope; two Session Agent scopes parent to it and record separate selection events.
- **Title**: Presets are shared standing scopes; Sessions are instances
- **Core message**: A Preset is a shared standing scope; the Session is the runtime instance that joins it.
- **Content**: Host plane: Web, persistence, credentials, sandbox, providers; Agent Preset: one standing mount per process; Session Agent scope: parent → selected Preset; switching: agent-preset/selected event, not a rewritten creation header; mutable state in a shared Preset must be keyed by Session or another explicit owner.
- **Visualization**: The single Preset node is visibly shared; each Session retains its own selection event as recoverable fact.
- **Fact IDs**: K-005, K-006

#### Slide 09 - Four ordered layers—not one file—define the runtime

- **Audience move**: From inspecting only final JSON to tracing provenance and override order.
- **Layout**: Four translucent configuration sheets rise from lower left to upper right; `--patch` uses a signal outline, and Effective runtime is the only output.
- **Title**: Four ordered layers—not one file—define the runtime
- **Core message**: Effective capability comes from ordered overlays, with later patches closer to the current user and run.
- **Content**: 1 · Bundles: reusable defaults; 2 · Profile patch: product or role selection; 3 · Home patch: durable user override; 4 · --patch: temporary run override; later layers override earlier ones, and order is behavior.
- **Visualization**: Each sheet keeps a source label and override arrow so the final runtime remains explainable.
- **Fact IDs**: K-007

#### Slide 10 - Events are facts; cache is versioned unit state

- **Audience move**: From treating cache as a persisted UI view to understanding versioned checkpoints plus tail replay.
- **Layout**: Append-only events on top; checkpoint `(key, ver, seq, val)` in the middle; replay branches into Conversation, Tasks, and Usage below.
- **Title**: Events are facts; cache is versioned unit state
- **Core message**: Events are facts; the cache stores replayable unit state, not a persisted UI view.
- **Content**: Events: user, assistant, Tool, approval, error; Request metadata: request/header · request/context; Checkpoint row: (key, ver, seq, val); View: restore or re-view unit state + replay tail; invariant · model-visible means logged.
- **Visualization**: Time runs left to right; the checkpoint marks processed `seq`, and tail events feed three independent projections.
- **Fact IDs**: K-008, K-009
- **Motion suggestion**: Preserve the same event-stream mental map across its visible states and move focus from facts to checkpoint to replay.

#### Slide 11 - Capability seams isolate Agents from implementations

- **Audience move**: From assuming one Service means one implementation to understanding Definition, Provider registry, Consumer, and Policy direction.
- **Layout**: Definition → Provider registry → Consumer → Agent; Policy wrappers intercept the Consumer from above; subprocess/ripgrep forms a separate lower seam.
- **Title**: Capability seams isolate Agents from implementations
- **Core message**: A stable seam separates capability contract, implementations, consumers, and composable policy.
- **Content**: Definition: stable types, methods, and events; Provider: one selected implementation or a named multi-provider registry; Consumer: Tool, Agent loop, UI, or another Service; boundary exception: tool-fs-search uses subprocess/ripgrep, not ctx.fs; Policy: approval · retry · timeout · observation.
- **Visualization**: The main chain expresses dependency inversion, vertical gates express cross-cutting policy, and the dashed lower path exposes the boundary exception.
- **Fact IDs**: K-005, K-010

### Part 3: Extension — multiple interfaces and dynamic Plugins

#### Slide 12 - 02 · Extension: one Core, multiple interfaces

- **Audience move**: From treating each entry point as a separate product to recognizing shared Core plus distinct adapters and lifecycle.
- **Layout**: Deep chapter field; one Core radiates to five interface nodes, with a plugin lifecycle signal path below.
- **Title**: 02 · Extension: one Core, multiple interfaces
- **Core message**: One core supports multiple adapters and an inspectable plugin release workflow.
- **Content**: CLI · Web · Headless · ACP · SDK · Dynamic Plugin.
- **Visualization**: The radial structure proves core reuse; the lower path previews inspect, define, run, diagnose, and repair.
- **Fact IDs**: K-011, K-014

#### Slide 13 - Five entry points share Core—but not transport ownership

- **Audience move**: From “SDK and Web are only different UIs” to process, connection, recovery, and runtime-ownership boundaries.
- **Layout**: Agent/Session/Tools core in the center; CLI, Web, Headless/ACP, TypeScript SDK, and Python SDK around it; Web expands into one POST uplink and two WS downlinks.
- **Title**: Five entry points share Core—but not transport ownership
- **Core message**: Interfaces share Agent and Session semantics, but Web and SDK process boundaries differ.
- **Content**: CLI: interactive product entry; Web: HTTP POST up + events.mux / events.host WebSockets down; Headless / ACP: automation and stdio JSON-RPC; TypeScript SDK: caller supplies the runtime; Python SDK: bundled subprocess by default.
- **Visualization**: Every adapter connects to one core, while Web and SDK branches expose their distinct transport details.
- **Fact IDs**: K-011, K-012

#### Slide 14 - Typert defines Host/Client contracts once

- **Audience move**: From assuming a shared tsconfig is enough to understanding a Host-built cross-process contract.
- **Layout**: Host source → Typert → metadata → registry/gateway → Client; Typert expands into Analyze, Model, Emit; one-way build order below.
- **Title**: Typert defines Host/Client contracts once
- **Core message**: Typert extracts cross-process structure during the Host build and exposes one generated contract to the Client.
- **Content**: Host TypeScript source; Analyzer → compiler-independent model → emitter; Remote metadata · reflection · Zod schemas; Loader / registry / gateway; Client compiler face; Build order: Host contracts → Client typecheck.
- **Visualization**: The contract pipeline remains on one axis; auth, TLS, and authorization are explicitly marked outside schema-generation scope.
- **Fact IDs**: K-013

#### Slide 15 - Run ok does not guarantee the next Client render

- **Audience move**: From treating activation success as complete success to separating page wait, approval, Run, and later render.
- **Layout**: Inspect → Define → Waiting for page → Approval → Starting → Run result; Run ok branches to Render ok and Render failed.
- **Title**: Run ok does not guarantee the next Client render
- **Core message**: A dynamic Plugin is a page-mediated release system; activation and later rendering have separate success boundaries.
- **Content**: Inspect: list → minimal query; Define: immutable Plugin / Package; Client half: wait for a matching page; Run: approval → starting → ok / failed; After settle: render diagnostics may still fail; Repair = new Package · Rollback = explicit currentPackageId.
- **Visualization**: The state machine preserves two success boundaries; repair and rollback attach to Package/version state rather than the Run node.
- **Fact IDs**: K-014, K-015

### Part 4: Enterprise — safety primitives are not a control plane

#### Slide 16 - 03 · Enterprise: Local is not Governed

- **Audience move**: From using “open source/self-hosted” as governance evidence to requiring three independent proof layers.
- **Layout**: Deep chapter field; Local runtime, Local data paths, and Enterprise governance are successive gates, and only the last opens to Production.
- **Title**: 03 · Enterprise: Local is not Governed
- **Core message**: Security primitives reduce local risk; an enterprise control plane determines scalable procurement.
- **Content**: Isolation primitives ≠ Enterprise control plane.
- **Visualization**: Three gates increase in proof strength, preventing a security-feature list from becoming a maturity claim.
- **Fact IDs**: K-016, K-017, K-018

#### Slide 17 - Self-hosted answers only one of three questions

- **Audience move**: From deployment-location reasoning to separate runtime, data-path, and control-evidence validation.
- **Layout**: Runtime local, Data path, and Control evidence form progressive containers with Primitives, Configurable, and Public evidence gap statuses.
- **Title**: Self-hosted answers only one of three questions
- **Core message**: Private deployment must independently prove where code runs, where data flows, and who governs access and lifecycle.
- **Content**: Layer 1 · Runtime local: where do code and processes run?; Layer 2 · Data path: where do models, search, Plugins, and telemetry go?; Layer 3 · Control evidence: who can access, approve, audit, upgrade, and own outcomes?; Harness: Layer 1 has primitives · Layer 2 is configurable · Layer 3 lacks public evidence.
- **Visualization**: Each layer combines the question, current evidence status, and direction of improvement; the public gap uses both text and a risk border.
- **Fact IDs**: K-016, K-017, K-018, K-031

#### Slide 18 - Sandbox covers file effects and same-world only

- **Audience move**: From “there is a sandbox, therefore it is secure” to precise covered and not-covered boundaries.
- **Layout**: Agent at the center; Sandbox, Credentials, Telemetry, Outbound, Persistence, and Web around it, each with covered and not-covered labels.
- **Title**: Sandbox covers file effects and same-world only
- **Core message**: A file sandbox cannot establish network, process, credential, identity, or audit guarantees.
- **Content**: Sandbox: file effects + same-world; Windows leaves read/network/process visible; Credentials: 0700/0600 does not block same-UID Tools; Telemetry: off by default, when on can include prompts, Tools, files, commands, and cwd; Outbound: Web search on by default, fetch and Session FTS off; Persistence / Web: JSONL is not auto-deleted, Host/Origin fence is not auth; Fail-closed ≠ full isolation · Append-only ≠ tamper-evident audit.
- **Visualization**: Six boundaries are arranged by actual data flow rather than as a checklist; text, icon, and state symbols jointly encode scope.
- **Fact IDs**: K-017, K-031, K-032

#### Slide 19 - The enterprise gap is evidence and accountability

- **Audience move**: From a vague enterprise-readiness concern to a verifiable identity, execution, data, audit, and lifecycle agenda.
- **Layout**: Full-width comparison matrix with Identity/tenancy, Execution, Secrets/data, Audit, and Lifecycle rows; Priority and Evidence status at the right.
- **Title**: The enterprise gap is evidence and accountability
- **Core message**: Enterprise adoption depends on verified identity, isolation, audit, and lifecycle evidence—not on plugin count.
- **Content**: Identity / tenancy: Host fence → SSO, RBAC, workspace isolation; Execution: file sandbox → network/process/remote isolation; Secrets / data: local file → Vault/KMS, DLP, residency evidence; Audit: Session log → redaction, retention, tamper evidence; Lifecycle: developer preview → LTS, SBOM, CVE, SLA, support; Priority: High; Evidence status: Public gap.
- **Visualization**: `enterprise-gap-matrix` is a four-column native text table; Native-ready: enterprise-gap-matrix=yes.
- **Fact IDs**: K-017, K-018

### Part 5: Market — three global and China competitive layers

#### Slide 20 - 04 · Market: Agent is not one market

- **Audience move**: From one leaderboard to buyer, job-to-be-done, and competitive layer.
- **Layout**: Deep chapter field; a three-level staircase names Runtime, Developer Product, and Enterprise Platform with the corresponding buyer.
- **Title**: 04 · Market: Agent is not one market
- **Core message**: Identify the competitive layer before comparing products, buyers, and business models.
- **Content**: Runtime / framework · Developer product / control surface · Enterprise platform.
- **Visualization**: The staircase labels Builder, Developer, and Enterprise buyer before any brands appear.
- **Fact IDs**: K-019, K-027

#### Slide 21 - Three layers compete for architecture, habits, and budget

- **Audience move**: From direct-substitute thinking to understanding three value systems, buyers, and switching costs.
- **Layout**: Three-layer market staircase expands into buyer, value, representatives, and switching cost; inter-layer arrows read enables, habits, governance.
- **Title**: Three layers compete for architecture, habits, and budget
- **Core message**: Runtime wins architecture, developer products win habits, and enterprise platforms win governance budgets.
- **Content**: Runtime/framework: Harness, AgentScope, LangGraph, OpenAI SDK, ADK, Agent Framework; Developer/control surface: Claude Code, Codex, Copilot, OpenHands, Qwen, Kimi, Trae; Enterprise platform: Dify, Coze, Model Studio, Tencent ADP; Switching cost: Capability contract → Workflow habit → IAM/VPC/SLA.
- **Visualization**: Each layer uses different structural weight rather than a logo wall; OpenHands is explicitly placed in the developer/control-surface layer.
- **Fact IDs**: K-019, K-021, K-022, K-024, K-025, K-026, K-033

#### Slide 22 - China is three competitions—not one leaderboard

- **Audience move**: From a stars leaderboard to same-layer comparison, license boundaries, and different winning mechanisms.
- **Layout**: Comparison matrix for Layer, China peers, Public attention, and Winning mechanism; below it, Attention → Experimentation → Adoption → Revenue uses broken arrows.
- **Title**: China is three competitions—not one leaderboard
- **Core message**: AgentScope competes for runtime, Qwen Code for developer entry, and cloud or low-code platforms for enterprise budget.
- **Content**: Runtime peer: AgentScope · 29,019 stars / 3,369 forks; Developer entry: Qwen Code · 27,144 / 2,877, then Kimi and Trae; Enterprise budget: Dify · 152,784 / 24,135, plus Coze, Model Studio, ADP; Harness: 157,324 / 16,338, differentiated by an open plugin runtime; License boundary: Dify has added conditions and some Coze features are commercial-only; 2026-08-18 snapshot · Attention ≠ Adoption ≠ Revenue.
- **Visualization**: `china-competition-matrix` is a native same-layer comparison table; Native-ready: china-competition-matrix=yes. Three `x` marks break unsupported inference jumps.
- **Fact IDs**: K-020, K-021, K-022, K-023, K-024, K-025, K-027

### Part 6: Action — validate claims with evidence

#### Slide 23 - Freeze grader, run ID, and evidence bundle

- **Audience move**: From one successful demo to a reproducible, auditable, same-layer comparison protocol.
- **Layout**: Choose and Freeze branch into System A and System B; a unique run_id gate appears before execution; paths converge on Evidence bundle, Shared rubric, Explain, and Repeat.
- **Title**: Freeze grader, run ID, and evidence bundle
- **Core message**: Freeze the evaluator, use a unique run ID, and retain the full evidence bundle.
- **Content**: Choose: same-layer peer + deterministic task; Freeze: commit, model, Tools, network, budget, grader; Run: use a new run_id whenever the patch changes; Capture: summary + report.json + test_output.txt + run_instance.log + eval.sh + patch.diff; Score: outcome, recovery, safety, effort, efficiency; one success = case study, while repeated tasks approach a benchmark.
- **Visualization**: The two systems share frozen inputs but run independently; six evidence artifacts are visible before shared scoring and mechanism explanation.
- **Fact IDs**: K-028, K-029

#### Slide 24 - Turn architectural attention into governed adoption

- **Audience move**: From “worth watching” to an executable 30/60/90-day evidence plan and explicit decision gate.
- **Layout**: Architecture, Governance, and Evidence support the conclusion on the left; a 30/60/90-day staircase reaches a Decision gate on the right; version and evidence boundaries remain in the footer.
- **Title**: Turn architectural attention into governed adoption
- **Core message**: Harness is worth studying for control-plane design; adoption depends on enterprise evidence and real-task outcomes.
- **Content**: 30 days: reproduce Profiles, Sessions, and capability seams; 60 days: map security data flows and enterprise evidence gaps; 90 days: run controlled comparisons with AgentScope and Qwen Code; Decision gate: embed, extend, partner, or wait based on evidence; Architecture attention → Reproducible evidence → Governed adoption.
- **Visualization**: Three supports and the action staircase form one loop; the Decision gate opens only after all evidence stages.
- **Fact IDs**: K-001, K-010, K-018, K-019, K-028
- **Data class: scenario**: The 30/60/90-day milestones are proposed evaluation targets, not external facts.
- **Closing impact**: Bind the conclusion “architectural attention must pass through reproducible evidence before governed adoption” and close on the Decision gate rather than a thank-you page.

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: Use the page-specific speaker_notes in deck-design.json as semantic authority; preserve technical boundaries, fixed-version claims, and citations. Do not read the slide aloud—add transitions, misconception corrections, and decision conditions.
- **Total duration**: about 32 minutes
- **Notes style**: Patient, explanatory, and conclusion-led; define before using, explain mechanisms on architecture pages, and state evidence levels on enterprise and market pages.
- **Presentation purpose**: instruct, analyze, support decision
