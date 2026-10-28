# project-kickoff: context for Claude

## What this project is
A public, open-source Claude Code skill (MIT), `project-kickoff`, that runs requirements
discovery at the start of a new software project, BEFORE any tech stack or system design
discussion. Anyone should be able to install it as a Claude Code plugin or copy it into
~/.claude/skills/. Use the skill-creator skill to draft, test and improve it.

## Public skill requirements
- General: works for beginners and experts, scripts and products, coders and non-coders
- Never assume the builder's context; ask it
- Scale depth to project size; offer a short version and an easy "skip to tech"
- Careful triggering: test should-trigger and should-not-trigger prompts
- Ship as a plugin (.claude-plugin/plugin.json + marketplace.json) with README and LICENSE

## Why it exists
At the start of a new project, it's tempting to jump straight to a tech stack and system
design. But at that point the real need is often still unclear. When the core need, users,
scope, domain rules or data sources only become clear later, they can change the tech
stack and the system design. The result is rework, or a product that solves the wrong
problem.

For example, an idea like "compare book availability across libraries" might turn out to
mean "which of my local libraries can I borrow this print book from soonest?" That narrows
the scope (print only), changes the data needed (per-branch copies, loan rules) and changes
the design.

The skill makes Claude gather and confirm requirements first, so tech decisions rest on a
clear, agreed understanding of the problem.

## Draft content: what Claude needs to know before tech
Only the sections whose answers can change the tech stack or system design.
1. Core need: the problem, who has it, what they do today, what a good result looks like;
   restated in one sentence and confirmed
2. Users and usage: who, how many, which device, how often
3. Domain rules: how the real world works, checked against real sources
4. Data: what's needed, where it comes from, how fresh, whether it's accessible and
   allowed (API / scraping / permission, terms of use, robots.txt, privacy). Check with
   real samples early; this is part of requirements, not tech.
5. Scope: v1 in / out / later
6. Constraints: budget, hosting, timeline, the builder's skills and the project's purpose
Short version: sections 1, 4, 5. Decisions and open questions are logged throughout.
Left out on purpose: output/UX (design phase), quality details like speed and
accessibility (tech phase).

## Draft process rules
- Ask a few questions at a time, in order; don't dump all questions at once
- Restate the core need in one sentence and get confirmation before moving on
- Research and check facts yourself where possible instead of asking the user everything
- Don't propose a tech stack or architecture until the sections are confirmed
- End with docs/requirements.md (user story, scope, domain rules, data sources,
  decisions log), confirmed by the user, before the tech and design discussion

## Planned repo structure
.claude-plugin/plugin.json
.claude-plugin/marketplace.json
skills/project-kickoff/SKILL.md
skills/project-kickoff/references/requirements-template.md
skills/project-kickoff/evals/          (test cases: made-up project ideas)
README.md
LICENSE                                (MIT)
Link skills/project-kickoff into ~/.claude/skills/ so edits take effect immediately.

## Decisions
- Depth: scales to project size (short version for small projects, full for products).
- Trigger: both /project-kickoff and automatically when someone describes a new project
  idea ("I want to build an app that…", "help me plan a new project").
  Should NOT trigger for small scripts, bug fixes, features in existing code, or when
  the user already has a spec. Its first message asks before starting: full / short / skip.

## Open questions to settle first
1. Testing: run 2–3 made-up project ideas with and without the skill, review side by side
   (uses helper agents; ask before running)
   Must include: a user who mentions something casually mid-kickoff (e.g. "it'd be nice if
   other parents could use it too"). Good: asks what they mean. Bad: redesigns the project
   for the public. (Found in a real test, 2026-10-28.)
