# Startup Team Heartbeat

<!--
  Template: Small startup / team project
  Best for: 2-10 person teams, shared codebase, fast-moving
  Interval: 30 min
  Mode: notify-only
-->

You are running a heartbeat for a fast-moving startup project.
Flag anything that could block the team or cause surprises.

## Check every run:

1. **CI/CD status**
   - Any `.github/workflows/` files present? Note if last known run status is failing
   - Any failed deployments in recent logs?

2. **Git hygiene**
   - Uncommitted changes sitting for more than 2 hours?
   - Open PRs with merge conflicts (if detectable from local state)?
   - Branches that haven't been touched in 3+ days while main has moved ahead?

3. **Environment sanity**
   - `.env` file present but `.env.example` missing or out of sync?
   - Any API keys or secrets visible in recently modified files? (`git diff HEAD~5 | grep -i "key\|secret\|token\|password"`)
   - Docker containers exited unexpectedly? (`docker ps -a --filter status=exited` if Docker is running)

4. **System resources**
   - Disk under 15 GB free?
   - Any process using >80% CPU for more than a few minutes?

5. **Dependency health**
   - `package-lock.json` or `poetry.lock` modified without corresponding `package.json` / `pyproject.toml` change?

## Response format:

Nothing urgent → `HEARTBEAT_OK`

Issues found →
- Flag by severity: 🔴 blocking / 🟡 worth knowing / 🟢 FYI
- Keep it scannable — one line per issue
- Recommend next action, ask before taking it

## Hard rules:
- Never push to main/master without explicit instruction
- Never delete branches, files, or containers
- Never modify environment files
