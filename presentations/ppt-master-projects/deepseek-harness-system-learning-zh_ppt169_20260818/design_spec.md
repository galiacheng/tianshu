<!-- ppt-master-schema: design-spec/v1 -->
# DeepSeek Harness System Learning ZH - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | DeepSeek Harness System Learning ZH |
| Canvas Format | PPT 16:9 |
| Page Count | 24 |
| Primary Language | zh-CN |
| Target Audience | 技术负责人、Agent 平台架构师、AI 开发者与产品战略人员；对 LLM Agent 有基本认识，希望系统理解 DeepSeek Harness 的架构、企业边界与国内外市场位置。 |
| Communication Intent | 先教学解释 DeepSeek Harness 的运行时、Cordis、Session、接口与 Plugin 机制，再用企业安全边界和三层市场框架支持架构评审、技术选型与后续实验决策。 |
| Desired Audience Outcome | 听众能复述四个核心问题，解释关键运行机制与限制，区分 runtime、developer product 和 enterprise platform，并据此批准或执行一项可复现的 90 天评估计划。 |
| Core Message / Ask / Action | DeepSeek Harness 值得学习的是可组合控制层与事件驱动状态；是否值得采用，必须由企业控制证据和真实任务实验决定，而不能由 stars 或自托管标签决定。 |
| Delivery Context | 主要为有主讲的约 32 分钟技术分享；次要为会后独立阅读、架构评审和中英文跨团队传播。 |
| Artifact Afterlife | 作为双语学习材料、架构与企业就绪度评审附件、市场分析参考以及后续对比实验的交接记录。 |
| Reading Mode | balanced |
| Content Strategy | 严格遵守已经通过校验的 24 页 deck-design.json：不改变叙事、页序、结论、引用或视觉意图；只允许中文本地化和 PowerPoint 实现所需的排版调整。 |
| Design Style | Circuit Atlas：深海军蓝章节页、浅色机制页、电光青 signal path、模块化节点和可编辑证据图。 |
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
- **Mode Behavior**: 以 instructional 负责从四个核心问题进入运行时、Cordis、Session、接口和 Plugin 的先后教学；在企业边界、市场位置与 90 天评估部分切换为 pyramid，先给判断，再给证据和可执行动作。标题以清晰教学句或判断句为主，章节之间显式回顾已知与下一步。
- **Visual style**: custom
- **Visual Style References**: blueprint, dark-tech
- **Visual Style Behavior**: blueprint 提供细线框、工程网格、坐标式标注和架构连接；dark-tech 提供深色章节负空间与局部 signal 强调。内容页保持浅色、平面、无阴影，以一张主图解或证据结构为骨架；发光仅作为极轻的当前状态提示，不使用玻璃拟态或霓虹装饰。
- **Theme**: Signal path 作为跨页识别系统：青色路径只表达控制、事件或数据关系；每页最多一个 signal 节点；章节页用深色场和上升路径重置节奏。
- **Tone**: 工程化、克制、可解释；技术判断必须同时给出边界和证据等级。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F7FAFC | 浅色内容页与可读证据场 |
| Secondary background | #E8EEF7 | 分组区域、表格隔行与低优先级模块 |
| Primary | #101B35 | 深色章节页、主标题与主节点 |
| Accent | #00C2D7 | signal path、当前状态和关键因果 |
| Secondary accent | #3448A8 | 主系列、次级路径与结构分区 |
| Body text | #101828 | 正文、标签和表格主文本 |
| Muted text | #475467 | 次要说明、来源与注释 |
| Warning | #D97706 | 边界提醒与需要验证的假设 |
| Risk | #C2415B | 高风险、失败边界与公开证据缺口 |
| Success | #15803D | 已验证状态与通过条件 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 几何无衬线、结论导向、紧凑 | Microsoft YaHei | Arial | sans-serif |
| Body | 中性无衬线、适合投影与独立阅读 | Microsoft YaHei | Arial | sans-serif |
| Code | 等宽、用于 contract、event 与命令标签 | Cascadia Mono | Cascadia Mono | Consolas, monospace |

