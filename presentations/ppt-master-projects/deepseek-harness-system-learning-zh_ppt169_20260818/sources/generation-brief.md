# Generation brief

## Output and locked artifacts

- Final PowerPoint: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.pptx`
- Template: none
- Artifact directory: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.artifacts`
- Knowledge map: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.artifacts\knowledge-map.json`
- Deck design: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.artifacts\deck-design.json`
- Style guide: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.artifacts\style-guide.json`
- Semantic review: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.artifacts\design-validation.json`
- Deterministic validation: `C:\Users\haiche\.copilot\repos\copilot-worktrees\tianshu\haiche-microsoft-ubiquitous-meme\presentations\deepseek-harness-system-learning-zh.artifacts\validation-result.json`
- Locked `deck_id`: `deepseek-harness-system-learning-zh`
- Locked `design_version`: `2`
- Locked `style_version`: `1`
- Aspect ratio: `16:9`
- Language: `zh-CN` (中文)
- Expected slide count: `24`

Implement the approved artifacts exactly. Do not redesign, reorder, substitute layouts, change global tokens, add unsupported facts, or remove source references. If implementation constraints make a slide impossible, return to the design artifacts, increment the relevant version, rerun validation, and regenerate.

## Slide implementation manifest

| Order | ID | Title | Layout | Variant | Visual |
| ---: | --- | --- | --- | --- | --- |
| 1 | S-01 | DeepSeek Harness：Everything is a Plugin | `title-orbit` | `dark` | shape-composition |
| 2 | S-02 | Agent 的难点不在“会想”，而在“安全地做完” | `context-gap` | `light` | diagram |
| 3 | S-03 | 用四个问题读懂 DeepSeek Harness | `roadmap-four` | `signal` | diagram |
| 4 | S-04 | 01 · 架构：三条流构成 Harness | `section-signal` | `dark` | shape-composition |
| 5 | S-05 | 一次 Turn 不是一次请求，而是带屏障的控制闭环 | `loop-flow` | `light` | diagram |
| 6 | S-06 | 五个 Primitive 让插件化从“约定”变成“运行时” | `primitive-ring` | `signal` | diagram |
| 7 | S-07 | “Everything is a Plugin”统一的是生命周期 | `ontology-stack` | `light` | diagram |
| 8 | S-08 | Preset 是共享 standing scope，Session 才是运行实例 | `dual-plane` | `signal` | diagram |
| 9 | S-09 | 最终能力来自四层叠加，而不是单个配置文件 | `layer-stack` | `light` | diagram |
| 10 | S-10 | Event 是事实，Cache 只保存可重放的 Unit State | `event-stream` | `signal` | diagram |
| 11 | S-11 | Capability Seam 把 Agent 与具体实现隔离 | `seam-flow` | `light` | diagram |
| 12 | S-12 | 02 · 扩展：一个 Core，多种 Interface | `section-signal` | `dark` | shape-composition |
| 13 | S-13 | 五个入口共享 Core，但 Transport 与 Runtime Ownership 不同 | `interface-hub` | `light` | diagram |
| 14 | S-14 | Typert 让 Host / Client 契约只定义一次 | `contract-pipeline` | `signal` | diagram |
| 15 | S-15 | Run ok 不代表后续 Client Render 一定成功 | `lifecycle-state` | `light` | diagram |
| 16 | S-16 | 03 · 企业：Local 不等于 Governed | `section-signal` | `dark` | shape-composition |
| 17 | S-17 | Self-hosted 只回答了三分之一的问题 | `three-layer` | `signal` | diagram |
| 18 | S-18 | Sandbox 只约束 File Effects 与 Same-world | `boundary-map` | `light` | diagram |
| 19 | S-19 | 企业 Gap 集中在公开证据与责任边界 | `gap-matrix` | `signal` | table |
| 20 | S-20 | 04 · 市场：Agent 不是一个市场 | `section-signal` | `dark` | shape-composition |
| 21 | S-21 | 三层分别争夺架构、习惯与预算 | `market-layers` | `signal` | diagram |
| 22 | S-22 | 中国竞争不是一场，而是三场 | `competitor-map` | `light` | table |
| 23 | S-23 | 冻结 Grader、Run ID 与 Evidence Bundle 才能复现 | `study-loop` | `signal` | diagram |
| 24 | S-24 | 结论：先把架构优势变成可验证的采用优势 | `closing-actions` | `dark` | shape-composition |

## Asset manifest

No external visual assets are required. Use only editable PowerPoint-native shapes, connectors, tables, and typography. Do not download stock images, logos, screenshots, icon packs, web assets, or AI-generated images.

| Asset category | Source | License | Credit |
| --- | --- | --- | --- |
| Diagrams | PowerPoint native shapes and connectors | not-applicable | Diagram synthesized from cited official sources |
| Tables | PowerPoint native table or shapes | not-applicable | Assessment inference from public evidence where specified |
| Icons | PowerPoint basic geometry only | not-applicable | none |

## Graphic build list

