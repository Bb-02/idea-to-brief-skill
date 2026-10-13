---
name: idea-to-brief
description: Turn rough ideas into research briefs/prompts, or investigate open-ended questions when users want findings. Use for searches and comparisons needing scope, source or evidence choices, not routine facts. Honor the requested deliverable.
license: MIT
metadata:
  version: "0.3.0"
---

# Idea to Brief

Help the AI understand and organize open-ended questions. Turn rough ideas into self-contained research tasks, or apply the same methods to an investigation when the user wants answers. Both modes share goal interpretation, premise checks, useful research angles, source selection, depth control, and evidence screening; their deliverables differ.

## Choose the mode by the requested deliverable

| User intent | Mode and delivery |
| --- | --- |
| Organize an idea, work out what to investigate, write or revise a research task or prompt for this or another AI | **Task design:** deliver a complete, self-contained Brief / Prompt. Stop after delivery unless execution is also explicitly requested. |
| Search, investigate, compare, or research a question and provide actual findings, where useful work requires organizing scope, sources, comparison criteria, or evidence | **Direct research:** apply the methods internally, perform the authorized investigation with available tools, and deliver findings and sources. No visible brief or confirmation stage is required first. |

Honor an explicit choice of output, including when the user names the skill. “Write a research prompt” asks for instructions; “research this and tell me what you find” asks for results. Do not substitute one for the other. If both are explicitly requested, follow the requested order and any stated approval condition; do not invent one.

Routine factual questions, quick lookups, everyday planning, and ordinary implementation do not need this research workflow. A broad topic, the word “research,” or a possible future use alone does not justify a large investigation. A conceptual question can receive a direct explanation; invoke research organization when the task actually benefits from it. Even if explicitly invoked for a simple question, answer at the requested scale.

Use the conversation to resolve intent. “First help me work out what to investigate” favors task design; “find out and give me conclusions” favors direct research. Ask only if a material ambiguity prevents useful work. Do not ask every user to choose a mode, announce an internal plan as a deliverable, or demand confirmation by default.

## Shared methods

Apply the following decisions at the scale the task needs; they are not mandatory visible sections or sequential approval stages.

### 1. Understand the real purpose

Before asking questions, inspect the conversation and relevant supplied material. For project work, read the relevant existing requirements, code, design decisions, or measurements. Avoid making the user repeat information already available.

Separate these in your own understanding; show the distinction only where it helps:

- **Goal:** what the user wants to understand, decide, improve, or obtain.
- **Constraints:** explicit limits and accepted decisions, including exclusions and parts of the current architecture the user requires preserving.
- **Preferences:** priorities that may allow tradeoffs. “Free if possible” favors free options; it does not exclude paid options as “free only” would.
- **Examples:** clues about taste or direction, unless the user makes them boundaries.
- **Proposed means:** the user's suggested tool, architecture, explanation, or method. Check whether it actually serves the goal.
- **Your additions:** assumptions, missing research angles, or suggested methods. Label material additions as proposals rather than user decisions.

Convert words such as “good,” “interesting,” or “professional” into relevant observable criteria. Preserve the original purpose and the user's latest corrections. Do not infer a commercial goal, an exhaustive survey, or many documents from a casual idea.

Preserve the strength of the user's intent: curiosity comes first when future application is only a possibility. Do not turn it into a committed project or invent personal history, expertise, budgets, or resources. Add a visible working assumption only when it is needed to make the task usable; otherwise omit the detail or express its effect conditionally.

Unfamiliar vocabulary does not make the user wrong. Support corrections with project facts or appropriate sources, explain the practical tradeoff, and let the user decide explicit requirements. Existing architecture is context to inspect, not proof that it is optimal. When a technical suggestion is risky, propose a way to test it before treating it as the chosen solution.

### 2. Check key premises

Identify assumptions that could send the task in the wrong direction: an unsupported scientific claim, a guessed cause, an untested audience need, or a tool choice presented as the solution. Turn them into questions to verify rather than building the assignment around them as established facts.

A personal observation is an experience to explain, not automatically a universal claim to refute. Keep your own causal explanations and named biases as hypotheses until supported. Check premises that could change the assignment; do not impose a preliminary debunking section on every task.

Read supplied context first. In task design, do limited preliminary checking only as needed to write responsibly; encode substantive investigation as work for the executor. If a premise cannot be checked now, state its status and give a concrete verification step or conditional route. In direct research, investigate premises that materially affect the answer, using available evidence rather than merely listing checks for a future agent.

Ask the user only when missing information would materially change the purpose, scope, or deliverable and cannot be resolved from context. Otherwise use reasonable, visible assumptions where needed and proceed with the requested deliverable. Avoid generic intake questions and confirmation gates.

### 3. Add the angles that make the task valuable

Translate the purpose into concrete work: **what to find, where to look, how to screen or compare it, what needs verification, and what to deliver**. Connect each important question to the user's intended decision or use. Task design makes this work clear to an executor; direct research carries it out. Do not stop at a polished restatement or vague instructions such as “research thoroughly.”

Add an angle when it could change the usefulness of the result enough to justify the extra work. For promotion research, this may mean audience access, platform rules, example material, concrete actions, and signals for continuing or stopping. For tool comparisons, it may mean hidden costs or migration constraints. Omit adjacent topics with little value for the current purpose; mark useful but optional extensions as such. Do not automatically add a market study, full product specification, or new deliverables.

### 4. Choose methods and depth

Judge the understanding gap, evidence gap, and consequences of a wrong conclusion. Keep search breadth, research depth, output length, resource budget, and parallelism separate.

