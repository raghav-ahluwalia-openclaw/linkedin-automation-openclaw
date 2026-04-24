# LinkedIn Opinion Engine (Data & BI)

This is a practical **PEMI** setup: Publish → Engage → Measure → Iterate.

## What this package gives you
- `n8n_workflow.json` → importable n8n workflow skeleton
- `airtable_schema.md` → Airtable base design
- `prompts.md` → reusable generation + rewrite + weekly-iteration prompts

## Recommended stack
- n8n (automation orchestrator)
- Airtable (idea backlog + post state + metrics)
- Buffer (safe LinkedIn scheduling)
- OpenAI (draft generation + weekly insights)
- Shield Analytics (or CSV export) for profile/post engagement data

## Core operating model
1. **Draft generation (weekly):** n8n pulls idea backlog and creates 3 post variants each.
2. **Human approval:** you approve/edit one variant per post in Airtable.
3. **Scheduling:** approved posts are sent to Buffer for LinkedIn scheduling.
4. **Engagement harvesting:** n8n syncs post metrics daily/weekly into Airtable.
5. **Iteration report:** top hooks/topics/CTAs are summarized into next week’s plan.

## Setup checklist
1. Create Airtable tables per `airtable_schema.md`.
2. Create Buffer app token + LinkedIn channel in Buffer.
3. Add API creds in n8n:
   - `AIRTABLE_API_KEY`
   - `AIRTABLE_BASE_ID`
   - `OPENAI_API_KEY`
   - `BUFFER_ACCESS_TOKEN`
   - `SHIELD_API_KEY` (optional, if using Shield API)
4. Import `n8n_workflow.json` into n8n.
5. Update placeholders in workflow nodes (base/table IDs, Buffer profile ID, model).
6. Run once manually and verify records are written correctly.

## Guardrails (important)
- Automate publishing + measurement.
- Keep comment replies human.
- Avoid scraping/bot-comment automation against LinkedIn ToS.

## Suggested posting cadence
- 3 posts/week (Tue/Thu/Sat) at your audience’s peak hour.
- 60-minute engagement sprint after each post.
- Weekly retro every Sunday.
