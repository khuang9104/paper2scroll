# 论点证据表 / Claim and evidence table

[Code as Policies: Language Model Programs for Embodied Control](https://arxiv.org/html/2209.07753v4) · Jacky Liang 等 / et al. · arXiv v4

[On Agentic Manipulation Policies](https://arxiv.org/html/2611.09892v1) · Chen Chen 等 / et al. · arXiv v1

图中示意与比较图均为原创绘制。数字取自下表所列原文。<br>All diagrams and comparison graphics were drawn for this example. The numbers come from the original sources below.

两篇所选版本均采用 arXiv 永久非独占分发许可。公开分享长图时，原文图片、截图、表格版式和大段文字的复用应核对原许可或其他适用的法律依据。论文权利由原权利人保留。[arXiv 许可与复用说明](https://info.arxiv.org/help/license/reuse.html)<br>Both selected versions use the arXiv perpetual non-exclusive distribution license. Public reuse of paper figures, screenshots, table layouts, or substantial text requires checking the source license or another applicable legal basis. Rights in the papers remain with their rights holders. [arXiv licensing and reuse](https://info.arxiv.org/help/license/reuse.html)

## Code as Policies: Language Model Programs for Embodied Control

| 图中论点 / Claim in the map | 原文定位 / Source | 证据边界 / Scope |
| --- | --- | --- |
| 语言模型可根据示例把新指令写成可执行的机器人策略。<br>A language model can use examples to turn a new instruction into an executable robot policy. | [摘要 / Abstract](https://arxiv.org/html/2209.07753v4#abstract1), [引言 / Introduction](https://arxiv.org/html/2209.07753v4#S1) | 生成的程序依赖可用的感知和动作接口。<br>The generated program depends on the available sensing and action interfaces. |
| 代码把语言和动作连起来，能执行几何计算，并用条件与循环处理观测和反馈。<br>Code connects language to action through geometric computation, conditions, and loops that process observations and feedback. | [方法 / Method](https://arxiv.org/html/2209.07753v4#S3), [反应式控制器 / Reactive controllers](https://arxiv.org/html/2209.07753v4#A0.SS6) | 生成的程序可以处理反馈。图中的回路是机制示意。<br>The generated program can handle feedback. The diagram is an editorial rendering of that mechanism. |
| 模型可递归生成尚未定义的辅助函数。<br>The model can recursively supply undefined helper functions. | [方法 / Method](https://arxiv.org/html/2209.07753v4#S3), [表 II / Table II](https://arxiv.org/html/2209.07753v4#S4.T2) | HumanEval 从 34.9% 到 39.8% 指单次采样的编程题通过率。<br>The change from 34.9% to 39.8% on HumanEval is a single-sample pass rate on coding problems. |
| 仿真长时序任务中，指令和属性均未见过时，生成代码的成功率为 80%，自然语言规划为 64%。<br>For long-horizon simulation tasks with unseen instructions and attributes, generated code achieved 80% and natural-language planning achieved 64%. | [表 III / Table III](https://arxiv.org/html/2209.07753v4#S4.T3) | 每项任务 50 次；两组数字取自同一个任务族和条件。<br>There were 50 trials per task. Both numbers come from the same task family and condition. |
| 实机演示覆盖画图、桌面抓放和移动操作。<br>Robot demonstrations include drawing, tabletop pick-and-place, and mobile manipulation. | [图 2 / Figure 2](https://arxiv.org/html/2209.07753v4#S1.F2), [实验 / Experiments](https://arxiv.org/html/2209.07753v4#S4), [局限 / Limitations](https://arxiv.org/html/2209.07753v4#S5) | 实机演示与表 III 的仿真比较使用各自的设置。<br>The robot demonstrations and the simulation comparison in Table III use separate setups. |

## On Agentic Manipulation Policies

| 图中论点 / Claim in the map | 原文定位 / Source | 证据边界 / Scope |
| --- | --- | --- |
| 通用模型在执行中继续决策，可按新观测或执行结果修订策略。<br>A general-purpose model stays involved during execution and can revise its strategy using new observations or execution results. | [引言 / Introduction](https://arxiv.org/html/2611.09892v1#S1), [讨论 / Discussion](https://arxiv.org/html/2611.09892v1#S3) | 模型可在动作段之间重新规划。<br>The model can replan between motion segments. |
| 模型通过持续的 Python 会话调用感知与运动接口，并接收执行反馈。<br>The model uses a persistent Python session to call sensing and motion interfaces and receive execution feedback. | [图 6 / Figure 6](https://arxiv.org/html/2611.09892v1#S4.F6), [第 4 节 / Section 4](https://arxiv.org/html/2611.09892v1#S4) | 运动由机器人运行时执行；控制流程是编辑示意。<br>The robot runtime executes motions. The control-flow graphic is an editorial schematic. |
| 允许模型请求控制错误恢复时成功 104/108 次，关闭时成功 94/108 次。<br>The policy succeeded in 104 of 108 trials with access to controller-error recovery and 94 of 108 without it. | [表 S1 / Table S1](https://arxiv.org/html/2611.09892v1#S5.T1), [第 4F 节 / Section 4F](https://arxiv.org/html/2611.09892v1#S4.SS6) | 12 项实机任务，每项 9 次。关闭恢复时，一次控制器错误即终止该试验。<br>Twelve real-world tasks had nine trials each. With recovery disabled, a controller error ended the trial. |
| 开启恢复时，成功的实机试验平均耗时 280 秒。模型能在相邻动作段之间调整策略。<br>With recovery enabled, successful real-world trials averaged 280 seconds. The model can revise the strategy between motion segments. | [表 1 / Table 1](https://arxiv.org/html/2611.09892v1#S2.T1), [展望 / Outlook](https://arxiv.org/html/2611.09892v1#S3.SS2) | 耗时统计限于该组成功试验。一次轨迹执行中，模型无法修改该段轨迹。<br>The average covers successful trials in that condition. The model cannot revise a trajectory while it is executing. |

## 综合分析 / Synthesis

| 并读发现 / Reading across both papers | 原文定位 / Source | 证据边界 / Scope |
| --- | --- | --- |
| 第二篇在引言中把第一篇归入执行前程序合成。<br>The second paper cites the first as an example of program synthesis before execution. | [第二篇引言 / Second paper introduction](https://arxiv.org/html/2611.09892v1#S1.p2.1) · [参考文献 9 / Reference 9](https://arxiv.org/html/2611.09892v1#bib.bib9) | 这是第二篇作者的分类。第一篇所生成的程序本身可以有反馈回路。<br>This is the later authors’ classification. The earlier paper can generate programs with feedback loops. |
| 将能写成规则的反应交给程序，将需要结合新情况重新判断的决策交给模型，是两篇并读得到的设计思路。<br>The two papers suggest a design option: delegate well-specified reactions to code and involve the model when new evidence calls for reconsidering the plan. | [第一篇方法 / First paper method](https://arxiv.org/html/2209.07753v4#S3) · [第二篇图 6 / Second paper Figure 6](https://arxiv.org/html/2611.09892v1#S4.F6) | 编辑综合。两篇评测的任务与协议不同，需统一条件才能直接比较两种策略。<br>Editorial synthesis. A direct comparison would require matching the tasks and evaluation protocols. |
| 固定设备、任务和预算，给两种反馈设计相同的异常，记录恢复成功率和耗时。<br>Hold hardware, tasks, and budget fixed, expose both feedback designs to the same failures, and measure recovery and elapsed time. | [第一篇方法 / First paper method](https://arxiv.org/html/2209.07753v4#S3) · [第二篇表 S1 / Second paper Table S1](https://arxiv.org/html/2611.09892v1#S5.T1) | 待验证的实验设计。表 S1 比较的是能否请求控制器错误恢复。<br>Proposed test. Table S1 compares access to controller-error recovery. |