- **Title stack**: Microsoft YaHei, Arial, sans-serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Code stack**: Cascadia Mono, Consolas, monospace
- **Role rationale**: Code 角色反复承载 `executionMode`、`events.mux`、`run_id` 等精确技术标识，与说明性正文分离。

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

- **Hierarchy direction**: 先读结论标题，再沿青色 signal path 或主证据结构完成一次左到右、上到下的解释。
- **Composition tendency**: 每页一个主图解或数据结构；根据因果、层级、状态、矩阵或行动阶梯选择几何，不把内容降格为重复卡片墙。
- **Cross-page continuity**: signal path、角标、单一强调节点与页脚版本线稳定重复；章节页切换为深色场，内容页在浅色与 signal surface 之间变化。
- **Spacing posture**: 章节与结论页呼吸充分；架构深潜和证据页允许高密度，但通过网格、路径和留白保持分组清晰。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/cpu | Model、runtime、计算节点 |
| tabler-outline/tool | Tool 执行与 capability |
| tabler-outline/database | Session、projection 与持久化 |
| tabler-outline/shield-lock | Sandbox、治理与企业控制 |
| tabler-outline/network | Web、transport 与 data path |
| tabler-outline/terminal-2 | CLI、Headless、ACP |
| tabler-outline/world | Web search、全球市场与外连 |
| tabler-outline/plug | Plugin、Provider 与装配 |
| tabler-outline/code | SDK、Typert 与 contract |
| tabler-outline/timeline | Event stream、checkpoint 与 replay |
| tabler-outline/server | Host、runtime ownership 与部署 |
| tabler-outline/key | Credential、Secrets 与 IAM |
| tabler-outline/file-code | Package、patch 与 evidence artifact |
| tabler-outline/git-branch | 分支、版本与双路实验 |
| tabler-outline/chart-bar | 市场快照与评分 |
| tabler-outline/activity | 运行状态与 telemetry |
| tabler-outline/alert-triangle | 风险、边界与待验证项 |
| tabler-outline/arrow-right | 单向控制、构建与行动路径 |
| tabler-outline/check | 已验证状态 |
| tabler-outline/cloud | 云平台与 enterprise platform |
| tabler-outline/lock | 隔离、审批和访问控制 |
| tabler-outline/settings | Profile、patch 与策略 |
| tabler-outline/x | 不覆盖、失败与错误推论 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P19 | table | comparison_matrix | 对比五类 Harness anchor、enterprise target、priority 与 public evidence status |
| P22 | table | comparison_matrix | 对比三层中国竞争、代表产品、公开注意力指标、许可边界和制胜机制 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Layout pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## IX. Content Outline

### Part 1: 开场——为什么需要 Harness

#### Slide 01 - DeepSeek Harness：Everything is a Plugin

- **Audience move**: 从“这是另一个 Agent 项目”转为“它是一层可组合、可观察、可替换的控制面”。
- **Layout**: 左侧标题、双版本边界与三重视角；右侧以 Harness control plane 为中心，Model、Tool、Session、Sandbox、UI 沿一条椭圆 signal path 分布。
- **Title**: DeepSeek Harness：Everything is a Plugin
- **Core message**: DeepSeek Harness 的核心价值是把 Agent 运行时变成可组合、可观察、可替换的控制层。
- **Content**: 从架构机制到企业边界与全球/中国竞争；基于 v0.1.0-rc.7 · commit 99f6f02；Tianshu ede03b8 · knowledge-to-pptx → ppt-master。
- **Visualization**: 中央控制面与五个插件节点构成单一 orbit；signal path 只表示能力围绕控制层装配。
- **Fact IDs**: K-001, K-005, K-030
- **Cover impact**: 绑定钩子为 “Everything is a Plugin”，并用插件轨道把口号立即转化为控制层心智模型。

#### Slide 02 - Agent 的难点不在“会想”，而在“安全地做完”

