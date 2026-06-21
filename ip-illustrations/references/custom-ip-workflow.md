# IP 定制工作流

## 目标

当用户想为新领域、新人设或新内容类型设计 IP 时，输出一个可直接落到 `workflows/<ip>/` 的 Markdown 规格包。默认只输出文本规格，不生成参考图。

## 输入信息

尽量从用户描述中提取这些字段；缺失时用合理默认值，不要为了小缺口反复追问：

- IP 名称
- 英文 slug
- 适用领域
- 不适用领域
- 角色外形和识别点
- 性格和动作气质
- 常用动作库
- 道具库
- 构图偏好
- 禁止画法
- prompt 片段
- QA 标准
- 路由关键词建议

## 输出文件规格

为新 IP 生成 4 个 Markdown 文件内容：

```text
workflows/<slug>/
├── ip.md
├── composition.md
├── prompt-template.md
└── qa.md
```

## 设计原则

- 新 IP 必须和已有 IP 有明确差异。
- 新 IP 必须适配全局风格 DNA：白底、手绘、少字、留白、红橙蓝克制批注。
- 新 IP 的识别点不超过 3 个，避免难以稳定生成。
- 新 IP 的动作库必须服务它的领域，不要只做装饰动作。
- 新 IP 的禁忌要写清楚，尤其是容易和已有 IP 混淆的地方。
- 新 IP 默认不加入 `ip-router.md`，除非用户明确要求纳入内置路由。

## 输出格式

先给一段简短说明：

```text
为你设计的新 IP：<中文名> / <English Name>
建议 slug：<slug>
适用领域：...
```

然后分别输出 `ip.md`、`composition.md`、`prompt-template.md`、`qa.md` 的完整 Markdown 内容。
