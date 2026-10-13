# Brief patterns

Use these as adaptable examples for the primary deliverable: a self-contained task description. Match the user's language; Chinese output can simply use “任务说明”, “研究任务”, or “提示词”, without a fixed label. The research instructions are for the recipient; drafting them does not mean running the research now.

## Short search prompt

Useful for a small discovery or comparison task:

> 请搜索值得尝试的开源桌面工具，帮助我扩大日常工具的选择范围。未限定平台，先覆盖 Windows、macOS 和 Linux 并标明支持情况；按用途寻找不同类别，核实项目存在和基本维护情况，去重后给出用途、使用门槛、主要限制及来源链接。优先选择容易上手的产品。交付一份简短分类清单，只做基础筛选，不展开商业分析或多轮审查。

This example makes a workable coverage assumption visible. If the user specified Windows, preserve that boundary instead. Ask a platform question only when it would materially alter the value of this particular task; do not require it before every discovery brief.

## A premise that needs checking

Useful when a proposed means may not solve the actual problem:

> 请调查订单接口响应慢的原因，目标是提高响应速度，同时保留订单可靠保存和避免重复扣库存的要求。更换数据库只是待验证方案。先读取项目接口、数据读写方式、既有架构和性能记录；缺少测量时，先给最小测量方案，不能把猜测当成瓶颈结论。必要时查当前技术文档，比较改进选项的收益、代价与验证办法。交付有依据的诊断或下一步测量建议，以及可理解的方案比较；本任务不修改实现。执行前需提供相关项目资料，无法访问时明确列出缺失材料。

The brief gives the executor a way to test the premise without presuming a replacement. Check available context while drafting if needed; put substantial diagnostic work into the task instead of performing it under the guise of writing instructions.

## Fuller research plan

Use a structure like this when the user wants a substantial learning assignment with several important questions or tradeoffs. Casual interest alone does not require it. Include only useful sections:

```markdown
# 移动端 UI 研究计划

## 目的
建立判断移动界面为什么好看、好用，以及哪些设计适合迁移到自己项目的能力。

## 重点问题
- 布局、导航和操作反馈怎样影响使用？
- 新颖交互在什么条件下有价值，什么时候增加负担？
- 哪些案例能形成可复用的判断依据？

## 范围与假设
研究移动端。用户提到的炫彩效果与系统交互作为线索。
先覆盖成熟原则与不同用途的案例；未指定平台时兼顾 Android 与 iOS，并分别标明适用条件。

## 方法与依据
结合平台官方设计资料、真实产品案例和可获得的使用证据。
区分官方建议、用户体验记录和分析判断；对无法确认的信息注明限制。

## 交付与完成标准
给出便于使用的判断清单、案例对照和适用条件。
每项关键建议有理由或证据，并能帮助判断一个实际界面。
资料不足的点明确保留，不为凑原则数量制造结论。
```

This is one possible format for a learning-oriented task, not a required template. Practical investigation may work better as a comparison and action request; simple search may need only paragraphs. Do not predetermine a fixed number of questions, sources, agents, or documents.

## Revision and continuation

When the user says “只做简单搜索，保留 Windows，取消之前的两个并发限制”:

> 请搜索值得尝试的 Windows 开源应用，按用途整理简短清单。核实项目存在、Windows 支持和基本可用性，去重并给出来源链接、使用门槛与简短建议。只做基础筛选，省略深入商业分析、红队和多轮审查；如采用并行，遵守当前执行环境能力，不设额外固定并发数。

Return the complete revised prompt. A cancellation of one limit leaves other constraints in effect. Neither asking for a revision nor approving its wording requests downstream execution.

## Portability check

Keep the current goal, accepted constraints, chosen scope, deliverables, completion criteria, and material uncertainties together. For research before development, distinguish the investigation requested from any later implementation.

Every brief should include enough context for an agent to execute without this conversation. Describe required capabilities and honest fallback behavior, rather than assuming a named model has browsing, subagents, or document tools.

A portable brief should carry the necessary background, current goal, hard constraints and softer preferences, research questions, suitable methods, requested output, and completion criteria. Include only fields that matter to this task. Distinguish accepted choices from unresolved assumptions and tell the executor how to handle non-blocking unknowns. Do not require a pre-execution confirmation for every brief.

If work has already begun, include relevant findings with their sources and outstanding questions, so the recipient can continue. Summarize necessary context directly; identify which supplied materials the recipient needs. Do not use “as discussed above” or rely on files that the recipient cannot access. If essential material is unavailable, state the gap and the action needed to resolve it.

Before handing over, check whether an agent seeing only the brief could understand what to do, what must be preserved, how to judge completion, and what remains uncertain. Keep short tasks short. Exporting a brief does not itself authorize the recipient to publish, deploy, or take other external actions.
