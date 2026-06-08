# qgteach course template

This repository is a reusable Quarto template for qgteach-style course websites.

## Use the template

1. Create a new repository from this template or copy the repository.
2. Rename the repository and the `.Rproj` file for your course.
3. Update the website title in `_quarto.yml` and the title in `index.qmd`.
4. Replace the example course materials with your own content.

## Render the course website

From the repository root, run:

```bash
quarto render
```

The rendered website is written to `docs/`.

## Publish with GitHub Pages

In the GitHub repository settings, configure Pages to deploy from the `main` branch and the `/docs` folder. Render and commit the updated `docs/` output before publishing.

## Add course materials

- Add course notes to `notes/`.
- Add presentation files to `slides/`.
- Add guided practical material to `tutorials/`.
- Add student tasks to `exercises/`.
- Add supporting apps, data, images, narration, scripts, and tools to their matching folders.
- Add new pages to `project.render` and the website navigation in `_quarto.yml` when they should be part of the website.

## Local agent guidance

`AGENTS.example.md` contains optional guidance for Codex and other coding agents. Copy it to `AGENTS.md` when local guidance is useful. Keep `AGENTS.md` local-only; it is ignored by Git and should not be committed.
