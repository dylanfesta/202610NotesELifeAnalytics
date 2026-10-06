# Analytics for eLife revision

A Quarto website for analyses, reviewer questions, and response material supporting an eLife revision. Its landing page links to a concise report and a full analysis. Adapted from `/home/dylan/Repositories/PlasticityAndStructureAnalytics/`.

## Requirements

- Quarto (setup verified with version 1.9.37)
- Git and Git LFS for project attachments

The pages use Markdown only and need no Python, Julia, or R environment.

## Render and preview

Run these commands from this repository:

```sh
quarto render
quarto preview
```

The rendered pages are `_site/index.html`, `_site/report.html`, and `_site/full-analysis.html`. Only their three source pages are rendered; the README and agent instructions are repository documentation. Build output is ignored by Git.

## Structure

- `index.qmd`: landing page titled "Analytics for eLife revision", linking to Report and Full analysis.
- `report.qmd`: concise report, containing the three-neuron model scheme, dynamics and plasticity equations, and concise fixed-point solutions, target-rate calibration, and small-M expansions.
- `full-analysis.qmd`: all previously existing content, including model definitions, detailed derivations, fixed points, timescales, and the generalization to N inhibitory neurons and K excitatory targets. Add detailed analyses, reviewer responses, and revision notes here.
- `_quarto.yml` and `styles.css`: three-page configuration and navigation, retaining the template’s dark theme and table of contents.
- `scripts/`: supporting analysis scripts as they are developed.
- `Attachments/`: figures and supporting files, tracked with Git LFS.
- `temp/`: ignored attachment staging directory, created during setup; recreate it after cloning with `mkdir -p temp`.
- `AGENTS.md` and `CLAUDE.md`: project instructions for coding agents.
- `.agents/skills/quarto-authoring/`: the template's Quarto authoring skill and references.
- `.agents/skills/image-attachments/`: attachment workflow for project pages.


## Attachments

LFS is initialized locally during project setup. After cloning, initialize it for this repository:

```sh
git lfs install --local
git lfs pull
```

Copy attachments into `Attachments/` using `YYYYMMDD[-HHMMSS]-original-filename.ext`. Reference them from `report.qmd` or `full-analysis.qmd` with relative paths, descriptive captions, and alt text:

```markdown
![Descriptive figure caption](Attachments/YYYYMMDD-HHMMSS-figure.png){#fig-example fig-alt="Description of the figure."}
```

Replace the example filename with an actual attachment before adding it to the page. Keep analytical assumptions, methods, script commands, and findings together so each result can be reproduced.

The report presents concise model results; the full analysis contains the detailed analytical work.
