# Idea to Brief · 想法成案

[简体中文](README.md) | **English** · [v1.0.0](https://github.com/Bb-02/idea-to-brief-skill/tree/v1.0.0)

**Turn rough ideas into well-organized research.**

An Agent Skill that helps AI organize searches and investigations: identify your real goal, check assumptions, add useful angles, and choose suitable sources and methods.

- **Want to shape the task?** Get a complete research brief or prompt for the current AI or another one. Work stops there by default.
- **Want answers now?** Get an actual investigation with sources, findings, and recommendations.

[Use cases](#when-to-use-it) · [User test](#user-test-one-request-parallel-research) · [Install](#install) · [Use](#use)

## When to use it

| Scenario | Examples | Research focus |
| --- | --- | --- |
| Find resources and inspiration | Independent projects, tools, reference examples | Cover different directions, screen, deduplicate, and check basic facts |
| Investigate practical problems | Event no-shows, promoting a project, comparing options | Find concrete evidence, alternatives, and implementation costs |
| Explore complex questions | Compare game engines, investigate technical approaches | Break down key questions, verify important claims, and seek counterexamples |

Simple searches stay lightweight; complex questions get depth as needed. Routine factual questions do not require a research workflow.

## User test: one request, parallel research

A user tested Qwen in ZCode with this Skill installed. **Their entire request was:**

> People often sign up for our book club and then don't show up. I think people just don't value free events; charging a little should fix it. Please investigate how others handle this and give me some evidence-based approaches we could try.

According to the user's report, **the AI generated task prompts and assigned them to three subagents working in parallel**. Below are full English translations of the two AI-generated prompts the user supplied. The [Chinese README](README.md#实测一句话启动并行调查) preserves the originals.

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

The task expanded from “would charging help?” to **side effects, alternatives, and real-world practice**, with explicit sources, search terms, and evidence requirements.

<sub>These are user-supplied task assignments, not final research findings. Added background and specific research leads still need verification. Agent count depends on the task and host.</sub>

## Install

With the [Skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add Bb-02/idea-to-brief-skill --skill idea-to-brief
```

Add `--agent codex --copy` to copy into a Codex project, or `--global` for a global install.

**Manual install:** [Download the source ZIP](https://github.com/Bb-02/idea-to-brief-skill/archive/refs/tags/v1.0.0.zip) and copy the entire `skills/idea-to-brief/` folder into your client's Skill directory.

## Use

In clients that support `$skill-name` invocation:

**Design a research task:**

```text
$idea-to-brief I want to understand how solo developers promote their work.
Turn this into a research task I can give to another AI.
```

**Get findings directly:**

```text
$idea-to-brief Investigate how solo developers promote their work.
Compare channels using real cases and suggest how to get started.
```

In other clients, select `idea-to-brief` through the skill interface. Automatic selection depends on the model and client. Browsing and subagents are supplied by the host; multiple agents are optional.

---

[Example requests](examples.en.md) · [Skill source](skills/idea-to-brief/SKILL.md) · [MIT](LICENSE)