- **Audience move**: 从关注模型推理能力转为识别 Harness 对副作用、记录与恢复的控制责任。
- **Layout**: 左侧一句因果判断；右侧 Model → Harness control plane → Environment 三层图，所有执行箭头必须经过 Harness，证据回流 Session。
- **Title**: Agent 的难点不在“会想”，而在“安全地做完”
- **Core message**: 模型只提出下一步；Harness 才把建议变成受控、可记录、可恢复的现实操作。
- **Content**: 模型：生成下一步建议；Harness：组装上下文、选择 Tool、施加权限与策略；真实环境：文件、进程、网络、业务系统产生副作用；Session：把可见输入与结果变成可恢复证据。
- **Visualization**: Harness 内含 Context、Policy、Tool、Session 四个节点；Tool 向 Environment 产生副作用，Environment 与模型可见结果回到 Session。
- **Fact IDs**: K-001, K-002, K-008

#### Slide 03 - 用四个问题读懂 DeepSeek Harness

- **Audience move**: 从信息散点转为拥有一条可复述的四问学习路线。
- **Layout**: 四个编号节点沿左下到右上的 signal path：Runtime、Extensibility、Enterprise、Market；终点为 Evidence。
- **Title**: 用四个问题读懂 DeepSeek Harness
- **Core message**: 理解项目只需回答四个问题：如何运行、如何扩展、能否治理、与谁竞争。
- **Content**: 1 · Runtime：一次 Agent turn 如何被控制？；2 · Extensibility：Everything is a Plugin 如何成立？；3 · Enterprise：安全原语与采购控制面差多少？；4 · Market：全球与中国竞品处于哪一层？
- **Visualization**: 上升路径将四问连接为逐层建立证据的学习旅程，而不是普通目录。
- **Fact IDs**: K-002, K-005, K-018, K-019

### Part 2: 架构——控制、装配与可恢复状态

#### Slide 04 - 01 · 架构：三条流构成 Harness

- **Audience move**: 从按 package 数量理解架构转为按控制流、装配流和事件流理解系统。
- **Layout**: 深色章节场；大号 `01` 与结论在左，右侧三条不同高度的 signal path 汇合为 Harness。
- **Title**: 01 · 架构：三条流构成 Harness
- **Core message**: 架构的主线是控制流、装配流和事件流，而不是 package 数量。
- **Content**: Control flow · Composition flow · Event flow。
- **Visualization**: 三条路径分别代表 Agent loop、Profile/Cordis 和 Session event stream，并在控制面终点汇合。
- **Fact IDs**: K-002, K-003, K-008
- **Motion suggestion**: 按 Control → Composition → Event 的语义顺序建立路径，以帮助听众预装本章三种关系；不激活自定义动画执行。

#### Slide 05 - 一次 Turn 不是一次请求，而是带屏障的控制闭环

- **Audience move**: 从“Tool 并发即无序”转为理解 exclusive barrier 与 ordered commit 的精确边界。
- **Layout**: 横向闭环为主视觉；executionMode 分类与 exclusive barrier 位于中部，两个 Tool body 并行路径在 ordered commit 前重新合流。
- **Title**: 一次 Turn 不是一次请求，而是带屏障的控制闭环
- **Core message**: Tool body 可以重叠，但 exclusive barrier 与有序提交保证模型看到确定顺序。
- **Content**: Project context → Policy hooks → Model request；Tool choice → executionMode 分类 → exclusive barrier；Body 可重叠 → post-processing 与 tool/result 按模型顺序提交；Continue / stop / fail；副作用权威在 Tool execution，并发不等于乱序提交。
- **Visualization**: 七步控制环；平行段只覆盖 dispatch 与 Tool body，合流段明确承载 post-processing 和 Session commit。
- **Fact IDs**: K-002, K-008, K-009

#### Slide 06 - 五个 Primitive 让插件化从“约定”变成“运行时”

