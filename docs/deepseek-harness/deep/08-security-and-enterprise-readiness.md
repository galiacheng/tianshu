# Security and enterprise readiness

## Why it matters

An Agent runtime can read source, run processes, call networks, and persist conversations. Local execution, data locality, and enterprise procurement are therefore three different claims that need separate evidence.

## Concrete anchor

Install DeepSeek Harness on a company laptop and connect it to a private OpenAI-compatible gateway. The process is local, but model requests, default search, optional telemetry, plugins, and credentials still form separate data and control paths.

## Provisional mental model

Evaluate private deployment in three layers:

1. **Local runtime:** code and processes execute on a workstation or in a private network.
2. **Local model and data paths:** prompts, code, Tool results, search, and telemetry stay within approved endpoints.
3. **Enterprise control plane:** identity, tenancy, policy, audit, lifecycle, support, and procurement are centrally governed.

DeepSeek Harness `v0.1.0-rc.7` has useful local safety primitives for layer 1 and configurable provider paths for layer 2. The reviewed public sources do not establish the enterprise controls and commercial guarantees required for layer 3; that is an evidence gap, not proof that a deployment cannot add them.

## Core concepts and mechanism

| Dimension | Harness anchor | Enterprise target | Gap at `v0.1.0-rc.7` |
| --- | --- | --- | --- |
| Model and data path | Private-compatible gateway; OTel disabled by default; default model and outbound Web search use DeepSeek paths | Default-deny egress, endpoint allowlist, residency evidence | High |
| Execution isolation | Permission presets, approval, fail-closed sandbox scoped to file effects and same-world confinement | Container/VM boundary, read, network, process, and central policy enforcement | High |
| Identity and tenancy | Loopback, Host, Origin, and cross-site request fences that explicitly are not authentication | SSO, RBAC/ABAC, workspace and tenant isolation | Public evidence gap |
| Secret management | Managed file under `0700`/`0600`; same-UID Tools can still read it | Vault/KMS, rotation, short-lived identity, Agent-process separation | High |
| Logs and telemetry | Append-only Session events; raw export; optional OTel; no automatic JSONL deletion | Tamper evidence, redaction, retention/deletion, audit export | High |
| Product lifecycle | MIT-licensed developer preview with community support and breaking-change warning | LTS, signed artifacts, SBOM, CVE response, HA and rollback | Public evidence gap |
| Procurement | Free self-hosting; no reviewed first-party SKU or SLA evidence | SKU, SLA, invoicing, support and implementation channel | Public evidence gap |

1. A model with file, shell, network, or business Tools can turn a mistaken instruction into a real side effect.
2. Local sandbox and approval reduce risk for a single developer, but they do not prove that every read, outbound request, credential, and child process is isolated.
3. Enterprise use adds multiple identities, tenants, sensitive repositories, internal systems, long-lived Sessions, and compliance obligations.
4. The threat model therefore expands from “can this command run?” to “who authorized it, which data crossed which boundary, which policy applied, and can the evidence be audited?”
5. Central IAM, network controls, secret brokers, DLP, retention, deletion, and incident response become control-plane requirements.
6. Procurement adds release stability, vulnerability response, support ownership, deployment architecture, service levels, and contractual responsibility.

Several concrete boundaries prevent overclaiming:

- The sandbox contract is explicitly limited to **file effects** and **same-world confinement**. Linux selects bubblewrap or Landlock, macOS depends on deprecated `sandbox-exec`, and unusable runners fail closed; none of this contract expresses network, process, syscall, device, or credential isolation.
- The Windows ACL backend reports `partial` enforcement and explicitly leaves reads, network, and process visibility outside its boundary.
- Local credential permissions protect against other operating-system users but not same-UID Tools. Harness does not expose the managed path to the model or inject managed secrets into the process environment, yet same-user processes can still read the file.
- OTel is disabled by default. If enabled, it can export prompts, messages, Tool arguments and results, command output, file contents, system prompts, feedback, and `cwd`; provider credentials are structurally excluded, but the remaining data still requires redaction and destination governance.
- DeepSeek model requests send stable per-home anonymous user identifiers and optional Session identifiers to the configured model or gateway endpoint. Separately, outbound DeepSeek Web search is enabled by default while fetch and local Session full-text search are disabled by default.
- Append-only Session logs support replay and recovery, but raw JSONL files accumulate until removed externally and are not automatically tamper-proof, centrally retained, or WORM-compliant audit records.
- The bare Web server has no TLS, authentication, or origin policy. The browser trust fence lives in the Client connection layer and restricts Host, Origin, and cross-site requests; it explicitly does not become identity authentication.

