# Requirements document template

Use this structure for `docs/requirements.md` at the end of a kickoff.

- Include only the sections that were covered. A short kickoff gives core need, data,
  scope, decisions log and open questions.
- Write in plain language the user would recognize. No stack or architecture, except tech
  preferences the user stated.
- Give a source for each domain rule and data check (a link, or "from the user"), so they
  can be checked again later.
- Replace every placeholder in [brackets] and drop any line that doesn't apply.

````markdown
# Requirements: [project name]

Last updated: [date] · Kickoff: [full / short]

## Core need

[The one-sentence core need, as the user confirmed it.]

- **Problem:** [what goes wrong today]
- **For:** [who has the problem]
- **Today they:** [their current workaround]
- **A good result looks like:** [one real situation and what the user would get]

## Users and usage

- **Who:** [types of users]
- **How many:** [just me / a few friends / the public / a team of N]
- **Device:** [phone, laptop, both]
- **How often:** [daily, weekly, once in a while]

## Domain rules

- [Rule or exception]. Source: [link / from the user]

## Data

| Data | Source | Access | Allowed to use? | Checked with a real sample? |
|------|--------|--------|-----------------|-----------------------------|
| [what] | [where from] | [API / open dataset / scraping / manual / needs permission] | [terms of use, robots.txt, privacy notes] | [yes: what it showed / not yet] |

**How fresh it needs to be:** [live / daily / rarely changes]

## Scope

- **In v1:** [features that serve the core need]
- **Out:** [things it won't do]
- **Later:** [ideas parked for after v1]

## Constraints

- **Budget:** [free only / small monthly cost / no limit]
- **Hosting:** [where it will run, if known]
- **Timeline:** [deadline or "none"]
- **Skills and purpose:** [what the builder knows; learning / portfolio / personal / product]
- **Tech preferences:** [only if the user stated any]

## Decisions log

| Date | Decision | Reason |
|------|----------|--------|
| [date] | [what was decided] | [why] |

## Open questions

- [ ] [question still to answer, and who or what can answer it]
````