- **Audience move**: 从把 Cordis 当依赖注入容器转为识别能力可见性、事件、回收和所有权原语。
- **Layout**: 中央 Plugin runtime；Context、Service、Event、Effect、Scope 环绕；底部独立 warning 提醒外部副作用不会自动回滚。
- **Title**: 五个 Primitive 让插件化从“约定”变成“运行时”
- **Core message**: Cordis 把能力、依赖、事件和生命周期装进同一个 Context 树。
- **Content**: Context：能力可见性与生命周期边界；Service：稳定依赖契约；Event：跨插件协作与拦截；Effect：带 disposer 的注册；Scope：一次激活的资源所有权；可逆注册 ≠ 外部副作用自动回滚。
- **Visualization**: 五原语围绕一个 runtime 协作；Effect 与 Scope 用 lifecycle 双向关系连接，warning 位于系统边界外。
- **Fact IDs**: K-003, K-004

#### Slide 07 - “Everything is a Plugin”统一的是生命周期

- **Audience move**: 从“插件越多越好”转为判断跨层能力是否共享装配、依赖、事件和 dispose 语义。
- **Layout**: 五层插件栈自 Host 到 Interfaces；右侧一条贯穿轴标注 mount、event、dispose。
- **Title**: “Everything is a Plugin”统一的是生命周期
- **Core message**: 插件化的价值是所有能力共享装配、依赖、事件与回收语义，而不是把代码拆成更多包。
- **Content**: Host 与启动表面；Agent Preset 与 Model；Tool、Policy 与 Sandbox；Session、Persistence 与 Projection；Web/CLI/ACP/SDK 界面；统一装配 · 显式依赖 · 可替换 Provider · 可回收 Scope。
- **Visualization**: 分层栈表达能力广度，贯穿轴表达统一机制；节点密度从底层运行时向上层接口逐步减轻。
- **Fact IDs**: K-003, K-005, K-010

#### Slide 08 - Preset 是共享 standing scope，Session 才是运行实例

- **Audience move**: 从“每个 Session 重挂 Preset”转为理解每进程一次 standing mount 与 Session parent 关系。
- **Layout**: 上方 Host plane；中部 standing Agent Preset scope；下方两个 Session Agent scope 通过 parent 连接同一 Preset，并各自记录 selection event。
- **Title**: Preset 是共享 standing scope，Session 才是运行实例
- **Core message**: Preset 每进程只挂载一次；Session Agent scope 通过 parent 关系加入所选能力，并用事件记录切换。
- **Content**: Host plane：Web、persistence、credential、sandbox、provider；Agent Preset：每进程一次 standing mount；Session Agent scope：parent → selected preset；切换：agent-preset/selected event，而不是改写创建 header；共享 Preset 中的可变状态必须按 Session 或显式 owner 分区。
- **Visualization**: 双 plane 与两个 Session 分支；中部唯一 Preset 节点强调共享，selection event 作为每个 Session 的可恢复事实。
- **Fact IDs**: K-005, K-006

#### Slide 09 - 最终能力来自四层叠加，而不是单个配置文件

- **Audience move**: 从只看最终 JSON 转为追踪每层配置来源与覆盖顺序。
- **Layout**: 四张透明配置叠片从左下到右上；`--patch` 使用 signal 描边，右侧输出 Effective runtime。
- **Title**: 最终能力来自四层叠加，而不是单个配置文件
- **Core message**: Profile 是有顺序的配置叠层；越靠后的 patch 越接近当前用户与本次运行。
- **Content**: 1 · Bundles：可复用默认能力集合；2 · Profile patch：产品或角色选择；3 · Home patch：用户级长期覆盖；4 · --patch：本次运行临时覆盖；后层覆盖前层，顺序属于行为语义。
- **Visualization**: 每层保留来源标签和覆盖箭头；最终 runtime 显示为叠层后的唯一输出。
- **Fact IDs**: K-007

#### Slide 10 - Event 是事实，Cache 只保存可重放的 Unit State

