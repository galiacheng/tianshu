# 01_DeepSeek Harness: Everything is a Plugin

This twenty-four-page tutorial treats DeepSeek Harness as an Agent control plane rather than another chat framework. Its central value is the ability to compose, observe, and replace Models, Tools, Sessions, Sandboxes, and Interfaces around one governed runtime. Technical claims are frozen to Harness v0.1.0-rc.7 at commit 99f6f02, while the material was generated with the knowledge-to-pptx and ppt-master Skills at Tianshu ede03b8. We will build a complete view through architecture, enterprise boundaries, and global and China market lenses.

---

# 02_The hard part is not thinking—it is finishing safely

A model can propose the next step, but it does not inherently own execution in files, processes, networks, or business systems. Harness routes a proposal through Context, Policy, Tool, and Session so real-world action can be constrained, recorded, and recovered after failure. The key distinction is that thinking is not acting, because side effects occur outside model text. When every execution path crosses the control plane, a visible result in the world can become durable, reviewable evidence.

---

# 03_Four questions explain DeepSeek Harness

Four questions provide a practical path through the project. How is one Turn controlled, how do Plugins become runtime capabilities, how far are the primitives from enterprise governance, and which market layer contains each meaningful peer? A fifth evidence thread turns every architectural answer into a testable adoption claim. That prevents the study from ending with an attractive diagram but no decision method.

---

# 04_Architecture: three flows form DeepSeek Harness

Do not begin by counting packages; begin with three flows. Control flow explains how one Turn moves from context to an execution result, composition flow explains how Profile and Cordis make capabilities visible in Context, and event flow explains how Session state can be recorded, recovered, and projected. All three converge on one Harness control plane, so execution, composition, and recoverability are not isolated subsystems. This map gives every implementation detail that follows a clear architectural home.

---

# 05_A turn is a barrier-controlled feedback loop

A Turn begins with project context and policy hooks, proceeds through the model request and tool choice, and then uses executionMode to decide how calls may run. An exclusive call creates a barrier, and later calls are reclassified before they start; within an allowed region, two Tool bodies may overlap without changing commit order. Post-processing and tool results are still written to the Session in deterministic model-visible order before the loop chooses Continue, Stop, or Fail. This guarantee governs what the model sees, while authority over file, process, and network side effects remains inside Tool execution.

---

# 06_Five primitives turn plugins into runtime rules

Cordis uses five primitives to turn plugin conventions into runtime behavior. Context establishes visibility and boundaries, Service provides a stable dependency contract, Event supports collaboration and interception, Effect makes registration disposable, and Scope decides activation, ownership, and release. Together they form one Context tree whose lifecycle is managed through the Effect and Scope relationship. Reversible registration is not automatic compensation, so files already written, network requests already sent, and processes already launched still need explicit recovery logic.

---

# 07_Everything is a Plugin unifies lifecycle

“Everything is a Plugin” unifies lifecycle rather than directory layout. The stack runs from Host, startup configuration, providers, and external systems through Agent Presets and Models, Tools, Policies, and Sandboxes, then Sessions, Persistence, and Projections, and finally Web, CLI, ACP, and SDK adapters. Every layer may participate as a Provider, Consumer, or policy, but each follows the same Context and Scope model from mount through event handling to dispose. Stable capability seams and dependency direction are what turn many packages into a replaceable system instead of an accidental collection of modules.

---

# 08_Presets are shared; Sessions are instances

The Host plane owns process-level capabilities such as Web, persistence, credentials, Sandboxes, and providers. An Agent Preset normally has one standing mount per process and can be inherited by multiple Session Agent scopes rather than being remounted for every Session. Session A and Session B own their own events and runtime state while pointing to the same shared Preset node. The resulting engineering rule is that mutable state inside a shared Preset must be partitioned by Session or another explicit owner.

---

# 09_Four ordered layers define the runtime

The effective runtime comes from four ordered overlays. Bundles provide reusable default Models, Tools, and policies; the Profile patch selects a product or role workflow; the Home patch preserves durable user preferences; and the command-line --patch is closest to the current user and task. Later layers override earlier layers, which makes order part of runtime behavior. Debugging therefore requires the provenance of all four layers, not only the final JSON, or no one can explain why a Tool exists or a policy was replaced.

---

# 10_Events are facts; cache is versioned unit state

The Session event stream records ordered facts such as request headers, request context, user and assistant messages, tool calls, approvals, and errors. Cache stores a projection checkpoint with a key, version, sequence, and value; it is not a second fact ledger. A cold read restores that versioned unit state and replays the tail after the checkpoint to rebuild independent Conversation, Tasks, or Usage views. The critical invariant is that anything visible to the model must be logged, allowing projections to be regenerated even when a cache is lost.

---

# 11_Capability seams decouple Agents from Providers

A capability seam defines stable types, methods, and events before a provider registry binds one implementation or a named set of implementations. Tools, the Agent loop, UI, and Services consume the contract, while approval, retry, timeout, and observation policies compose at the seam. The Agent therefore depends on a capability rather than a specific Provider, and the three-role model describes dependency direction rather than provider count. Boundary exceptions still matter: tool-fs-search launches packaged ripgrep through a subprocess, so replacing ctx.fs does not automatically replace search semantics.

---

# 12_Extension: one Core, many interfaces

The key extension principle is that an Adapter should not copy Agent and Session semantics. CLI, Web, the TypeScript and Python SDKs, Headless, ACP, and Dynamic Plugins all surround one Agent, Session, and Tools Core while retaining explicit transport and runtime ownership. Dynamic Plugins still pass through an inspectable lifecycle from inspect and define to run, diagnose, and repair. The next distinction is crucial: sharing Core semantics does not mean sharing a process boundary.

