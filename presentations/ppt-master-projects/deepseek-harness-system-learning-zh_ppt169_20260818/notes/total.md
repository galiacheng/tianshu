# 01_DeepSeek Harness：Everything is a Plugin

这套二十四页教程把 DeepSeek Harness 视为一个 Agent control plane，而不只是另一个对话框架。它的核心价值，是让模型、Tool、Session、Sandbox 与 Interface 围绕同一控制层进行组合、观察和替换。所有技术判断固定在 Harness v0.1.0-rc.7、提交 99f6f02，材料生成则固定在 Tianshu ede03b8 的 knowledge-to-pptx 与 ppt-master Skills。接下来我们会从架构机制、企业边界以及全球和中国市场三个视角建立完整认知。

---

# 02_Agent 的难点不在“会想”，而在“安全地做完”

模型可以提出下一步，但它并不天然拥有文件、进程、网络或业务系统里的执行权。Harness 把模型建议依次放进 Context、Policy、Tool 与 Session，使每次现实操作都能够被约束、记录并在失败后恢复。这里最重要的区别是，思考不等于行动，真正的副作用发生在模型文本之外。只有让所有执行都经过 control plane，环境中的可见结果才可能转化为可恢复、可审查的证据。

---

# 03_用四个问题读懂 DeepSeek Harness

理解这个项目可以沿四个问题推进。第一，一次 Turn 如何被控制；第二，Plugin 如何从代码约定变成运行时能力；第三，这些原语距离企业治理还有多远；第四，Harness 在全球和中国市场究竟与谁、在哪一层竞争。最后还要增加一条证据主线，把每个答案转成可以通过实验验证的采用判断，而不是停留在架构印象。

---

# 04_架构：三条流构成 Harness

阅读 DeepSeek Harness 时，不要从 package 数量开始，而要先看三条流。控制流解释一次 Turn 怎样从上下文走到执行结果，装配流解释能力怎样通过 Profile 和 Cordis 进入 Context，事件流解释 Session 状态怎样被记录、恢复和投影。三条流最终汇入同一个 Harness control plane，因此控制、组合和状态恢复不是三个孤立子系统。掌握这张地图后，后面的实现细节都会有明确归属。

---

# 05_一次 Turn 不是一次请求，而是带屏障的控制闭环

一次 Turn 从 project context 和 policy hooks 开始，经过 model request、tool choice，再由 executionMode 决定如何执行。exclusive call 会建立 barrier，后续 call 必须在启动前重新分类；在允许的区域里，两个 Tool body 可以重叠运行，但并发并不改变提交顺序。post-processing 与 tool result 仍按模型看到的顺序写回 Session，循环再决定 Continue、Stop 或 Fail。这个保证只约束模型可见顺序，文件、进程或网络副作用的最终权威仍然位于 Tool execution 本身。

---

# 06_五个 Primitive 让插件化从“约定”变成“运行时”

Cordis 用五个 primitive 把插件化变成运行时规则。Context 建立可见性与边界，Service 提供稳定依赖契约，Event 负责协作与拦截，Effect 把注册动作变成带 disposer 的可清理效果，Scope 则决定资源何时激活、由谁拥有以及何时释放。它们共同形成一棵 Context tree，并通过 Effect 与 Scope 的关系管理生命周期。需要特别注意，可逆注册并不等于外部副作用自动回滚，已经写入的文件、发出的网络请求和启动的进程仍需要显式补偿。

---

# 07_“Everything is a Plugin”统一的是生命周期

“Everything is a Plugin”真正统一的不是目录形式，而是从 mount、event 到 dispose 的生命周期。最底层是 Host、启动配置、provider 与外部系统，其上依次是 Agent Preset 与 Model，Tool、Policy 与 Sandbox，Session、Persistence 与 Projection，最上层则是 Web、CLI、ACP 和 SDK 等接口适配器。每层都可以作为 Provider、Consumer 或 policy 参与组合，但必须遵守相同的 Context 和 Scope 规则。只有稳定的 capability seam 和清晰的依赖方向，才能让大量 package 形成一个可替换系统，而不是一组偶然拼接的模块。

---

# 08_Preset 是共享 standing scope，Session 才是运行实例

