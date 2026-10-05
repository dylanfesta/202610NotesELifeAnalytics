# Analytics for eLife revision

A single-page Quarto report for analyses, reviewer questions, and response material supporting an eLife revision. Adapted from `/home/dylan/Repositories/PlasticityAndStructureAnalytics/`.

## Requirements

- Quarto (setup verified with version 1.9.37)
- Git and Git LFS for project attachments

The starter page uses Markdown only and needs no Python, Julia, or R environment.

## Render and preview

Run these commands from this repository:

```sh
quarto render
quarto preview
```

The rendered page is `_site/index.html`. Only `index.qmd` is rendered; the README and agent instructions are repository documentation. Build output is ignored by Git.

## Structure

- `index.qmd`: the complete report, with sections for reviewer questions, analyses, responses, and revision notes.
- `_quarto.yml` and `styles.css`: single-page configuration and styling, retaining the template's dark theme and table of contents.
- `scripts/`: supporting analysis scripts as they are developed.
- `Attachments/`: figures and supporting files, tracked with Git LFS.
- `temp/`: ignored attachment staging directory, created during setup; recreate it after cloning with `mkdir -p temp`.
- `AGENTS.md` and `CLAUDE.md`: project instructions for coding agents.
- `.agents/skills/quarto-authoring/`: the template's Quarto authoring skill and references.
- `.agents/skills/image-attachments/`: attachment workflow adapted for this single page.

The template's separate content and progress-report pages are replaced by sections within `index.qmd`.

## Attachments

LFS is initialized locally during project setup. After cloning, initialize it for this repository:

```sh
git lfs install --local
git lfs pull
```

Copy attachments into `Attachments/` using `YYYYMMDD[-HHMMSS]-original-filename.ext`. Reference them from `index.qmd` with relative paths, descriptive captions, and alt text:

```markdown
![Descriptive figure caption](Attachments/YYYYMMDD-HHMMSS-figure.png){#fig-example fig-alt="Description of the figure."}
```

Replace the example filename with an actual attachment before adding it to the page. Keep analytical assumptions, methods, script commands, and findings together so each result can be reproduced.

The starter contains placeholders, with no manuscript-specific results or reviewer comments yet.
