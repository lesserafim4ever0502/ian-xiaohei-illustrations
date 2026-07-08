# Prompt Examples

下面这些 prompt 可以直接复制到 Codex 里使用。

## 混合 IP：只做配图规划

```text
Use $ip-illustrations 先不要生图。
请分析下面这篇文章，逐图选择最合适的 IP，输出 5 张左右的 shot list。
同一篇文章可以使用多个 IP，但同一张图只能使用一个 IP。
每张图写清楚：
- 放在哪个段落后
- 选择的 IP
- 选择理由
- 图的主题
- 核心意思
- 结构类型
- 当前 IP 在图里做什么
- 建议元素
- 建议中文标注词

<粘贴文章>
```

## 混合 IP：文章正文配图

```text
Use $ip-illustrations 把下面这篇文章生成 4 张正文配图。
请为每张图单独选择最合适的 IP，但同一张图不要混用多个角色。
要求：16:9 横版、纯白背景、黑色手绘线稿、少量红橙蓝中文手写批注。

<粘贴文章>
```

## 指定 Pageworker / 页工

```text
Use $ip-illustrations 用 pageworker 工作流，为这篇知识管理文章做配图策略。
重点表现：素材如何从混乱变成可复用卡片。
整篇统一使用 pageworker，先输出 shot list，不要生成图片。

<粘贴文章>
```

## 指定 Threadsmith / 线匠

```text
Use $ip-illustrations 用 threadsmith 工作流，为“把注册用户接到付费转化路径”生成一张正文配图。
不要混用其他 IP。画面要纯白、手绘、少字、怪诞但清爽。
```

## 指定 Holeseeker / 洞探

```text
Use $ip-illustrations 用 holeseeker 工作流，为“为什么这个自动化流程总是在最后一步失败”生成一张诊断配图。
画面表现根因排查，不要画正式故障树。
```

## 定制新 IP 工作流

```text
Use $ip-illustrations 帮我为“学习复盘”领域设计一个新的 IP 工作流。
只输出 Markdown 规格包，不要生图。
这个 IP 要适合错题、复盘、学习路径和薄弱点定位。
```

## 对比不同 IP 效果

```text
Use $ip-illustrations 为同一个观点分别设计 3 个 shot list 方向：
- pageworker
- threadsmith
- holeseeker
只做文字规划，不要把多个 IP 放进同一张图。

观点：一个系统不是靠功能多变强，而是靠关键路径少断点。
```
