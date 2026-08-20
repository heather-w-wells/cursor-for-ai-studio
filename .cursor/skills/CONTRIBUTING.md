# Contributing Skills

This folder contains shared Cursor skills for the AI Studio team. Each skill lives in its own subfolder with a `SKILL.md` file.

## Adding a New Skill

1. Create a folder with a descriptive name (lowercase, hyphens only):
   ```
   .cursor/skills/your-skill-name/
   ```

2. Add a `SKILL.md` with the required frontmatter:
   ```markdown
   ---
   name: your-skill-name
   description: What this skill does and when to use it.
   ---

   # Your Skill Name

   Instructions for the agent go here.
   ```

3. Optionally add supporting files (keep references one level deep):
   ```
   your-skill-name/
   ├── SKILL.md          # Required
   ├── reference.md      # Optional - detailed docs
   └── scripts/          # Optional - utility scripts
   ```

4. Commit and push.

## Naming Conventions

| Rule | Example |
|------|---------|
| Lowercase with hyphens | `code-review`, `generate-report` |
| Max 64 characters | — |
| Descriptive, not generic | `analyze-api-logs` not `helper` |

## Tips

- Keep `SKILL.md` under 500 lines — use separate reference files for detailed content.
- Write descriptions in third person ("Generates reports..." not "I generate reports...").
- Include both **what** the skill does and **when** to use it in the description.
- Add `disable-model-invocation: true` to the frontmatter if the skill should only run when explicitly invoked.
