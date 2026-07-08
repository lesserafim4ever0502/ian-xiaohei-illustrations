---
name: ip-illustrations
description: 多 IP 中文正文配图工作流库。用于为中文文章、帖子、博客、Notion 文档、工作流文档、方法论、流程、结构、状态、隐喻或观点生成白底手绘正文配图；支持逐图选择 IP、指定 IP、只做 shot list、编辑已有图，以及定制新的隔离 IP 工作流。
---

# IP Illustrations 工作流库

## 核心定位

这是一个多 IP 中文正文配图 Skill。目标不是把多个角色放进同一张图，而是为文章里的每个配图点选择最合适的独立 IP 工作流，生成清爽、怪诞、有记忆点的 16:9 手绘解释图。

默认内置 3 个隔离工作流：

- `pageworker`：知识整理、文档、信息结构、内容系统。
- `threadsmith`：路径、流程、漏斗、承接、断点修补。
- `holeseeker`：问题诊断、debug、复盘、风险、常见坑。

## 读取顺序

按任务最小需要读取，不要一次塞满上下文：

1. 先读 `references/global-style-dna.md`，确认全局画风。
2. 如果用户没有指定 IP，读 `references/ip-router.md` 和 `references/shot-routing-rules.md`，为每个配图点选择 IP。
3. 如果用户要定制新 IP，读 `references/custom-ip-workflow.md`，只输出 Markdown 规格包。
4. 对于每张图，只读取该图被选中的 `workflows/<ip>/` 目录：
   - `ip.md`
   - `composition.md`
   - `prompt-template.md`
   - `qa.md`

## 隔离原则

- 一篇文章可以使用多个 IP。
- 一张图只能使用一个 IP。
- 不要在一个 IP 的 prompt 里借用另一个 IP 的外形、动作库或禁忌。
- 只有用户明确要求“整篇统一 IP”或指定某个 IP 时，才对整组图使用同一个 IP。
- `legacy-assets/` 仅用于授权、审计和迁移背景，不作为主动视觉参考。

## 工作流

### 1. 判断任务类型

- 用户说“自动选择 / 给这篇文章配图 / 混合 IP 配图”：按 `shot-routing-rules.md` 为每个配图点路由。
- 用户明确说“用页工 / threadsmith / 洞探”：直接进入对应工作流。
- 用户说“只做规划 / shot list”：输出配图策略，不调用图像生成。
- 用户说“生成 / 输出 / 做图”：每张图单独生成，不要拼图。
- 用户说“设计一个新 IP / 新领域 IP / 定制 IP 工作流”：进入 `custom-ip-workflow.md`。

### 2. 消化正文

先读用户给的正文、链接、Markdown、Notion 内容、截图或主题。提炼：

- 核心观点是什么
- 哪些段落承担认知转折
- 哪些内容适合用图解释
- 哪些地方只适合文字，不需要图

不要平均配图。优先选择认知锚点，例如：核心判断、输入输出闭环、分流、前后对比、承接路径、常见坑、角色状态变化。

### 3. 生成 shot list 并逐图选择 IP

如果用户指定整篇统一 IP，尊重指定。否则先把文章拆成多个配图点，再按 `references/shot-routing-rules.md` 为每个 shot 单独选择 IP，并写明选择理由。

同一篇文章可以出现多个 IP；同一张图不能混用多个 IP。无法判断某张图时默认 `pageworker`。

### 4. 单图单 IP 生成

为每张图进入它被选中的 `workflows/<ip>/`，使用该目录自己的角色定义、构图规则、prompt 模板和 QA。每张图只讲一个核心结构。

提示词必须包含：

- 16:9 横版中文正文配图
- 纯白背景
- 黑色手绘线稿
- 少量红色/橙色/蓝色中文手写批注
- 大量留白
- 当前 IP 作为核心动作主体
- 禁止 PPT、商业插画、幼稚可爱、复杂架构、左上角类型标题

### 5. 保存交付

如果用户在 workspace 内工作，把最终图复制到：

```text
assets/<article-slug>-illustrations/
```

按顺序命名：

```text
01-topic-name.png
02-topic-name.png
```

保留原始生成文件，不要覆盖已有资产，除非用户明确要求替换。

## 输出口径

生成前策略输出要短而准。生成后的交付包含：

- 每张图选择了哪个 IP，以及一句选择理由
- 生成了几张
- 每张图的用途
- 保存路径
- 哪些图最稳，哪些图是可选

不要长篇解释风格理论；让图自己说话。