1. S-01: 右侧以中央 Harness control plane 节点为核心，Model、Tool、Session、Sandbox、UI 五个节点沿椭圆轨道分布；一条 signal path 依次连接节点。
2. S-02: 三层垂直图：Model → Harness control plane → Environment；Harness 内含 Context、Policy、Tool、Session 四个小节点，副作用箭头从 Tool 进入 Environment，事件箭头回到 Session。
3. S-03: 四个编号节点沿左下至右上的 signal path：Runtime、Extensibility、Enterprise、Market；路径终点是 Evidence。
4. S-04: 右侧三条不同高度的 signal path 分别标注 Control、Composition、Event，并在终点汇合为 Harness。
5. S-05: 七步闭环中加入 executionMode 分类与 exclusive barrier；并发 body 使用平行路径，随后在 ordered commit 节点重新合流。
6. S-06: 中央 Plugin runtime，外圈五个 primitive；Effect 与 Scope 之间用双向 lifecycle 箭头，底部橙色 callout 标出外部副作用不会自动回滚。
7. S-07: 五层插件栈，每层包含 2-3 个代表节点；右侧一条 lifecycle 轴贯穿所有层，标注 mount、event、dispose。
8. S-08: 上方 Host plane；中部 standing Agent Preset scope；下方两个 Session Agent scope 以 parent 连接同一 Preset，并各自记录 selection event。
9. S-09: 四张半透明配置叠片依次覆盖，最上层 --patch 使用 signal 边框；右侧输出 Effective runtime。
10. S-10: 顶部 append-only event stream；中部 versioned checkpoint row；底部以 tail replay 生成 Conversation、Tasks 与 Usage 三个当前视图。
11. S-11: Definition → Provider → Consumer → Agent 横向链；上方 Policy wrappers 以垂直拦截线连接 Consumer；下方列出可替换 capability。
12. S-12: 中央 core 节点向外辐射五个 interface 节点，底部一条 plugin lifecycle signal path。
13. S-13: 中央 Agent/Session/Tools core，五个入口环绕；Web 拆成 HTTP POST、events.mux 和 events.host；SDK 分成 caller-supplied 与 bundled subprocess。
14. S-14: 五段 pipeline 从 Host source 到 Client，Typert 段展开为 analyze、model、emit 三个子节点；底部 build-order 箭头单向前进。
15. S-15: 状态机增加 Waiting for page 与 Post-settle render 分支；Run ok 和 Render failed 作为两个独立结果节点。
16. S-16: 右侧三个递进门：Local runtime、Local data paths、Enterprise governance；只有最后一扇门通向 Production。
17. S-17: 三个从左到右递进的容器，分别放置 process、data-flow、governance icon；每层底部标注当前判断 Strong、Configurable、Gap。
18. S-18: 中央 Agent，外围 Sandbox、Credential、Telemetry、Outbound、Persistence、Web 六个边界；每条路径标出 covered 与 not covered。
19. S-19: 五行三列表格：Dimension、Harness anchor、Enterprise target；最右增加文字 severity 标签 High 或 Blocking，Blocking 使用 risk 文本和 stop icon。
20. S-20: 右侧三层阶梯，每层只有层名和 buyer：Builder、Developer、Enterprise buyer。
21. S-21: 三层市场阶梯：每层左侧是 buyer 与 value，右侧是代表产品；层间箭头分别标注 enables、habits、governance。
22. S-22: 三列竞争矩阵列出 Layer、China peers 与 winning mechanism；底部 Attention → Experimentation → Adoption → Revenue 使用断裂箭头。
23. S-23: Choose 与 Freeze 后分成两个系统；在 Run 之前加入 unique run_id gate，合流到 Evidence bundle、Shared rubric、Explain 与 Repeat。
24. S-24: 左侧一个结论节点连接 Architecture、Governance、Evidence 三个支点；右侧 30/60/90 天阶梯，终点为 Decision gate。

All connectors must use explicit anchor points and remain attached when shapes move. Keep diagrams editable; do not rasterize them.

## Citation rules

1. Resolve every slide `source_refs` entry through `knowledge-map.json`.
2. Add a 9 pt compact source footer inside the 0.55 in safe margin on all content and summary slides.
3. Preserve full URLs in speaker notes where practical.
4. S-01 and S-24 must state `v0.1.0-rc.7 · commit 99f6f02`; S-01 must also state `Tianshu ede03b8`.
5. S-22 must state `GitHub snapshot: 2026-08-18` and `Stars/forks measure public attention, not adoption or revenue`.
6. S-17–S-19 must label enterprise conclusions as assessment based on public evidence, not verified compliance.
7. Do not attach a citation to a claim the source does not support.

## Style implementation rules

- Use only tokens, layouts, and variants in `style-guide.json`.
- Keep body text at or above 17 pt and source footers at or above 9 pt.
- Use one dominant native visual per slide and signal cyan on at most one primary node.
- Do not use decorative color bars, title underlines, gradients, glow, glass effects, or generic card grids.
- Do not encode risk or state with color alone.
- Preserve the 0.55 in safe margin and all approved alt text.
- Populate speaker notes from `deck-design.json`.

## Required QA

1. Extract and compare slide text against `deck-design.json`.
2. Open and save through a PowerPoint-compatible implementation.
3. Render all 24 slides and inspect overflow, overlap, clipping, wrapping, contrast, small type, orphaned elements, placeholders, and connector drift.
4. Compare each slide with its locked layout, variant, visual kind, title, content, citations, and alt text.
5. Record evidence and repairs in `final-qa.json`.
6. Deliver only when content, file, visual, and design-fidelity checks pass.
