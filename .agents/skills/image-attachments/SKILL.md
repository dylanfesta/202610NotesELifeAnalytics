---
name: image-attachments
description: Add figures or supporting documents to the single-page eLife revision report using timestamped filenames and Git LFS.
metadata:
  author: Dylan Festa
  version: "1.1"
license: MIT
---

# Attachments for the eLife revision report

Adapted from the source template's image-attachments skill.

## Workflow

1. Identify the requested source file, usually in the repository's `temp/` directory. If the intended file is ambiguous, ask which one to use.
2. Copy it into this repository's `Attachments/` directory using `YYYYMMDD-HHMMSS-original-filename.ext` with the current local date and time. Preserve the original filename, avoid collisions, and leave the source unchanged.
3. Confirm that `.gitattributes` tracks the attachment through Git LFS. Use `git lfs install --local` if initialization is needed; do not modify global Git settings.
4. Add the attachment to the relevant section of `index.qmd`, the project's only rendered page. Keep `lightbox: true` in its front matter.
5. Run `quarto render` from the repository root and verify the link or figure in `_site/index.html`.

## Figures

Use a caption, a unique label, and meaningful alt text:

```markdown
![Figure caption](Attachments/YYYYMMDD-HHMMSS-original-filename.png){#fig-example fig-alt="Description of the figure."}
```

Refer to labeled figures with `@fig-example`. Replace example names with actual files and labels.

## Other files

Link supporting documents from `index.qmd`:

```markdown
[Supporting document](Attachments/YYYYMMDD-HHMMSS-original-filename.pdf)
```

Interactive HTML outputs may be linked or embedded using a relative path:

```html
<iframe src="Attachments/YYYYMMDD-HHMMSS-analysis.html" title="Interactive analysis" width="100%" height="600"></iframe>
```

Keep all destination files inside this repository and all report content in `index.qmd`. Do not create separate attachment or progress-report pages.
