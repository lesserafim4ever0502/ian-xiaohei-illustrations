# IP Illustrations / IP 正文配图库

> English: A Codex Skill for choosing one isolated visual IP workflow and turning Chinese articles into clean, strange, hand-drawn explanatory illustrations.
>
> 中文：一个 Codex Skill，用“IP 备选库 + 隔离工作流”的方式，为中文文章生成白底、手绘、怪诞但清爽的正文配图。
>
> 16:9 horizontal / 16:9 横版 | isolated IP workflow / 隔离 IP 工作流 | pure white sketch / 纯白手绘 | sparse Chinese notes / 少量中文批注

---

## What This Is / 这个仓库是什么

English:

IP Illustrations is a multi-IP Codex Skill for Chinese article illustrations. It does not put multiple characters into one image. Instead, it chooses exactly one IP workflow for the current article, then uses that workflow's character, composition rules, prompt template, and QA checklist.

The goal is to keep one consistent visual language while allowing different fields to use different recurring IPs.

中文：

IP Illustrations 是一个多 IP 中文正文配图 Skill。它不是把多个角色放进同一张图，而是根据文章领域和表达任务，从 IP 备选库里选择一个独立工作流，再使用该 IP 自己的角色设定、构图规则、prompt 模板和 QA。

核心目标是：**统一画风，不统一角色；统一调度，不混合工作流。**

---

## Built-in IPs / 内置 IP

### Pageworker / 页工

English: For documents, notes, knowledge management, information structure, and content systems.

中文：适合文档、笔记、知识管理、信息结构、内容系统。形象是折页 / 索引卡式系统操作员。

### Threadsmith / 线匠

English: For paths, workflows, funnels, handoff chains, user journeys, and broken connections.

中文：适合路径、流程、漏斗、承接链路、用户旅程和断点修补。形象是修补路径的线轴工匠。

### Holeseeker / 洞探

English: For debugging, diagnosis, retrospectives, risks, common traps, root causes, and failure modes.

中文：适合 debug、问题诊断、复盘、风险、常见坑、根因和系统失效。形象是排查洞口与裂缝的现场勘探员。

---

## Output / 它会产出什么

Default output / 默认输出：

- 16:9 horizontal article illustrations / 16:9 横版正文配图
- 4-8 image shot lists for one article / 一篇文章的 4-8 张 shot list
- IP selection reason, theme, core idea, structure type, character action, elements, and Chinese label suggestions / IP 选择理由、主题、核心意思、结构类型、角色动作、元素和中文标注建议
- PNG files saved under `assets/<article-slug>-illustrations/` / 最终 PNG 图片保存到 `assets/<article-slug>-illustrations/`
- Markdown specs for custom IP workflows / 新 IP 定制时输出 Markdown 规格包

Default non-output / 默认不输出：

- Multiple IPs inside one image / 一张图里混用多个 IP
- PPTX / PDF / Keynote
- SVG / HTML / Canvas editable diagrams
- Commercial posters or cover key visuals
- Large text-heavy explainers

---

## Visual Style / 视觉风格

English:

- Pure white background, no paper texture, shadow, gradient, or beige tone.
- Thin black hand-drawn line art with slight wobble.
- Lots of empty space; the main subject usually uses 40%-60% of the canvas.
- Sparse red, orange, and blue handwritten Chinese annotations.
- One image explains one core action, structure, state, or metaphor.
- The selected IP must perform the core conceptual action, not decorate the side.
- Strange, clean, memorable, and product-sketch-like; not cute or childish.

中文：

- 纯白背景，不要纸纹、米色、阴影、渐变
- 黑色手绘线稿，细线，轻微抖动
- 大量留白，主体只占画面约 40%-60%
- 少量红色、橙色、蓝色中文手写批注
- 一张图只表达一个核心动作、结构、状态或隐喻
- 被选中的 IP 必须参与核心动作，不能只是装饰
- 怪诞、有创意、清爽，有产品草图感，但不幼稚、不卖萌

---

## Install / 安装

Copy the skill directory into your Codex skills folder / 把 skill 子目录复制到 Codex skills 目录：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./ip-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Use it in Codex / 在 Codex 里使用：

```text
Use $ip-illustrations 为这篇中文文章自动选择合适 IP，并设计 5 张正文配图。
```

---

## Usage / 怎么用

### Auto Select IP / 自动选择 IP

```text
Use $ip-illustrations 先不要生图。
请分析下面这篇文章，自动选择最合适的 IP，输出 5 张左右的 shot list。
每张图写清楚：放在哪段后、选择的 IP、主题、核心意思、结构类型、角色在做什么、建议中文标注词。

<粘贴文章>
```

### Specify One IP / 指定一个 IP

```text
Use $ip-illustrations 用 threadsmith 工作流，为“把注册用户接到付费转化路径”生成一张正文配图。
不要混用其他 IP。画面要纯白、手绘、少字、怪诞但清爽。
```

### Custom IP Workflow / 定制新 IP 工作流

```text
Use $ip-illustrations 帮我为“学习复盘”领域设计一个新的 IP 工作流。
只输出 Markdown 规格包，不要生图。
这个 IP 要适合错题、复盘、学习路径和薄弱点定位。
```

More examples / 更多示例：[`examples/prompts.md`](examples/prompts.md)

---

## Workflow / 工作流程

1. Read the article, Markdown, Notion content, screenshot, or topic. / 读取文章、Markdown、Notion 内容、截图或主题。
2. Determine whether the user wants auto routing, a specified IP, a shot list, generation, editing, or custom IP design. / 判断用户要自动路由、指定 IP、shot list、生成、改图还是定制 IP。
3. Choose one IP workflow from `ip-illustrations/workflows/`. / 从 `ip-illustrations/workflows/` 选择一个 IP 工作流。
4. Read only that selected IP workflow. / 只读取被选中的 IP 工作流。
5. Invent a fresh low-tech physical metaphor. / 重新发明低科技物理隐喻。
6. Make the selected IP perform the core action. / 让被选中的 IP 承担核心动作。
7. Generate each image separately. / 每张图单独生成。
8. Check against the selected IP's QA checklist. / 按所选 IP 的 QA checklist 检查。
9. Save final PNG files and report paths. / 保存 PNG 并报告路径。

---

## Structure / 目录结构

```text
.
├── README.md
├── CHANGELOG.md
├── CHANGE_TRACKING.md
├── LICENSE
├── NOTICE.md
├── examples/
│   └── prompts.md
├── legacy-assets/
│   └── upstream-*/
└── ip-illustrations/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── references/
    │   ├── global-style-dna.md
    │   ├── ip-router.md
    │   ├── output-rules.md
    │   └── custom-ip-workflow.md
    └── workflows/
        ├── pageworker/
        ├── threadsmith/
        └── holeseeker/
```

The directory to install is / 真正需要安装的是：

```text
ip-illustrations/
```

---

## Notes / 注意事项

- One image uses one IP only. / 一张图只使用一个 IP。
- Keep Chinese labels short. / 中文标注越短越稳定。
- The selected IP must be part of the action. / 被选中的 IP 必须参与动作。
- Do not reuse legacy example compositions. / 不复用历史示例构图。
- If text quality is poor, reduce labels first. / 中文错字严重时优先减少标注。
- Legacy upstream assets stay in `legacy-assets/` for audit and attribution only. / 历史上游资产只保留在 `legacy-assets/` 中，用于审计和署名。

---

## License / 许可

MIT License. See [LICENSE](LICENSE).