---

# 13_Five interfaces share Core, not process ownership

CLI is a local interactive entry point, while Headless and ACP support automation over stdio JSON-RPC with the caller managing connection and lifecycle. Web sends commands through HTTP POST and delivers events over two downlink-only WebSockets, events.mux and events.host. The TypeScript and Python SDKs are both out of process, but the TypeScript caller normally supplies the runtime while Python can launch a bundled process by default. These interfaces share Agent, Session, and Tools semantics, yet their transport, deployment, failure, and security boundaries must be evaluated separately.

---

# 14_Typert defines Host/Client contracts once

Typert begins with TypeScript source on the Host and passes it through Analyze, Model, and Emit to create a compiler-independent structural model. That model produces remote metadata, reflection information, and Zod schemas, which a registry or gateway publishes through loaders, routing, and remote faces for the Client compiler face to consume. The build order must therefore complete Host contracts before Client type checking. This pipeline keeps cross-process structure consistent, but authentication, TLS, and authorization remain outside schema generation.

---

# 15_Run ok does not guarantee the next Client render

Dynamic Plugin release begins with Inspect and a minimal query against the live contract, followed by Define of an immutable Plugin and Package. A Client half may then wait for a matching page and an explicit approval before Starting, a Run result, and the later render settle. A Run result of ok proves activation only; Client rendering can still fail independently, so diagnostics must cover both phases. Repair creates a new Package rather than mutating a settled version, and rollback explicitly selects a known currentPackageId.

---

# 16_03 · Enterprise: Local is not Governed

Enterprise readiness is a sequence of gates, not a property inherited from open source. A local runtime must first prove that its data paths are local, then add governed identity, policy, audit, and ownership before production is justified. The diagram deliberately separates those stages because self-hosting answers where code runs, not who may act, what leaves the boundary, or how a decision is reconstructed.

---

# 17_Self-hosted answers only one of three questions

The first enterprise question asks where the runtime executes. The second asks where prompts, outputs, credentials, events, and artifacts actually travel, including remote models, tools, and clients. The third asks whether controls and evidence identify the actor, enforce policy, preserve an auditable record, and support review. A self-hosted process can answer the first question while leaving the other two open.

---

# 18_Sandbox covers file effects and same-world only

The repository Sandbox contributes meaningful controls for file effects and same-world execution, but it is not a universal security boundary. Host API access, Plugin loading, remote transport, credential residency, observability data, and rollback each cross a different boundary and therefore need their own enforcement and review. The right enterprise question is not whether a Sandbox exists, but which flows it covers and which controls remain external to it.

---

# 19_The enterprise gap is evidence and accountability

The matrix compares current public evidence with the proof an enterprise adoption decision still requires. Identity needs tenant mapping and runtime authorization; execution needs policy enforcement and approval records; data needs transport, redaction, retention, and residency controls; audit needs durable export and reconciliation; lifecycle needs signed artifacts, canaries, rollback, and operational ownership. These are evidence and accountability gaps, not proof that the architecture is unusable, and they define the control shell that a serious pilot must add.

---

# 20_04 · Market: Agent is not one market

Agent products compete on different stairs. A runtime or framework is bought by builders for execution semantics and extensibility, a developer product is won through workflow habit and task fit, and an enterprise platform is bought through governance, procurement, and support. Harness can move upward across these layers, but each step changes the buyer, the substitute, and the proof required.

---

# 21_Three layers compete for architecture, habits, and budget

At the runtime layer, Harness and AgentScope compete for architecture through plugin seams, lifecycle semantics, and control of execution. At the developer-entry layer, Qwen Code, Kimi, Trae, and similar products compete for repeated workflow habits. At the enterprise-platform layer, Dify, Coze, Model Studio, and Tencent ADP compete for governance budget and carry high switching costs around identity, networks, service levels, and procurement. A useful competitive comparison therefore stays within one layer at a time.

---

# 22_China is three competitions—not one leaderboard

The China snapshot separates runtime, developer entry, and enterprise budget rather than collapsing them into one ranking. Public stars and forks anchor attention as of August 18, 2026, but attention does not prove experimentation, adoption, or revenue, which is why the inference chain is deliberately broken. License boundaries also matter: AgentScope is Apache 2.0, while Dify adds conditions and some Coze capabilities are commercial-only. The decision question is the winning mechanism within each layer, not which repository has the largest headline number.

---

# 23_A credible trial makes every comparison replayable

A credible trial freezes one hypothesis, release, model set, task, and success threshold before System A and System B run. Both paths receive a unique run identifier that binds the configuration snapshot, events, logs, artifacts, outcomes, and costs into one evidence bundle. The same rubric then judges success, cost, and failure without post-hoc metric changes. If the team cannot explain the delta and repeat the run, the result remains an anecdote rather than decision-grade evidence.

---

# 24_Turn 90 days into an adoption decision—not a demo

Architecture, governance, and evidence remain the three supports throughout the roadmap. By day thirty, the team freezes the paired experiment, owners, run identity, and shared rubric; by day sixty, it adds policy, identity, secret, audit, replay, and failure controls. By day ninety, it names a production owner, approved providers and tools, service objectives, rollback paths, and adoption and finance metrics. The gate is explicit: proceed to governed adoption only when the system remains explainable and repeatable across all three supports; otherwise hold and close the gaps.