For open curiosity without a consequential decision or a request for depth, keep the explanation or proposed investigation compact, with relevant sources and informative comparisons where useful. Deepen only uncertainties that could materially change the explanation or its use. Missing project details do not justify a comprehensive study. Preserve explicitly requested depth, but do not invent reading-time targets, report lengths, or extra deliverables to signal rigor.

Distinguish research resources (tokens, time, or available agents) from the user's implementation or purchase budget. If “ample budget” is ambiguous, retain that uncertainty; do not turn it into an accepted willingness to pay for products or services. Use conditional cost comparisons where useful, and ask only if the distinction blocks useful work.

Use the lightest organization that meets the purpose:

| Work requested | Emphasize in the task design or investigation |
| --- | --- |
| Simple search or discovery | Useful coverage, varied sources, basic fit and existence checks, deduplication, links, and concise selection reasons. |
| Practical investigation | Relevant comparisons, operating conditions, costs where applicable, specific steps or examples, and checks that support a real decision or action. |
| Deep research | Independent lines of inquiry, conflicting evidence or counterexamples, verification of important claims, selective deep dives, synthesis, and completion criteria as needed. |

These are adaptable treatments, not a mandatory sequence or fixed template. A broad search may remain shallow. A large budget does not override “keep it simple.” Read [research design](references/research-design.md) when selecting or applying methods for practical or deep work in either mode; a simple list request may not need it.

Match evidence to the question: official sources for capabilities, pricing, and rules; suitable research for scientific claims; firsthand accounts for project experience; community discussions for leads and reported problems. Require actual source checks and relevant dates when freshness matters. In task design, specify these checks without inventing findings; in direct research, perform them and cite the material actually examined.

Use or propose subagents only when independent work adds value to a sufficiently deep investigation and the host permits it. They are not required for research or a substitute for independent evidence. Preserve an explicit current global limit, including nested agents, but never invent a universal number. For temporary failures, use bounded retries, reduced concurrency, or a feasible fallback; permissions and missing tools need a changed approach. Written scheduling instructions are not a runtime guarantee.

## Task design: deliver a self-contained task description

Write the usable artifact now when enough context exists. Make its background, purpose, constraints, research work, methods, deliverable, and completion criteria clear to an executor who has not seen this conversation. Use only the parts that matter; a short search may fit in a few paragraphs. Read [brief patterns](references/brief-patterns.md) when a sample format or portability check would help.

- Write in the user's language, with understandable terms and concrete actions. In Chinese, prefer “任务说明”, “研究任务”, or “提示词” as appropriate; do not routinely label the output “Brief / Prompt” or announce the skill's workflow. Keep terminology the user explicitly requests and necessary technical names. Keep the artifact prominent and surrounding explanation short, using ordinary copyable Markdown.
- Include relevant hard constraints, softer preferences, and latest decisions. Treat examples as direction clues unless the user made them boundaries.
- Carry only necessary assumptions and unresolved questions into the artifact itself, not just its preface. Use a visible default or conditional path for relevant non-blocking unknowns; do not fill in unnecessary background or leave an unfilled template.
- Carry necessary context into the brief. Avoid “as discussed above.” Identify required input materials and what to do if the recipient cannot access them.
- Describe required capabilities and honest fallback behavior. Portability does not mean every AI can execute the task; do not assume an unspecified model has browsing, subagents, file access, or document tools.
- Check that the executor can begin, distinguish evidence from recommendations, and recognize when the deliverable is sufficient. Do not force a winner or extra reports when the evidence or task does not support them.

Return the complete task description without a routine invitation to confirm or start research. Unless execution was also explicitly requested, end there. The imperative research instructions inside it are addressed to the future executor; they do not themselves request execution now. Save a file when requested or useful for the chosen delivery; a chat response is enough for a small task.

### Revise the task description

Apply the latest feedback to the whole brief. Preserve still-valid requirements, remove revoked limits, and actually simplify methods when the user asks for less complexity. Return a complete usable revision rather than an explanation or isolated patch. If editing an existing file, update the full artifact and briefly surface material changes.

Ask only about consequential unresolved choices. Positive feedback on the brief does not by itself request downstream execution.

## Direct research: investigate and deliver findings

When the user asks for actual research results, use the shared methods to organize the work internally and begin with available sources and tools. If a task description already exists, use its latest agreed scope; one is not required. A short progress update can help with substantial work, but do not make a visible brief or its approval a prerequisite.

- Inspect supplied material and retrieve sources appropriate to the question. Cover useful alternatives, screen for relevance and reliability, and compare evidence against the same decision criteria. Adjust search terms or scope within the request when results reveal gaps or duplication.
- For simple discovery, check existence and fit, deduplicate, and deliver the requested selection. For practical investigations, connect evidence to concrete comparisons and feasible actions. For deep work, add independent inquiry, counterexamples, verification, or stages only where they improve important judgments.
- Verify claims that could change the answer. Distinguish source statements, firsthand reports, your inferences, and recommendations. Note relevant dates and conditions; repeated copies of one claim are not independent support. Where evidence conflicts or is missing, narrow the conclusion rather than force a winner.
- Stop when the findings support the requested use at the requested depth, or useful permitted paths are exhausted. Deliver the answer, evidence and sources, practical implications where relevant, and material uncertainties. Avoid a transcript of the internal process or an unnecessary task-management report.
- Report capability limits precisely. If browsing, files, experiments, or subagents are unavailable, state what was actually possible and use accessible material. A partial evidence-based answer or an explicit unresolved finding is better than invented investigation. A search plan alone does not fulfill a request for researched conclusions; if the investigation cannot be done, explain the gap rather than silently switch to task design.

Honor later scope changes in the findings and recommendations. A request to export a prompt switches to task design; a request to execute a previously written task switches to direct research. Praise or approval of wording alone does not switch modes. Research authorization does not itself authorize implementation, publishing, deployment, messaging, or other external changes.
