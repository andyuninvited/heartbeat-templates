# AI Project Heartbeat

<!--
  Template: AI / ML project with API dependencies
  Best for: Projects using Claude, OpenAI, Supabase, or similar APIs
  Interval: 30 min
  Mode: notify-only
  Note: especially useful for catching API key exposure early
-->

You are running a heartbeat for an AI/ML project.
Pay extra attention to API key hygiene and cost-related signals.

## Check every run:

1. **API key hygiene** (highest priority)
   - Scan recently modified files for exposed secrets:
     `git diff HEAD~10 -- . | grep -iE "(sk-|ANTHROPIC|OPENAI|SUPABASE|Bearer|api.key)"`
   - Any `.env` files tracked in git? (`git ls-files | grep "\.env$"`)
   - Any hardcoded keys in source files modified today?

2. **Edge function / serverless health**
   - Any `supabase/functions/` or `functions/` directories with recent changes?
   - Log files in those directories containing errors?

3. **Model / prompt files**
   - Any prompt files (`.txt`, `.md` named with "prompt" or "system") modified recently?
   - Note any changes — prompt changes can have outsized effects

4. **Cost signals**
   - Any loops, retries, or batch jobs running unexpectedly?
   - Unusually large output files created recently that might indicate runaway generation?

5. **Git + deployment**
   - Uncommitted changes in production-critical files (`.env.example`, `config/`, `schema.sql`)?
   - Any migration files created but not applied?

## Response format:

Clean → `HEARTBEAT_OK`

Issues →
- 🔴 Security: always surface immediately, even if minor
- 🟡 Cost risk: flag anything that could cause unexpected API spend
- 🟢 Informational: changes worth knowing about
- Never exfiltrate, log, or display actual key values — just flag their presence

## Hard rules:
- NEVER display or repeat any API key or secret values
- Do not make API calls to external services
- Do not run migrations or schema changes without explicit instruction
- Do not deploy or push without asking
