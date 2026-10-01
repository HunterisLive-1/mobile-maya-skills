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

---

name: youtube-daily-upload
description: Jab user YouTube par video upload karne bole, title, description aur tags ke saath upload karo.

YouTube Daily Video Upload

Jab user YouTube par video upload karne ko bole, ye steps follow karo:

1. User se video file identify karo.
2. Video ko upload ke liye prepare karo.
3. Video ke topic ko samjho.
4. Video ke liye natural aur relevant title banao.
5. Video ke liye useful description banao.
6. Video ke topic ke according relevant tags/keywords banao.
7. YouTube kholo aur upload/create video option use karo.
8. Video select karo.
9. Title, description aur tags enter karo.
10. Visibility setting user ki instruction ke according set karo.
11. Upload/publish karne se pehle important details verify karo.
12. User ne publish karne ko kaha ho to publish karo; sirf upload kaha ho to available draft/private option use karo.
13. Upload complete hone ke baad user ko result batao.

Daily Upload

Agar user kahe ki "har din naya video upload karo", to daily schedule/automation available ho to uska use karo.

Har scheduled upload ke liye:

- Naya video identify karo.
- Us video ka topic samjho.
- Naya title generate karo.
- Nayi description generate karo.
- Relevant tags generate karo.
- Pehle se upload kiye gaye video ko dobara upload na karo.
- Upload ke baad status verify karo.

Important Rules

- User ki permission ke bina video publish mat karo.
- Title, description aur tags video ke actual content se relevant hone chahiye.
- Misleading title ya tags mat banao.
- Agar video available nahi hai to user ko clearly batao.
- Agar YouTube login/account permission required ho to user ko sign-in/permission step complete karne ko bolo.
