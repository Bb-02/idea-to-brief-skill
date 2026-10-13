---
name: idea-to-brief
description: Create and revise self-contained research briefs and prompts from rough, fragmented, or immature ideas, including requests with unverified assumptions or proposed solutions. Use when shaping search, practical investigation, deep research, or research needed before development into a task that the current or another AI can execute. Deliver a usable draft when context is sufficient; ask only about gaps that materially change the task. Do not redirect clear factual questions or explicit execution requests into prompt writing.
license: MIT
metadata:
  version: "0.2.1"
---

# Idea to Brief

Turn the user's rough ideas into a high-quality, self-contained task description: a Brief or Prompt with a clear purpose, appropriate scope, useful methods, and concrete deliverables. The user can use it with the current AI or give it to another one. This artifact is the primary deliverable.

Default to producing a usable draft and revising it from feedback. Do not require approval before writing each brief, and do not begin its downstream search, research, or implementation unless the user explicitly requests that work. Writing a brief and performing the task described in it are separate actions.

## When to use

Use this skill when the user is shaping a research assignment, organizing scattered ideas, or asking for a plan, brief, or prompt. It can help surface useful questions, check uncertain premises, and translate everyday wishes into executable work. A broad topic alone does not authorize a large investigation.

For a clear factual question or an explicit request to execute a bounded task, follow the normal workflow. Do not replace the requested result with a prompt. When this skill is invoked to produce a brief, deliver that artifact even if the eventual executor is unspecified.

## 1. Understand the real purpose

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

## 2. Check key premises

Identify assumptions that could send the task in the wrong direction: an unsupported scientific claim, a guessed cause, an untested audience need, or a tool choice presented as the solution. Turn them into questions to verify rather than building the assignment around them as established facts.

A personal observation is an experience to explain, not automatically a universal claim to refute. Keep your own causal explanations and named biases as hypotheses until supported. Check premises that could change the assignment; do not impose a preliminary debunking section on every task.

Read supplied context first. Do limited preliminary checking only when it is necessary to write a sound brief and permitted by the host. Keep it tied to the uncertain premise; do not carry out the downstream research while preparing its instructions. If the premise cannot be checked now, state its status and give the executor a concrete verification step or a conditional route.

Ask the user only when missing information would materially change the purpose, scope, or deliverable and cannot be resolved from context. Otherwise use visible, reasonable assumptions and produce the draft. Avoid generic intake questions and confirmation gates that merely delay a useful brief.

## 3. Add the angles that make the task valuable

Translate the purpose into work another agent can actually do: **what to find, where to look, how to screen or compare it, what needs verification, and what to deliver**. Connect each important question to the user's intended decision or use. Do not stop at a polished restatement or vague instructions such as “research thoroughly.”

Add an angle when it could change the usefulness of the result enough to justify the extra work. For promotion research, this may mean audience access, platform rules, example material, concrete actions, and signals for continuing or stopping. For tool comparisons, it may mean hidden costs or migration constraints. Omit adjacent topics with little value for the current purpose; mark useful but optional extensions as such. Do not automatically add a market study, full product specification, or new deliverables.

## 4. Choose methods and depth

Judge the understanding gap, evidence gap, and consequences of a wrong conclusion. Keep search breadth, research depth, output length, resource budget, and parallelism separate.

For open curiosity without a consequential decision or a request for depth, start with a compact explanatory assignment, relevant sources, and a few informative comparisons. Deepen only uncertainties that could materially change the explanation or its use. Missing project details do not justify a comprehensive study. Preserve explicitly requested depth, but do not invent reading-time targets, report lengths, or extra deliverables to signal rigor.

Distinguish research resources (tokens, time, or available agents) from the user's implementation or purchase budget. If “ample budget” is ambiguous, retain that uncertainty; do not turn it into an accepted willingness to pay for products or services. Use conditional cost comparisons where useful, and ask only if the distinction blocks the brief.

Use the lightest organization that meets the purpose:

| Work requested | Emphasize in the brief |
| --- | --- |
| Simple search or discovery | Useful coverage, varied sources, basic fit and existence checks, deduplication, links, and concise selection reasons. |
| Practical investigation | Relevant comparisons, operating conditions, costs where applicable, specific steps or examples, and checks that support a real decision or action. |
| Deep research | Independent lines of inquiry, conflicting evidence or counterexamples, verification of important claims, selective deep dives, synthesis, and completion criteria as needed. |

These are adaptable treatments, not a mandatory sequence or fixed template. A broad search may remain shallow. A large budget does not override “keep it simple.” Read [research design](references/research-design.md) when selecting methods for practical or deep work; a simple list request may not need it.

In the brief, match evidence to the question: official sources for capabilities, pricing, and rules; suitable research for scientific claims; firsthand accounts for project experience; community discussions for leads and reported problems. Require actual source checks and relevant dates when freshness matters. Do not fabricate current facts while writing the task.

Describe parallelism only when independent work adds value and the environment supports it. Preserve an explicit current global limit, including nested agents, but never invent a universal number. For temporary failures, require bounded retries, reduced concurrency, or a feasible fallback; permissions and missing tools need a changed approach. Such instructions are not a runtime scheduling guarantee.

## 5. Deliver a self-contained task description

Write the usable artifact now when enough context exists. Make its background, purpose, constraints, research work, methods, deliverable, and completion criteria clear to an executor who has not seen this conversation. Use only the parts that matter; a short search may fit in a few paragraphs. Read [brief patterns](references/brief-patterns.md) when a sample format or portability check would help.

- Write in the user's language, with understandable terms and concrete actions. In Chinese, prefer “任务说明”, “研究任务”, or “提示词” as appropriate; do not routinely label the output “Brief / Prompt” or announce the skill's workflow. Keep terminology the user explicitly requests and necessary technical names. Keep the artifact prominent and surrounding explanation short, using ordinary copyable Markdown.
- Include relevant hard constraints, softer preferences, and latest decisions. Treat examples as direction clues unless the user made them boundaries.
- Carry only necessary assumptions and unresolved questions into the artifact itself, not just its preface. Use a visible default or conditional path for relevant non-blocking unknowns; do not fill in unnecessary background or leave an unfilled template.
- Carry necessary context into the brief. Avoid “as discussed above.” Identify required input materials and what to do if the recipient cannot access them.
- Describe required capabilities and honest fallback behavior. Portability does not mean every AI can execute the task; do not assume an unspecified model has browsing, subagents, file access, or document tools.
- Check that the executor can begin, distinguish evidence from recommendations, and recognize when the deliverable is sufficient. Do not force a winner or extra reports when the evidence or task does not support them.

Return the complete task description and end there, without a routine invitation to confirm or start research. The imperative research instructions inside it are addressed to the future executor, not an instruction to begin executing them now. Save a file when requested or useful for the chosen delivery; a chat response is enough for a small task.

## 6. Revise from feedback

Apply the latest feedback to the whole brief. Preserve still-valid requirements, remove revoked limits, and actually simplify methods when the user asks for less complexity. Return a complete usable revision rather than an explanation or isolated patch. If editing an existing file, update the full artifact and briefly surface material changes.

Ask only about consequential unresolved choices. Positive feedback on the brief does not by itself request downstream execution.

## Optional follow-through

If the user explicitly asks the current agent to perform the task, use the latest brief and available host capabilities. Respect existing authorization and clarify only material remaining gaps. Report what was actually completed, source or tool limitations, and unresolved findings. Producing or approving a brief does not authorize unrelated publishing, deployment, messaging, or other external changes.