- **Audience move**: 从把 cache 当 UI 快照转为理解 versioned checkpoint 与 tail replay。
- **Layout**: 顶部 append-only event stream；中部 checkpoint `(key, ver, seq, val)`；底部 replay 分叉到 Conversation、Tasks、Usage。
- **Title**: Event 是事实，Cache 只保存可重放的 Unit State
- **Core message**: Projection cache 保存 versioned checkpoint row，而不是持久化 UI 视图；当前视图来自 checkpoint 加 tail replay。
- **Content**: Events：user、assistant、tool、approval、error；Request metadata：request/header · request/context；Checkpoint row：(key, ver, seq, val)；View：restore / re-view unit state + replay tail；Invariant · model-visible means logged。
- **Visualization**: 时间方向从左到右；checkpoint 位于已处理 seq，tail events 进入三个独立 projection。
- **Fact IDs**: K-008, K-009
- **Motion suggestion**: 相邻状态保持同一 event-stream 心智地图，只切换高亮从 facts 到 checkpoint 再到 replay，以降低架构切换成本。

#### Slide 11 - Capability Seam 把 Agent 与具体实现隔离

- **Audience move**: 从把 Service 当单一实现转为理解 Definition、Provider registry、Consumer 和 Policy 的依赖方向。
- **Layout**: Definition → Provider registry → Consumer → Agent 横向链；上方 Policy wrappers 通过垂直拦截线进入 Consumer；下方独立 subprocess/ripgrep seam。
- **Title**: Capability Seam 把 Agent 与具体实现隔离
- **Core message**: 可替换能力需要 Definition、Provider、Consumer 三个角色，Policy 在接缝上组合。
- **Content**: Definition：稳定类型、方法与事件；Provider：单选实现或多命名 registry；Consumer：Tool、Agent loop、UI 或另一 Service；例外边界：tool-fs-search 走 subprocess/ripgrep，而非 ctx.fs；Policy：approval · retry · timeout · observation。
- **Visualization**: 主链表达依赖反转，Policy 线表达横切控制，底部虚线表达不经过 ctx.fs 的边界例外。
- **Fact IDs**: K-005, K-010

### Part 3: 扩展——多界面与动态 Plugin

#### Slide 12 - 02 · 扩展：一个 Core，多种 Interface

- **Audience move**: 从把各入口当独立产品转为识别共同 Core 与不同 adapter/lifecycle。
- **Layout**: 深色章节场；中央 Core 向五个 interface 节点辐射，底部 plugin lifecycle signal path。
- **Title**: 02 · 扩展：一个 Core，多种 Interface
- **Core message**: 扩展性来自同一核心上的多 adapter 与可检查的插件发布流程。
- **Content**: CLI · Web · Headless · ACP · SDK · Dynamic Plugin。
- **Visualization**: 辐射图证明 core reuse；底部生命周期路径预告发现、定义、运行、诊断和修复。
- **Fact IDs**: K-011, K-014

#### Slide 13 - 五个入口共享 Core，但 Transport 与 Runtime Ownership 不同

- **Audience move**: 从“SDK 与 Web 只是不同 UI”转为识别进程、连接、恢复和 runtime ownership 边界。
- **Layout**: Agent/Session/Tools core 居中；CLI、Web、Headless/ACP、TypeScript SDK、Python SDK 环绕；Web 展开一条 POST 上行和两条 WS 下行。
- **Title**: 五个入口共享 Core，但 Transport 与 Runtime Ownership 不同
- **Core message**: 界面共享 Agent/Session 语义，但 Web 与两类 SDK 的进程、连接与恢复边界不同。
- **Content**: CLI：交互式产品入口；Web：HTTP POST up + events.mux / events.host WS down；Headless / ACP：自动化与 stdio JSON-RPC；TypeScript SDK：调用方提供 runtime；Python SDK：默认 bundled subprocess。
- **Visualization**: 所有 adapter 连接同一 core；Web 和 SDK 分支展开各自 transport 细节，避免把差异藏在注释中。
- **Fact IDs**: K-011, K-012

#### Slide 14 - Typert 让 Host / Client 契约只定义一次

