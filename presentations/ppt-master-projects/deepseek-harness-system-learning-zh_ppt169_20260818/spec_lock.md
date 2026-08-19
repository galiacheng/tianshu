<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 技术负责人、Agent 平台架构师、AI 开发者与产品战略人员
- objective: 逐步解释 Harness 机制并用企业、市场与实验证据，使听众能够评审技术选型并执行可复现的 90 天评估。
- core_message: 可组合控制层值得学习；采用必须由企业控制证据和真实任务结果决定。
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, pyramid
- mode_behavior: 先以先修顺序教学 runtime、Cordis、Session、interfaces 与 Plugins，再在企业边界、市场位置和评估行动中先给判断、后给证据与动作；章节显式回顾已知与下一步。

## visual_style
- visual_style: custom
- visual_style_references: blueprint, dark-tech
- visual_style_behavior: 以工程网格、细线框、坐标式注释和语义连接承载机制；深色章节页与浅色证据页交替，signal cyan 只标记当前控制、事件或数据路径，不使用玻璃拟态、重阴影或装饰性霓虹。

## colors
- background: #F7FAFC
- secondary_bg: #E8EEF7
- primary: #101B35
- accent: #00C2D7
- secondary_accent: #3448A8
- body_text: #101828
- muted_text: #475467
- warning: #D97706
- risk: #C2415B
- success: #15803D

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: Microsoft YaHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- code_family: Cascadia Mono, Consolas, monospace
- body: 24
- title: 42
- subtitle: 32
- annotation: 18
- code: 18

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/cpu, tabler-outline/tool, tabler-outline/database, tabler-outline/shield-lock, tabler-outline/network, tabler-outline/terminal-2, tabler-outline/world, tabler-outline/plug, tabler-outline/code, tabler-outline/timeline, tabler-outline/server, tabler-outline/key, tabler-outline/file-code, tabler-outline/git-branch, tabler-outline/chart-bar, tabler-outline/activity, tabler-outline/alert-triangle, tabler-outline/arrow-right, tabler-outline/check, tabler-outline/cloud, tabler-outline/lock, tabler-outline/settings, tabler-outline/x

## page_rhythm
- P01: anchor
- P02: dense
- P03: breathing
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: breathing
- P13: dense
- P14: dense
- P15: dense
- P16: breathing
- P17: dense
- P18: dense
- P19: dense
- P20: breathing
- P21: dense
- P22: dense
- P23: dense
- P24: anchor

## page_visualizations
- P19: table/comparison_matrix
- P22: table/comparison_matrix

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
