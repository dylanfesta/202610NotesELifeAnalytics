# Analytics for eLife revision

This project is a Quarto website for analytical work supporting an eLife revision, with a landing page linking to a report and a full analysis.

## Scope and structure

- Keep all project changes inside this repository. Treat the source template at `/home/dylan/Repositories/PlasticityAndStructureAnalytics/` as read-only.
- Keep `index.qmd` as the landing page, with the title "Analytics for eLife revision" and links to `report.qmd` ("Report") and `full-analysis.qmd` ("Full analysis").
- Keep `_quarto.yml` restricted to rendering `index.qmd`, `report.qmd`, and `full-analysis.qmd`. The report contains the model scheme, dynamics and plasticity equations, and concise fixed-point solutions with target-rate calibration and small-M expansions; keep detailed derivations, analyses, reviewer responses, and dated progress notes in the full analysis.
- Put supporting analysis scripts in `scripts/` and figures or supporting documents in `Attachments/`.
- Do not invent scientific results, reviewer comments, manuscript details, or citations. Clearly distinguish placeholders, assumptions, and verified findings.

## Authoring and checks

- Use `awk` for text replacement and not Python scripts.
- Use Markdown and Quarto conventions. Read `.agents/skills/quarto-authoring/SKILL.md` for Quarto-specific tasks and only the relevant reference files.
- Use stable section, equation, table, and figure labels for cross-references.
- Separate multiplied variables or factors with `\,` in LaTeX equations, for example `$w_{12}\,w_{21}$`.
- Preserve the template's dark theme, table of contents, and image lightbox unless asked otherwise.
- After changing page content, configuration, styles, or referenced resources, run `quarto render` from the repository root and check `_site/index.html`, `_site/report.html`, and `_site/full-analysis.html`, including navigation and cross-references.
- Keep generated output and local analysis environments out of Git. Add analysis dependencies only when an analysis requires them, and document how to reproduce its results.

## Attachments

- Read `.agents/skills/image-attachments/SKILL.md` when adding attachments.
- Copy attachments into `Attachments/` with names like `YYYYMMDD[-HHMMSS]-original-filename.ext`; never overwrite existing files.
- Track attachments with Git LFS using `.gitattributes`. Initialize LFS with `git lfs install --local` so configuration stays inside this repository.
- `temp/` is an ignored staging directory. Do not delete source files after copying them.