- **Audience move**: 从认为共享 tsconfig 即可转为理解 Host build 产生跨进程 contract 的单向依赖。
- **Layout**: Host source → Typert → metadata → registry/gateway → Client 五段 pipeline；Typert 展开 Analyze、Model、Emit；底部只有单向 build-order 箭头。
- **Title**: Typert 让 Host / Client 契约只定义一次
- **Core message**: Typert 把跨进程结构在 Host build 阶段冻结，再交给 Client 消费。
- **Content**: Host TypeScript source；Analyzer → compiler-independent model → emitter；Remote metadata · reflection · Zod schemas；Loader / registry / gateway；Client compiler face；Build order：Host contracts → Client typecheck。
- **Visualization**: 五段管线保持同一轴；Typert 子步骤用嵌套结构，auth/TLS/authorization 以边界注释标明不在 schema generation 范围内。
- **Fact IDs**: K-013

#### Slide 15 - Run ok 不代表后续 Client Render 一定成功

- **Audience move**: 从把 activate 成功当完整成功转为分辨页面等待、审批、Run 与后续 render 的独立边界。
- **Layout**: 生命周期状态机：Inspect → Define → Waiting for page → Approval → Starting → Run result；Run ok 后分叉到 Render ok / Render failed。
- **Title**: Run ok 不代表后续 Client Render 一定成功
- **Core message**: 动态 Plugin 是页面参与的小型发布系统；激活、审批与后续渲染是不同成功边界。
- **Content**: Inspect：list → minimal query；Define：immutable Plugin / Package；Client half：等待匹配页面连接；Run：approval → starting → ok / failed；After settle：render diagnostics 仍可能失败；Repair = new Package · Rollback = explicit currentPackageId。
- **Visualization**: 状态机保留两个成功边界；repair 与 rollback 作为版本操作规则贴近 Package 而非 Run 节点。
- **Fact IDs**: K-014, K-015

### Part 4: 企业——安全原语不等于控制面

#### Slide 16 - 03 · 企业：Local 不等于 Governed

- **Audience move**: 从用“开源/自托管”替代治理判断转为要求三层独立证据。
- **Layout**: 深色章节场；Local runtime、Local data paths、Enterprise governance 三扇递进门，只有最后一门通向 Production。
- **Title**: 03 · 企业：Local 不等于 Governed
- **Core message**: 安全原语降低局部风险；企业控制面决定能否规模化采购。
- **Content**: Isolation primitives ≠ Enterprise control plane。
- **Visualization**: 三道门按证明强度递增，Production 位于治理门之后，避免把安全功能表误呈现为成熟度。
- **Fact IDs**: K-016, K-017, K-018

#### Slide 17 - Self-hosted 只回答了三分之一的问题

- **Audience move**: 从单一部署位置判断转为分别验证 runtime、data path 和 control evidence。
- **Layout**: 三个从左到右递进容器：Runtime local、Data path、Control evidence；底部状态分别为 Primitives、Configurable、Public evidence gap。
- **Title**: Self-hosted 只回答了三分之一的问题
- **Core message**: 私有部署必须分别证明运行位置、数据路径和组织控制。
- **Content**: Layer 1 · Runtime local：代码与进程在哪里？；Layer 2 · Data path：模型、搜索、Plugin、telemetry 去哪里？；Layer 3 · Control evidence：谁能访问、审批、审计、升级和负责？；Harness：Layer 1 有原语 · Layer 2 可配置 · Layer 3 公开证据不足。
- **Visualization**: 三层同时编码问题、证据状态和升级方向；公开证据不足用文字与 risk 边框双重表达。
- **Fact IDs**: K-016, K-017, K-018, K-031

#### Slide 18 - Sandbox 只约束 File Effects 与 Same-world