Host plane 持有 Web、持久化、凭据、Sandbox 和 provider 等进程级能力。Agent Preset 通常在每个进程中只做一次 standing mount，然后由多个 Session 的 Agent scope 共同继承，而不是为每个 Session 重挂一次。Session A 和 Session B 各自拥有事件与运行状态，但它们可以指向同一个共享 Preset 节点。由此产生的工程规则是，Preset 内部的可变状态必须按 Session 或其他显式 owner 分区，否则共享能力会变成跨会话状态泄漏。

---

# 09_最终能力来自四层叠加，而不是单个配置文件

有效运行时由四层有序 overlay 形成。Bundles 提供可复用的默认模型、Tool 和策略集合，Profile patch 面向产品或角色做工作流级覆盖，Home patch 保存跨运行的用户级偏好，命令行的 --patch 则最接近当前用户和当前任务。后层覆盖前层，因此顺序本身就是行为语义。调试时不能只保留最终 JSON，还必须保存四层 provenance，才能解释一个 Tool 为什么存在或某条 policy 为什么被覆盖。

---

# 10_Event 是事实，Cache 只保存可重放的 Unit State

Session event stream 记录 request header、request context、user、assistant、tool、approval 与 error 等按序事实。Cache 保存的是带 key、version、sequence 和 value 的 projection checkpoint，而不是另一本事实账本。冷读时先恢复这个可版本化 unit state，再重放 checkpoint 之后的 tail events，分别得到 Conversation、Tasks 或 Usage 等独立视图。关键不变量是，模型可见的信息必须被记录；这样 cache 即使丢失，事实仍可重放，视图也可以重新生成。

---

# 11_Capability Seam 把 Agent 与具体实现隔离

Capability seam 先定义稳定的类型、方法与事件，再由 provider registry 绑定单个实现或一组命名实现，Tool、Agent loop、UI 和 Service 只消费这个契约。Approval、retry、timeout 与 observation 等 policy 可以在接缝上组合，因此 Agent 依赖能力而不是依赖具体 provider。这个三角色模型描述的是依赖方向，并不要求 provider 只有一个。也要识别接缝之外的例外，例如 tool-fs-search 通过 subprocess 启动 packaged ripgrep，它不会自动遵循 ctx.fs 的替换语义。

---

# 12_扩展：一个 Core，多种 Interface

扩展层的核心判断是，Adapter 不应该复制 Agent 与 Session 语义。CLI、Web、TypeScript 和 Python SDK、Headless、ACP 以及 Dynamic Plugin 都围绕同一个 Agent、Session 和 Tools Core，但各自保留明确的 transport 与 runtime ownership。动态插件也仍然服从可检查的生命周期，从 inspect、define、run 到 diagnose 和 repair。下一步需要进一步区分，共享 Core 并不意味着这些入口运行在同一个进程边界里。

---

# 13_五个入口共享 Core，但传输与运行时所有权不同

CLI 是本地交互式入口，Headless 和 ACP 面向自动化并通过 stdio JSON-RPC 由调用方管理连接与生命周期。Web 使用 HTTP POST 上行，并通过 events.mux 和 events.host 两条只下行的 WebSocket 传递事件。TypeScript SDK 与 Python SDK 都是 out-of-process，但前者通常由调用方提供 runtime，后者默认可启动 bundled process。它们共享 Agent、Session 与 Tools 的核心语义，却不共享 transport ownership，因此部署、故障和安全边界必须按入口分别判断。

---

# 14_Typert 让 Host / Client 契约只定义一次

Typert 从 Host 侧的 TypeScript source 开始，经过 Analyze、Model 和 Emit，形成与编译器无关的结构模型。这个模型再生成 remote metadata、reflection 信息和 Zod schemas，由 registry 或 gateway 的 loader、routing 与 remote face 对外发布，Client 只消费生成后的 compiler face。构建顺序因此必须先完成 Host contracts，再做 Client typecheck。这个流程解决跨进程结构契约的一致性，但 authentication、TLS 与 authorization 仍然位于 schema generation 之外。

---

# 15_Run ok 不代表后续 Client Render 一定成功

动态 Plugin 的发布从 Inspect 开始，通过最小查询确认 live contract，然后 Define 一个不可变的 Plugin 和 Package。如果存在 Client half，运行时可能需要等待匹配页面和显式 approval，之后才进入 Starting、Run result 与 Render settle。Run 返回 ok 只说明激活阶段成功，后续 Client render 仍可能独立失败，因此诊断必须同时覆盖 Run 和 render。修复应创建新的 Package，而不是修改已经运行的版本；回滚则通过显式 currentPackageId 选择已知版本。

