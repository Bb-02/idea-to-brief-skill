# Idea to Brief · 想法成案

[简体中文](README.md) | **English**

**Turn rough ideas into well-organized research.**

You have a question, an early idea, or a hunch that something might work. You are not yet sure what to investigate—or what kind of answer would actually help.

Idea to Brief helps an AI work with that uncertainty: understand the goal, examine assumptions, add useful angles, choose sources and methods, and deliver something you can use to decide or act.

**Need to shape the task? Get a brief. Need the answer? Get an investigation.**

An Agent Skill for turning rough ideas into actionable research tasks and evidence-based answers.

[See a user test](#user-test-one-request-parallel-research) · [Two ways to use it](#a-task-or-an-answer) · [Install](#install) · [Validation record](tests/results.md)

## User test: one request, parallel research

A user tested Qwen in ZCode with this Skill installed. **Their entire request was:**

> People often sign up for our book club and then don't show up. I think people just don't value free events; charging a little should fix it. Please investigate how others handle this and give me some evidence-based approaches we could try.

According to the user's test report, **the AI then automatically launched three subagents to research in parallel**. The user did not write the research instructions below; the AI generated and assigned them. The user supplied two of those prompts, both reproduced in full below as English translations. The [Chinese README](README.md#实测一句话启动并行调查) preserves the original wording.

<details open>
<summary><strong>Subagent 1: research evidence, charging fees, and alternative mechanisms — full translation</strong></summary>

> You are a researcher. Use WebSearch and WebFetch to retrieve primary sources (do not fabricate from memory; every conclusion must include a source URL and an approximate year).
>
> Background: a volunteer-run, free book club frequently has registered participants fail to show up (no-shows). The organizer suspects that "charging a fee will solve it." We need to test and expand on this hypothesis.
>
> Investigate the following questions, focusing on conclusions **supported by research or data**:
>
> 1. Differences in no-show rates between free and paid events: are there industry statistics, such as no-show data published by Eventbrite, Meetup, or event-management platforms? What are the approximate figures?
> 2. Behavioral economics / psychology explanations: sunk costs, pain of paying, and commitment devices—what mechanisms explain fees reducing no-shows? Are there classic experiments? For example, the "deposits / small financial incentives reducing appointment no-shows" experiment published by Volpp and colleagues in journals such as NEJM (the milk-deposit study): verify its design, figures, and conclusions.
> 3. Side effects of charging: can fees discourage registration or change the composition of participants? Is there evidence?
> 4. Mechanisms that are equally effective without charging: appointment-confirmation reminders (especially studies of SMS reminders in medical appointments, with quantified reductions in no-show rates), refundable deposits (returned on arrival), public commitments, waitlists, social norms / peer pressure, check-in systems, and penalties for habitual absence (such as a three-cancellation rule)—find empirical evidence or reliable practical sources for each.
> 5. Is there evidence that "refundable deposits" outperform "direct fees"?
>
> Requirements:
>
> - Search using both English and Chinese keywords, such as "no-show rate free vs paid events", "commitment device reduce no-show", "appointment reminder SMS reduce no-show percentage", and "金钱激励 爽约 预约".
> - For each conclusion, provide the source title, URL, year, and whether it is peer-reviewed research, an industry report, or practitioner experience (distinguish the levels).
> - Clearly distinguish "supported by evidence", "conflicting evidence", and "just a claim".
> - If you cannot find something, say so. Do not invent numbers.
>
> Output: a Chinese research report with structured findings, each accompanied by its source.

</details>

<details>
<summary><strong>Subagent 2: community practice, platform features, and negative experiences — full translation</strong></summary>

> You are a researcher. Use WebSearch and WebFetch to investigate **real community organizers' practical experiences** (do not fabricate from memory; include source URLs for conclusions).
>
> Background: a free book club (a few dozen people, run by volunteers, meeting offline or in a hybrid online/offline format) frequently has registered participants fail to show up. We want to know what other club, community, and Meetup organizers actually do about "signing up but not attending," and how well those approaches work.
>
> Investigate:
>
> 1. Posts on Reddit (r/Meetup, r/community, r/nonprofit, etc.), Meetup community forums, and event-operations blogs where organizers discuss "no-show / people don't show up": which approaches do they report as effective? Which have been shown not to work? Pay particular attention to firsthand accounts ("we tried X, and the result was...").
> 2. Built-in mechanisms on Meetup / Eventbrite / Luma / Huodongxing (活动行) / Hudongba (互动吧): RSVP management, deposits, waitlists, automatic reminders, and no-show marking / disqualification features—how are they used, and what do platform documents say?
> 3. Specific practices and the feedback they have received:
>    - Charging a nominal fee (even RMB 1–5) or a deposit refunded on arrival
>    - Requiring attendees to "confirm participation" 24 hours before the event; treating non-confirmation as cancellation and releasing the place to someone on the waitlist
>    - Blocking or restricting registration after three no-shows
>    - Registration deadlines + attendance caps + waitlists
>    - WeChat group sign-up chains / registration lists, check-in sheets, and photo records
>    - Small, stable groups whose members know each other, to increase motivation to attend
>    - Actual attendance rates in paid communities, such as paid book clubs, and accounts from organizers who switched from free to paid events
> 4. Are there negative experiences: cases where fees or deposits caused a sharp drop in registrations, worsened the atmosphere, or were difficult for volunteers to administer?
>
> Suggested searches: English terms such as "meetup organizer how to reduce no-shows reddit", "eventbrite deposit no show", and "how to stop people from flaking on your meetup"; Chinese terms such as "读书会 报名 爽约 押金" and "活动 鸽子 怎么办 社群".
>
> Requirements: for each practice, identify its source and source type (official platform documentation / a practitioner's firsthand post / an operations article). Where figures are available, reproduce them; where quantitative data cannot be found, state that it is anecdotal experience. Do not fabricate.
>
> Output: a structured report in Chinese: effective practices (ranked by strength of evidence), ineffective or risky practices, and a source list.

</details>

One everyday request expanded into **hypothesis checks, alternative approaches, source selection, concrete search terms, evidence requirements, and deliverables**. This is the kind of research organization Idea to Brief is designed to help an AI do.

<sub>The user supplied and authorized publication of this case. These are task assignments, not final research findings. The added background and specific research leads in the originals still require verification. Three parallel agents were a choice in this run, not a fixed Skill requirement. Tool names and available capabilities depend on the host.</sub>

For more task-design examples, see [solo-project discovery, promotion research, and game-engine research](examples.md) (Chinese).

## What it adds to the way an AI works

- **Turn intuition into researchable questions.** Separate the goal, the proposed solution, and untested explanations, so evidence can change the initial judgment.
- **Add angles you may not have considered.** Examine alternatives, hidden costs, conditions, and important risks. Each addition should serve your purpose.
- **Match sources to the question.** Use official documents for capabilities, appropriate research for effects, and firsthand experience for practical details. Explain what the material supports and what it does not establish.
- **Make the next step clear.** Deliver an executable task or evidence-based comparisons and recommendations that help you decide what to do next.

Use your own words. You do not need to know the field's terminology or write a complex research prompt first.

## A task, or an answer?

The same research methods support two different deliverables.

| | Task design | Direct research |
| --- | --- | --- |
| You want to… | Organize an idea, write a prompt, or hand a task to another AI | Search, investigate, compare, and get findings now |
| The AI does… | Define the goal, scope, questions, methods, and deliverable | Organize the investigation internally, then retrieve, screen, and check sources with available tools |
| You receive… | A complete, copyable, self-contained task description | Findings, sources, applicable conditions, and useful next steps |
| Where it stops | After delivering the task description by default | After the requested investigation, without requiring a visible brief first |

For example, take the same question about learning:

**Help me design the task**

> I can follow a tutorial, but I get stuck when the problem changes. I want to understand how to adjust my learning methods. Turn this into a research task I can give directly to another AI.

**Investigate it for me**

> I can follow a tutorial, but I get stuck when the problem changes. Look into relevant research and tell me how I could adjust my learning methods, with the evidence behind your recommendations.

When there is enough information, work begins on the requested deliverable. Questions are reserved for gaps that would materially change the task. Explicit requests for a prompt, a short answer, or another format take priority.

After receiving a task description, you can say "This is too complicated; give me a complete, simpler version" or "Now carry out this investigation." Saying "Looks good" does not automatically start downstream execution.

## Go deeper when useful. Keep it small when enough.

| What you need | Appropriate effort |
| --- | --- |
| Find projects, tools, or inspiration | Cover different directions, check basic facts, screen and deduplicate, then return a short list with sources |
| Investigate a practice or compare options | Find concrete evidence, conditions, and costs; turn them into actionable recommendations |
| Study a complex question in depth | Use independent inquiry, verification of important claims, counterexamples, and staged synthesis as needed |

A broad question can use shallow checks. A narrow question can deserve deep verification. More tokens or time do not require more reports or exhausting the available resources.

Complex investigations can run in parallel when the host permits it and the work benefits. **Multiple agents are optional**, with no fixed roles or concurrency count. The questions still need to be useful, the evidence reliable, and the results reconciled.

Your examples are clues unless you make them boundaries. "That was just an example," "remove the old limit," and "keep this simpler" should change the work. Assumptions added by the AI should remain distinct from your accepted requirements.

## Install

Stable release: **v1.0.0** · [Browse this version](https://github.com/Bb-02/idea-to-brief-skill/tree/v1.0.0) · [Download source ZIP](https://github.com/Bb-02/idea-to-brief-skill/archive/refs/tags/v1.0.0.zip)

Install from GitHub with the [Skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add Bb-02/idea-to-brief-skill --skill idea-to-brief
```

For example, copy it into a Codex project:

```bash
npx skills add Bb-02/idea-to-brief-skill --skill idea-to-brief --agent codex --copy
```

Installation is project-scoped by default; add `--global` for a global install. You can also copy the entire `skills/idea-to-brief/` folder into your client's designated Skill directory, including references, metadata, and the license. Updating the source folder does not update a separately installed copy automatically.

If you have cloned the repository, you can install locally with `npx skills add . --skill idea-to-brief` from its root.

## Start using it

In a host that supports explicit skill invocation:

```text
$idea-to-brief I want to research how solo developers promote their work, but I don't know which channels to examine. Help me turn this into a practical research task.
```

Or ask for findings directly:

```text
$idea-to-brief Investigate how solo developers promote their work. Give me a comparison of channels grounded in real cases and a starting plan that one person can manage.
```

Automatic selection depends on the model and client. This Skill fits tasks that benefit from organizing scope, sources, comparison criteria, or evidence. Routine factual questions, single lookups, everyday planning, and ordinary development keep their normal workflow. "This might be useful someday" does not by itself require a full investigation.

Outputs use natural language appropriate to the user. Short tasks can be completed in chat without a uniform long template or extra files.

## What the method depends on

Browsing, file access, experiments, and subagents are provided by the host. Idea to Brief guides how an AI organizes the work; the result still depends on the model, tools, available material, and actual verification.

In task design, preliminary checks should stay proportionate to drafting responsibly. In direct research, findings should trace back to sources actually examined. Unavailable tools, missing evidence, and unsuccessful searches should be reported honestly. Temporary failures get bounded retries; persistent gaps stay visible. A research request does not itself authorize posting, deployment, or changes to external systems.

## Validation

Local validation has covered paired "write a prompt / perform an online investigation" requests, analysis of supplied material, mode switches across turns, unavailable capabilities, and simple questions. The [validation record](tests/results.md) documents the setup, observations, and untested areas (Chinese).

Try the [test cases](tests/cases.md) in your own environment (Chinese). Record loading, automatic selection, deliverable fit, and research reliability separately. One successful invocation does not establish consistent behavior across all questions and models.

## Help improve it

Useful feedback starts with a minimal case you can share publicly:

- Which rough question became a worthwhile investigation?
- Which important assumption went unchecked, or which extra angle should have been left out?
- When did the task need more depth, and when did it become too elaborate?

Runtime instructions live in [SKILL.md](skills/idea-to-brief/SKILL.md), with supporting references distributed inside the skill folder. See [AGENTS.md](AGENTS.md) for contributor guidance. Commit messages are in Chinese.

License: [MIT](LICENSE).
