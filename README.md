# Heartbeat Templates

[![License](https://img.shields.io/badge/License-GPLv3-green.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Built%20for-Claude%20Code-orange.svg)](https://claude.ai/code)
[![TinMan](https://img.shields.io/badge/Works%20with-TinMan-blue.svg)](https://github.com/andyuninvited/tinman_for_claudecode)

> Community templates for [TinMan](https://github.com/andyuninvited/tinman_for_claudecode) — the heartbeat scheduler for Claude Code.

Drop any of these into your project as `HEARTBEAT.md` and TinMan will run it on a schedule. Edit freely — these are starting points, not rules.

---

## Part of the Claude Code Toolkit

| Tool | Role | Link |
|------|------|------|
| **TinMan** | The heart — runs these templates on a schedule | [tinman_for_claudecode](https://github.com/andyuninvited/tinman_for_claudecode) |
| **C3Poh** | The voice — sends alerts to your phone | [c3poh_for_claudecode](https://github.com/andyuninvited/c3poh_for_claudecode) |
| **Agent Blueprints** | The brains — starter agent templates | [agent-blueprints](https://github.com/andyuninvited/agent-blueprints) |

---

## Templates

| # | Template | Best for | Interval |
|---|----------|----------|----------|
| [01](templates/01-solo-dev.md) | **Solo Dev** | Personal projects, side projects | 30 min |
| [02](templates/02-startup-team.md) | **Startup Team** | Fast-moving team codebases | 30 min |
| [03](templates/03-ai-project.md) | **AI Project** | Claude/OpenAI/Supabase projects, API key hygiene | 30 min |
| [04](templates/04-content-creator.md) | **Content Creator** | Writers and newsletter authors, no code jargon | 60 min |
| [05](templates/05-open-source-maintainer.md) | **OSS Maintainer** | Public repos with issues, PRs, CI | 60 min |
| [06](templates/06-security-paranoid.md) | **Security Paranoid** | High-stakes projects, PII, payments, auth | 15 min |
| [07](templates/07-mobile-app-dev.md) | **Mobile App Dev** | iOS/Android/Capacitor/React Native | 30 min |
| [08](templates/08-data-pipeline.md) | **Data Pipeline** | ETL jobs, batch processing, database workflows | 15 min |

---

## How to use

**1. Pick a template and copy it:**
```bash
curl -o HEARTBEAT.md https://raw.githubusercontent.com/andyuninvited/heartbeat-templates/main/templates/01-solo-dev.md
```

**2. Edit it to match your project** — remove checks you don't care about, add ones you do.

**3. Run TinMan:**
```bash
pip install tinman-for-claudecode
tinman init
```

That's it. TinMan picks up `HEARTBEAT.md` from your project directory automatically.

**4. (Optional) Get alerts on your phone:**
```bash
pip install c3poh-for-claudecode
c3poh init
```

Then enable C3Poh notifications in TinMan's config.

---

## The one rule every template follows

Every template here ends with some version of:

> *Nothing urgent → `HEARTBEAT_OK`. Something found → bullets + ask before acting.*

This is intentional. Claude reports, never acts unilaterally. If you want Claude to take action, you have to explicitly tell it to in your own HEARTBEAT.md. The templates here won't do it by default.

---

## Contribute a template

Got a workflow that isn't covered? PRs welcome.

**Template format:**
```markdown
# Your Template Name

<!--
  Template: Short name
  Best for: Who this is for
  Interval: Recommended interval
  Mode: notify-only (default) or active
-->

[Your checklist here]

## Response format:
[How Claude should respond]

## Hard rules:
[What Claude must never do]
```

One template per file, named `NN-descriptive-name.md`. Add it to the table in this README.

---

## Related

- [TinMan](https://github.com/andyuninvited/tinman_for_claudecode) — the heartbeat scheduler these templates run on
- [C3Poh](https://github.com/andyuninvited/c3poh_for_claudecode) — Telegram bridge so heartbeat alerts reach your phone
- [Agent Blueprints](https://github.com/andyuninvited/agent-blueprints) — starter templates for more complex agents

---

## License

GNU GPLv3

---

*Built by [@andyuninvited](https://github.com/andyuninvited)*
