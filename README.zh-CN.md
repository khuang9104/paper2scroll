# Paper2Scroll · 论文一图流

**一张长图，读懂论文的主张、方法和证据。**

把研究论文 PDF 交给 Paper2Scroll，它会把核心主张、理论框架、研究方法和结果组织成一张纵向长图。关键结论标注原文章节、图号或表号，方便回查。

[English](README.md) · [看样例](#样例) · [安装](#安装)

- **每篇一张长图。** 三项导读搭起主线，随后展开方法、结果、关键对照和局限。
- **多篇一起读。** 保留逐篇长图，再按共同问题、证据异同生成 1–5 张综合图。
- **附论点证据表。** 回原文核对数字、比较条件和结论范围。

## 样例

**谁决定机器人的下一步？** 两篇公开论文分别展示了生成的程序如何根据观测作出反应，以及语言模型如何在执行中重新决定策略。

[![两篇公开机器人论文的综合预览。对比生成程序如何处理反馈，以及模型如何在执行过程中调整策略。](examples/robot-policies/preview.png)](examples/robot-policies/feedback-synthesis.png)

| 公开论文 | 生成结果 |
| --- | --- |
| [Code as Policies: Language Model Programs for Embodied Control](https://arxiv.org/abs/2209.07753v4) | [独立长图](examples/robot-policies/code-as-policies.png) |
| [On Agentic Manipulation Policies](https://arxiv.org/abs/2611.09892v1) | [独立长图](examples/robot-policies/agentic-manipulation-policies.png) |
| 两篇并读：反馈交给谁？ | [综合长图](examples/robot-policies/feedback-synthesis.png) · [论点证据表](examples/robot-policies/evidence.md) |

## 安装

直接把这句话发给 Codex 或 Claude Code：

```text
请从 https://github.com/khuang9104/paper2scroll/tree/main/skills/paper2scroll 安装 paper2scroll 技能，供当前 Agent 使用。
```

也可以在项目终端用 [Skills CLI](https://github.com/vercel-labs/skills) 安装，需要 Node.js 22.20 或更新版本：

```bash
npx skills add khuang9104/paper2scroll --skill paper2scroll
```

加 `-a codex` 或 `-a claude-code` 指定宿主，加 `-g` 安装为跨项目可用。

附上论文后，输入「用 Paper2Scroll 帮我读这篇论文，用中文输出」。Codex 里也可用 `$paper2scroll`，Claude Code 里可用 `/paper2scroll` 显式调用。如果安装后还未显示技能，新开一次会话即可。

Paper2Scroll 使用宿主提供的论文读取和图像渲染能力，导出 PNG 需要有可用的渲染工具。

## 设置输出语言

编辑已安装技能目录里的 `config.yaml`，也可以直接让 Agent 帮你修改。[初始配置](skills/paper2scroll/config.yaml)是 `zh-en`。

```yaml
language: de
```

`zh` 是简体中文，`en` 是英文，`zh-en` 是中英双语。也可以填 `de`（德语）、`zh-Hant`（繁体中文）、`pt-BR`（巴西葡萄牙语）等标准语言标签。配置应用于长图、证据表和交付说明。本次请求明确指定语言时，以本次请求为准。

## 许可

[MIT](LICENSE) 适用于贡献者有权授权的项目内容。样例采用自行撰写的解读文字和重新绘制的示意图、数据图。论文及其他第三方材料保留各自的权利和许可，详见[样例来源与复用说明](examples/robot-policies/evidence.md)。
