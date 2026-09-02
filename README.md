# DDC Skills Marketplace

A local [Claude Code](https://claude.com/claude-code) marketplace that packages the
[DataDrivenConstruction skills](https://github.com/datadrivenconstruction/DDC_Skills_for_AI_Agents_in_Construction)
(238 skills) into a single installable, toggleable **plugin**: `ddc-construction-skills`.

Packaging these as a plugin (instead of loose personal skills) means you can enable/disable the
whole set with one command, and share it to other machines or to Cowork.

## Install (Claude Code)

```bash
claude plugin marketplace add ~/ddc-skills-marketplace
claude plugin install ddc-construction-skills@ddc-marketplace
```

Restart Claude Code, then the skills are available to the Skill tool. Toggle anytime:

```bash
claude plugin disable ddc-construction-skills
claude plugin enable  ddc-construction-skills
```

## Install (Cowork / another machine)

Push this folder to a GitHub repo, then on the other machine / in Cowork:

```bash
claude plugin marketplace add <your-github-user>/ddc-skills-marketplace
claude plugin install ddc-construction-skills@ddc-marketplace
```

## What's inside

- `ddc-construction-skills/` — the plugin
  - `.claude-plugin/plugin.json` — plugin manifest
  - `skills/` — 238 skill folders, each with a `SKILL.md`
- `.claude-plugin/marketplace.json` — marketplace manifest

## Notes

- 7 skill names collided across the upstream categories; each was disambiguated by appending its
  source category (e.g. `co2-carbon-footprint-bim-analysis` vs `co2-carbon-footprint-sustainability`).
- The RVT / DWG / DGN converters rely on Windows-only binaries and won't execute on macOS/Linux;
  the IFC, Excel, CWICR cost, and analytics skills are cross-platform.
- Python deps for the runnable skills: `pip install pandas openpyxl ifcopenshell pdfplumber`.
- Upstream license/attribution: see `NOTICE.md` in the source repository.