- **Audience move**: 从笼统“有 sandbox 所以安全”转为逐条说明 covered 与 not covered。
- **Layout**: 中央 Agent，外围 Sandbox、Credential、Telemetry、Outbound、Persistence、Web 六个边界；每条路径同时显示 covered 与 not covered。
- **Title**: Sandbox 只约束 File Effects 与 Same-world
- **Core message**: 每个安全原语都有明确边界；不能从文件沙箱推导网络、进程、凭据、身份或审计结论。
- **Content**: Sandbox：file effects + same-world；Windows 不限制 read/network/process；Credential：0700/0600 不阻止同 UID Tool；Telemetry：默认关，开启后可含 prompt、Tool、文件、命令与 cwd；Outbound：Web search 默认开，fetch 与 Session FTS 默认关；Persistence / Web：JSONL 不自动删，Host/Origin fence 不是 auth；Fail-closed ≠ full isolation · Append-only ≠ tamper-proof audit。
- **Visualization**: 六条边界线按数据流布局，不做 checklist；每项用文本、图标和状态符号共同说明覆盖范围。
- **Fact IDs**: K-017, K-031, K-032

#### Slide 19 - 企业 Gap 集中在公开证据与责任边界

- **Audience move**: 从抽象“企业能力不足”转为一份可验证的身份、执行、数据、审计与生命周期议程。
- **Layout**: 全宽 comparison matrix；五行依次为 Identity/tenancy、Execution、Secrets/data、Audit、Lifecycle；最右同时显示 Priority 与 Evidence status。
- **Title**: 企业 Gap 集中在公开证据与责任边界
- **Core message**: 企业决策需要验证身份、隔离、审计和生命周期；公开材料缺口不能自动变成绝对能力断言。
- **Content**: Identity / tenancy：Host fence → SSO、RBAC、workspace isolation；Execution：file sandbox → network/process/remote isolation；Secrets / data：local file → Vault/KMS、DLP、residency evidence；Audit：Session log → redaction、retention、tamper evidence；Lifecycle：developer preview → LTS、SBOM、CVE、SLA、support；Priority：High；Evidence status：Public gap。
- **Visualization**: `enterprise-gap-matrix` 为四列纯文本表格；Native-ready: enterprise-gap-matrix=yes。
- **Fact IDs**: K-017, K-018

### Part 5: 市场——全球与中国三层竞争

#### Slide 20 - 04 · 市场：Agent 不是一个市场

- **Audience move**: 从统一排行榜比较转为先固定 buyer、job-to-be-done 与竞争层。
- **Layout**: 深色章节场；右侧三层阶梯仅显示 Runtime、Developer Product、Enterprise Platform 及对应 buyer。
- **Title**: 04 · 市场：Agent 不是一个市场
- **Core message**: 先识别竞争层，再比较产品；否则同一排行榜混合了不同买家与商业模式。
- **Content**: Runtime / framework · Developer product / control surface · Enterprise platform。
- **Visualization**: 三层阶梯分别标注 Builder、Developer、Enterprise buyer；不出现品牌，先建立分类框架。
- **Fact IDs**: K-019, K-027

#### Slide 21 - 三层分别争夺架构、习惯与预算

- **Audience move**: 从把所有 Agent 产品当直接替代品转为理解三层价值、买家与切换成本。
- **Layout**: 三层市场阶梯扩展为 buyer、value、representatives、switching cost 四类信息；层间箭头标注 enables、habits、governance。
- **Title**: 三层分别争夺架构、习惯与预算
- **Core message**: Harness 赢架构心智，开发者产品赢日常入口，企业平台赢治理与预算。
- **Content**: Runtime/framework：Harness、AgentScope、LangGraph、OpenAI SDK、ADK、Agent Framework；Developer/control surface：Claude Code、Codex、Copilot、OpenHands、Qwen、Kimi、Trae；Enterprise platform：Dify、Coze、Model Studio、Tencent ADP；切换成本：Capability contract → Workflow habit → IAM/VPC/SLA。
- **Visualization**: 每层使用不同结构权重而非品牌 Logo 墙；OpenHands 明确位于 developer/control-surface 层。
- **Fact IDs**: K-019, K-021, K-022, K-024, K-025, K-026, K-033

#### Slide 22 - 中国竞争不是一场，而是三场