> [!CAUTION]
> “Self-hosted” proves a deployment location, not data sovereignty or enterprise compliance. Every model, search, plugin, telemetry, update, and support path needs an explicit data-flow decision.

## Refined mental model

The three-layer model separates useful local safety primitives from stronger organizational claims. Its limit is that a company can add external controls or weaken built-in defaults, while missing public evidence does not prove a capability is impossible. A defensible assessment is deployment-specific: **enterprise readiness equals bounded technical isolation plus a governance control plane plus operational and procurement guarantees**.

## Optional hands-on

<details>
<summary>Try it yourself</summary>

Create a data-flow inventory for one coding Session: user prompt, repository reads, model request, search request, Tool execution, telemetry export, Session persistence, and credentials. For each edge, record destination, identity, encryption, retention, and denial policy. Do not accept “runs locally” as an answer for an outbound edge.

</details>

## Checkpoint questions

1. If Harness is installed on an enterprise laptop, does source code automatically stay inside the enterprise?

<details>
<summary>Show answer 1</summary>

No. Model APIs, search providers, plugins, update paths, and enabled telemetry can create external data paths. Each must be configured and governed.

</details>

2. Does fail-closed sandboxing prove complete Agent isolation?

<details>
<summary>Show answer 2</summary>

No. It prevents silent unprotected execution when a required sandbox fails, but it does not by itself eliminate read, network, same-user credential, or platform-specific boundary gaps.

</details>

3. What is the earliest likely blocker for a large-enterprise purchase?

<details>
<summary>Show answer 3</summary>

The reviewed public evidence does not establish the control and assurance layer: SSO/RBAC, tenant isolation, secret and network governance, compliance audit, stable lifecycle, SLA, and accountable support. A buyer must verify those requirements in the actual deployment and commercial arrangement.

</details>

## Primary sources

- [Architecture and Session log](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/docs/architecture.md)
- [Base profile defaults](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/bundle/base/cordis.patch.yml)
- [Multi-provider LLM gateway](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/llm/llm-pi-ai/README.md)
- [DeepSeek native request identifiers](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/llm/llm-deepseek/README.md)
- [Anonymous identifier boundary](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/identity/anonymous-user-id/README.md)
- [Sandbox contract](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/sandbox/sandbox/README.md)
- [Local sandbox boundaries](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/sandbox/sandbox-local/README.md)
- [Windows ACL sandbox boundaries](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/sandbox/sandbox-windows-acl/README.md)
- [Local credential boundary](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/credentials/credentials-local/README.md)
- [Session telemetry data surface](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/session/session-telemetry-otel/README.md)
- [Default outbound Web search](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/web/web-search-deepseek/README.md)
- [Browser trust fence](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/client/connection/README.md)
- [Bare Web server boundary](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/host/webserver/README.md)
- [JSONL persistence and retention limit](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/packages/session/session-persistence-jsonl/README.md)
- [Developer-preview lifecycle and support](https://github.com/deepseek-ai/deepseek-harness/blob/99f6f02fecdb7dff40c3fbc9470f5907c29f74ca/README.md)
- [China: Interim Measures for Generative AI Services](https://www.cac.gov.cn/2023-07/13/c_1690898327029107.htm), retrieved 2026-08-18.
- [China: Personal Information Protection Law](http://www.npc.gov.cn/npc/c2/c30834/202108/t20210820_313088.html), retrieved 2026-08-18.

## Navigation

- Prerequisite: [Plugin development workflow](07-plugin-development-workflow.md)
- [Deep track](README.md)
- Next: [Global and China competition](09-global-and-china-competition.md)
- [Topic root](../README.md)
