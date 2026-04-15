# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is
This repository is a **Claude Code skill** (Nutrition AI Sao Paulo) implemented entirely as Markdown.

The “runtime” artifact is `SKILL.md`: Claude Code reads the YAML frontmatter (metadata + allowed tools) and the specific nutritional prompts/instructions for the 21-year-old Bulking profile in Sao Paulo.

`README.md` is for humans: installation, regional context overview, and the nutritional mission statement.

## Key files (and how they relate)
- `SKILL.md`
  - The actual skill definition and logic.
  - Starts with YAML frontmatter containing `name` (nutrition-ai-sp), `version`, and `allowed-tools`.
  - Contains the core instruction set for the AI's persona, local market knowledge (Tauste, Coop, Confiança), and the bulking logic.
- `README.md`
  - Installation and usage instructions.
  - Contains the feature tables and the localized shopping guide.

When changing nutritional logic or local data, treat `SKILL.md` as the source of truth, and update `README.md` to stay consistent.

## Common commands
### Install the skill into Claude Code
Recommended (clone directly into Claude Code skills directory):
```bash
mkdir -p ~/.claude/skills
git clone [https://github.com/paulo-straforini/nutrition-ai-sp.git](https://github.com/paulo-straforini/nutrition-ai-sp.git) ~/.claude/skills/nutrition-ai-sp
Manual install/update (only the skill file):

Bash
mkdir -p ~/.claude/skills/nutrition-ai-sp
cp SKILL.md ~/.claude/skills/nutrition-ai-sp/
How to “run” it (Claude Code)
Invoke the skill:

/nutrition-ai-sp then ask your nutrition/bulking question.

Making changes safely
Versioning (keep in sync)
SKILL.md has a version: field in its YAML frontmatter.

README.md should reflect the current status in its header.

If you update the caloric calculations or local market logic, bump the version in both files.

Editing SKILL.md
Preserve valid YAML frontmatter formatting and indentation.

Maintain the Sao Paulo regional focus (climate, local stores) as this is a key performance driver for the skill.

Documenting non-obvious fixes
If you adjust the prompt to handle specific regional issues (e.g., better hydration tips for SP's heatwaves or better cost-benefit for local products), add a note to the commit to track the evolution of the nutritional advice.


---

### Destaques da adaptação:
* **Identidade:** Renomeado para `nutrition-ai-sp` para manter a consistência com o `SKILL.md`.
* **Contexto Local:** Mantive a menção aos mercados (Tauste, Coop, Confiança) e ao clima de SP nas diretrizes de edição.
* **Instalação:** Caminhos de diretório e comandos `git clone` ajustados para o nome da sua skill.
* **Sincronização:** Instrução clara para manter o `SKILL.md` (lógica da IA) e o `README.md` (documentação humana) em sintonia.
