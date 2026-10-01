# mobile-maya-skills

Skill store for the **MAYA Android** voice companion. Each skill is a Claude-Code-style
`SKILL.md` playbook that teaches Maya the *right way* to do a job on the phone. The app
fetches `index.json` from this repo's `main` branch, shows the catalog in
**Settings → Skills**, and auto-updates installed skills when their `updated` stamp
changes here.

## Skill format

One markdown file in `skills/`, with frontmatter:

```markdown
---
name: my-skill-name
description: One line — WHEN Maya should use this skill (shown in her prompt index)
---
# Title

Step-by-step Hinglish instructions using Maya's real tools...
```

Rules:
- `name`: short kebab-case, unique.
- `description`: ONE line, ≤140 chars — this is the only part that lives in Maya's
  system prompt permanently, so make it a good trigger ("jab user X bole...").
- Body: ≤6000 chars. Loaded on demand via the `use_skill` tool, so it can be detailed.
- Language: instructions in Hinglish (it's Maya's voice), structure/headers anywhere.

## Adding a skill

1. Add `skills/<name>.md` with the format above.
2. Add an entry to `index.json` with `name`, `description`, `file`, and today's date
   as `updated`.
3. Push to `main` — it appears in every app's store on the next refresh.

To update an existing skill: edit the file **and bump its `updated` date** — installed
copies auto-update on the users' next session.
