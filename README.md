# project-kickoff

A [Claude Code](https://claude.com/claude-code) skill that pins down what you're building,
and why, before anyone picks a tech stack.

> **Status:** first draft, not yet tested. Expect changes.

## Why

At the start of a new project, it's tempting to jump straight to a tech stack and system
design. But the real need is often still unclear. When the core need, users, scope, domain
rules or data sources only become clear later, they can change the tech stack and the
system design, and that means rework.

## What it does

When you describe a new project idea, Claude offers a quick requirements kickoff before
any tech talk:

- **Full**, **short**, or **skip**: you choose how deep to go
- A few questions at a time on the core need, users, domain rules, data, scope and
  constraints
- Claude checks facts itself where it can, including fetching real samples of any data the
  project depends on
- It ends with a `docs/requirements.md` you've confirmed, then moves on to the tech
  discussion

## Install

Copy the skill into your personal Claude Code skills folder:

```sh
git clone https://github.com/xixifish/project-kickoff.git
cp -r project-kickoff/skills/project-kickoff ~/.claude/skills/
```

Then describe a new project idea to Claude Code, or type `/project-kickoff`.

## License

[MIT](LICENSE) © Jing Chen
