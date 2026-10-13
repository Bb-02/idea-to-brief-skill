# Contributor guidance

This repository distributes `skills/idea-to-brief/` as one self-contained Agent Skill. Repository documentation supports contributors and users; installed instructions must not depend on files outside that folder.

- Preserve the user's real goal, accepted constraints, and latest revisions. Distinguish a proposed solution from the goal and a suggestion from an approved requirement.
- The primary deliverable is a self-contained Brief / Prompt for the current or another AI. Research-dependent requirement clarification supports that artifact. Clear factual requests and explicit execution requests retain their normal workflow.
- Size clarification by understanding gaps, evidence gaps, and consequences. Do not equate large resource budgets with long plans, more documents, or deep research.
- Produce a usable draft when context is sufficient. Ask only about material gaps; do not require confirmation before generating a brief. Revision or approval of its wording does not automatically request downstream execution.
- Separate brief generation from the research it describes. Check a premise only as needed to draft responsibly; encode substantive investigation as work for the executor. Execute afterward only when explicitly requested.
- Ground corrections in evidence and project context. Neither novice wording nor existing architecture proves a technical choice wrong or right.
- Keep examples illustrative. Do not make fixed agent counts, stages, report counts, red-team procedures, or client-specific tools universal requirements.
- Maintain one canonical instruction entrypoint. Optional resources must have clear read conditions. Keep the root and packaged MIT license texts identical.
- Never publish source conversations, private project details, personal local paths, credentials, or raw debugging logs.
- Use Chinese commit messages. Prior publishing intent alone does not authorize republishing after withdrawal; follow the user's current publishing instructions. This revision is local until the user asks to publish it.

For changes, check frontmatter and metadata, relative links, package completeness, and staged content. Run relevant cases in `tests/cases.md` when behavior changes. Record the actual setup and results; handcrafted examples are not execution evidence. Installation discovery, copied files, native client loading, automatic selection, and downstream execution are different checks.
