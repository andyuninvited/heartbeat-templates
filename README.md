# 💓 HEARTBEAT.md Templates

> Community templates for [TinMan](https://github.com/andyuninvited/tinman_for_claudecode) — the heartbeat scheduler for Claude Code.

Drop any of these into your project as `HEARTBEAT.md` and TinMan will run it on a schedule. Edit freely — these are starting points, not rules.

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
- Community: [t.me/tinmanc3poh](https://t.me/tinmanc3poh)