---

# 16_03 · 企业：Local 不等于 Governed

企业就绪是一串闸门，不是开源天然附带的属性。Local runtime 必须先证明数据路径同样留在本地，再补上身份、策略、审计和责任归属，才有理由进入生产。图中刻意把这些阶段拆开，因为自托管只回答代码在哪里运行，并没有回答谁可以行动、什么会越界，以及事后如何还原一次决策。

---

# 17_Self-hosted 只回答了三分之一的问题

第一个企业问题是 runtime 在哪里执行。第二个问题是 prompt、output、credential、event 与 artifact 实际流向何处，包括远程 model、tool 和 client。第三个问题是控制与证据能否识别行动者、执行策略、保留可审计记录并支持复核。Self-hosted 可以回答第一个问题，却仍然让后两个问题保持开放。

---

# 18_Sandbox 只约束 File Effects 与 Same-world

仓库中的 Sandbox 对 file effects 与 same-world execution 提供了有意义的控制，但它不是覆盖所有路径的通用安全边界。Host API access、Plugin loading、remote transport、credential residency、observability data 与 rollback 分别跨越不同边界，因此都需要自己的执行与复核机制。企业真正要问的不是有没有 Sandbox，而是它覆盖哪些流，以及哪些控制仍然必须由外部系统补齐。

---

# 19_企业 Gap 集中在公开证据与责任边界

这张矩阵把当前公开证据与企业采用仍需证明的能力并列起来。Identity 需要 tenant mapping 和 runtime authorization，execution 需要 policy enforcement 与 approval record，data 需要 transport、redaction、retention 和 residency 控制，audit 需要持久导出与对账，lifecycle 则需要签名制品、canary、rollback 和运营责任。这些是证据与责任缺口，不等于架构不可用，但它们定义了严肃试点必须补上的 control shell。

---

# 20_04 · 市场：Agent 不是一个市场

Agent 产品在不同台阶上竞争。Runtime 或 framework 面向 builder，卖的是执行语义与可扩展性；developer product 依靠工作习惯和任务适配获胜；enterprise platform 则通过治理、采购与支持拿到预算。Harness 可以沿这些层级向上移动，但每上一个台阶，购买者、替代物和所需证据都会改变。

---

# 21_三层分别争夺架构、习惯与预算

在 runtime 层，Harness 与 AgentScope 围绕 Plugin 接缝、生命周期语义和执行控制争夺架构位置。在 developer-entry 层，Qwen Code、Kimi、Trae 等产品争夺可重复的工作习惯。在 enterprise-platform 层，Dify、Coze、Model Studio 与 Tencent ADP 争夺治理预算，同时带来身份、网络、SLA 与采购上的高切换成本。因此，有效的竞争分析必须一次只比较同一层。

---

# 22_中国竞争不是一场，而是三场

中国市场快照把 runtime、developer entry 与 enterprise budget 分开，而不是压成一张总榜。以 2026 年 8 月 18 日为截点，公开 stars 与 forks 只能锚定关注度，不能证明 experimentation、adoption 或 revenue，所以图中的推断链被故意断开。许可边界也必须纳入判断：AgentScope 是 Apache 2.0，Dify 带有附加条件，Coze 的部分能力只在商业版提供。真正的决策问题，是每一层靠什么机制获胜，而不是谁拥有最大的标题数字。

---

# 23_可信试点让每一次比较都可重放

可信试点要先冻结一个假设、版本、模型集合、任务和成功阈值，再让 System A 与 System B 成对运行。两条路径使用唯一 run_id，把配置快照、事件、日志、产物、结果和成本绑定成一个证据包。随后用同一标尺判断成功、成本与失败，不允许事后修改指标。如果团队不能解释差异并重放运行，那么结果仍然只是轶事，而不是决策级证据。

---

# 24_把 90 天变成采用决策，而不是一次演示

架构、治理和证据在整个路线图中始终是三根支柱。到第三十天，团队冻结成对实验、负责人、run_id 与共享标尺；到第六十天，补上策略、身份、密钥、审计、重放和失败控制。到第九十天，明确生产负责人、获批 Provider 与 tools、SLO、回滚路径，以及采用和财务指标。闸门必须显式：只有三根支柱同时保持可解释、可重复，才进入 governed adoption；否则就暂停并关闭缺口。