- **Audience move**: 从 stars 榜单转为同层比较、许可边界和不同制胜机制。
- **Layout**: 上部 comparison matrix 为 Layer、China peers、Public attention、Winning mechanism；下部 Attention → Experimentation → Adoption → Revenue 使用断裂箭头。
- **Title**: 中国竞争不是一场，而是三场
- **Core message**: 中国市场中，AgentScope 争 runtime，Qwen Code 争开发者入口，云与低代码平台争企业预算。
- **Content**: Runtime 最近邻：AgentScope · 29,019 stars / 3,369 forks；开发者入口：Qwen Code · 27,144 / 2,877，其次 Kimi、Trae；企业预算：Dify · 152,784 / 24,135，Coze、Model Studio、ADP；Harness：157,324 / 16,338，优势是公开 plugin runtime；License 边界：Dify 有附加条件，Coze 部分能力仅商业版；2026-08-18 snapshot · Attention ≠ Adoption ≠ Revenue。
- **Visualization**: `china-competition-matrix` 为同层比较表；Native-ready: china-competition-matrix=yes。断裂推论轴用 `x` 标记三个不可直接跨越的证据跳跃。
- **Fact IDs**: K-020, K-021, K-022, K-023, K-024, K-025, K-027

### Part 6: 行动——用证据验证判断

#### Slide 23 - 冻结 Grader、Run ID 与 Evidence Bundle 才能复现

- **Audience move**: 从一次 demo 成功转为拥有可重复、可审计的同层对比协议。
- **Layout**: Choose 与 Freeze 后分叉为 System A / System B；unique run_id gate 位于执行前；两路合流到 Evidence bundle、Shared rubric、Explain、Repeat。
- **Title**: 冻结 Grader、Run ID 与 Evidence Bundle 才能复现
- **Core message**: 真正的比较不仅冻结输入，还要冻结 evaluator，并防止缓存复用旧 patch 结果。
- **Content**: Choose：同层竞品 + 确定性任务；Freeze：commit、model、Tools、network、budget、grader；Run：patch 改变即使用新 run_id；Capture：summary + report.json + test_output.txt + run_instance.log + eval.sh + patch.diff；Score：outcome、recovery、safety、effort、efficiency；一次成功 = case study，重复任务才接近 benchmark。
- **Visualization**: 双路实验保持对称输入与独立运行，证据束使用六个文件标记，评分与机制解释位于合流后。
- **Fact IDs**: K-028, K-029

#### Slide 24 - 结论：先把架构优势变成可验证的采用优势

- **Audience move**: 从“项目值得关注”转为可执行的 30/60/90 天证据计划与明确决策门。
- **Layout**: 左侧结论节点由 Architecture、Governance、Evidence 三个支点支撑；右侧 30/60/90 天阶梯通向 Decision gate；底部保留版本和证据边界。
- **Title**: 结论：先把架构优势变成可验证的采用优势
- **Core message**: Harness 值得学习的是控制层设计；是否值得采用，要靠企业控制面补齐与真实任务证据。
- **Content**: 30 天：复现 Profile、Session 和 capability seam；60 天：完成安全数据流与 enterprise gap 设计；90 天：与 AgentScope / Qwen Code 做受控对比；决策门：通过证据选择嵌入、扩展、合作或观望；Architecture attention → Reproducible evidence → Governed adoption。
- **Visualization**: 三支点与行动阶梯构成同一闭环；Decision gate 只在三阶段证据到位后开启。
- **Fact IDs**: K-001, K-010, K-018, K-019, K-028
- **Data class: scenario**: 30/60/90 天里程碑是建议的评估计划目标，不是外部事实。
- **Closing impact**: 绑定结论为“架构关注必须通过可复现证据才能转化为受治理采用”，以 Decision gate 收束而不是 Thank You 页。

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 以 deck-design.json 的逐页 speaker_notes 为语义权威，保留技术边界、版本基线与引用；正文不重复照读，补充过渡、误区澄清和判断条件。
- **Total duration**: 约 32 分钟
- **Notes style**: 耐心、解释性、结论清晰；先定义再使用，架构页说明机制，企业与市场页明确证据等级。
- **Presentation purpose**: instruct, analyze, support decision
