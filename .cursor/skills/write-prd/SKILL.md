---
name: write-prd
description: Write a PRD from a template. Use when the user asks to create a PRD, draft product requirements, or write a spec.
disable-model-invocation: true
---

# Write PRD

## Overview

Generate a PRD by selecting a template from the vault's `templates/` folder, grounding content in context and research files, and drafting section-by-section with user approval.

## Workflow

### 1. Select a template

1. List all `.md` files in the `templates/` folder at the vault root.
2. Use the AskQuestion tool to present the list and ask the user which template to use.
3. Read the selected template file to understand its structure and sections.

### 2. Read context and research

1. Look for `context/` and `research/` folders relative to the current project or vault root.
2. Read all files in those folders to gather grounding material.
3. Note which facts come from which source files — you will need this for assumption flagging.

### 3. Ask the 5 hardest questions

Based on the template sections and the gaps in the context/research files, identify the 5 most critical questions that will shape the PRD. These should be questions where:

- The answer materially changes the scope, direction, or feasibility
- The context files do not already provide a clear answer
- Getting it wrong would cause rework downstream

Ask these questions **one at a time** using the AskQuestion tool or plain text. Wait for the user's answer before asking the next question.

Do NOT begin drafting until all 5 questions are answered.

### 4. Draft section by section

For each section in the selected template:

1. Write the section content, grounding claims in context/research files where possible.
2. Flag any claim that cannot be traced to a context or research file with `[ASSUMPTION]`.
3. Present the drafted section to the user.
4. **Pause and wait for approval** before moving to the next section.
5. If the user requests changes, revise the section and present again.

### 5. Save the PRD

1. Ask the user where in the vault to save the file (suggest a default like `PRDs/<feature-name>.md` or the relevant project folder).
2. Write the complete PRD to the specified path.
3. Confirm the file was saved and provide the path.

## Rules

- Never draft before all 5 questions are answered.
- Never advance to the next section without explicit user approval.
- Every factual claim must either cite a context/research file or be flagged `[ASSUMPTION]`.
- Use plain English. Avoid jargon unless it appears in the context files.
- Use tables for structured data (metrics, risks, dependencies, timelines).
- If the template has sections that don't apply, ask the user whether to skip or include them.

## Output format

- Standard markdown, compatible with Obsidian.
- Use the exact heading structure from the selected template.
- Preserve any metadata tables or frontmatter the template defines.
