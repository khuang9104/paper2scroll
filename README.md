# Paper2Scroll

**Read a research paper in one scroll.**

Paper2Scroll turns research PDFs into vertical infographics that explain the argument, framework, method, and findings. Key claims point back to the paper’s sections, figures, or tables.

[简体中文](README.zh-CN.md) · [See the example](#example) · [Install](#install)

- **One long PNG per paper.** Start with a three-part overview, then see how the method works, what the study found, and where its findings apply.
- **Synthesis for multiple papers.** Get individual maps and one to five comparison maps organized around shared questions, agreements, or disagreements.
- **A claim and evidence table.** Check where a number came from, what was compared, and what the evidence supports.

## Example

**Who decides what a robot does next?** Two public robotics papers show how a generated program can react to sensor data and how a model can also revise a strategy during execution.

[![Two public robotics papers compared. The preview traces feedback through generated code and through a model that can replan during execution.](examples/robot-policies/preview.png)](examples/robot-policies/feedback-synthesis.png)

| Public paper | Output |
| --- | --- |
| [Code as Policies: Language Model Programs for Embodied Control](https://arxiv.org/abs/2209.07753v4) | [Paper infographic](examples/robot-policies/code-as-policies.png) |
| [On Agentic Manipulation Policies](https://arxiv.org/abs/2611.09892v1) | [Paper infographic](examples/robot-policies/agentic-manipulation-policies.png) |
| Where does feedback go? | [Synthesis infographic](examples/robot-policies/feedback-synthesis.png) · [Claim and evidence table](examples/robot-policies/evidence.md) |

## Install

Paper2Scroll is an [Agent Skill](https://agentskills.io/specification). It uses your agent’s document-reading and image-rendering tools. The steps below install it in one Codex project. Run them from that project’s root in a directory with a writable parent.

```bash
git clone https://github.com/khuang9104/paper2scroll.git ../paper2scroll-source
mkdir -p .agents/skills
cp -R ../paper2scroll-source/skills/paper2scroll .agents/skills/
```

<details>
<summary>Windows PowerShell</summary>

```powershell
git clone https://github.com/khuang9104/paper2scroll.git ../paper2scroll-source
New-Item -ItemType Directory -Force -Path .agents/skills | Out-Null
Copy-Item -LiteralPath ../paper2scroll-source/skills/paper2scroll -Destination .agents/skills -Recurse
```

</details>

Open a new session in the project, attach a paper, and ask:

```text
Use $paper2scroll to explain this paper. Show the key comparison and cite the original table.
```

For another Agent Skills-compatible host, copy the entire [skill folder](skills/paper2scroll) into that host’s skill directory. PNG output requires a renderer available to the agent.

## Choose an output language

Edit `.agents/skills/paper2scroll/config.yaml` in your project. [The bundled default](skills/paper2scroll/config.yaml) is `zh-en`.

```yaml
language: de
```

Use `zh` for Simplified Chinese, `en` for English, `zh-en` for Chinese and English together, or a standard language tag such as `de`, `zh-Hant`, or `pt-BR`. The setting applies to the infographics, evidence table, and delivery summary. A language requested in your prompt takes precedence for that run.

## License

[MIT](LICENSE) for this project and its original example graphics. The source papers are linked for reference.
