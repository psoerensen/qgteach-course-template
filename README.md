# qgteach course template

This repository is a reusable Quarto template for creating qgteach-style course websites.

Use it when you want a course repository with a consistent structure for notes, slides, tutorials, exercises, apps, data, images, narration, scripts, tools, and rendered website output.

## What this template provides

The template contains:

-   a Quarto website configuration in `_quarto.yml`

-   a landing page in `index.qmd`

-   an example notes page in `notes/notes.qmd`

-   an example RevealJS slide deck in `slides/introduction.qmd`

-   standard folders for common course material

-   a local-only agent-instructions example in `AGENTS.example.md`

-   a GitHub Pages-ready `docs/` output folder

## Standard repository structure

```         
course-repo/   _quarto.yml   index.qmd   README.md   .gitignore   course-name.Rproj    notes/   slides/   tutorials/   exercises/   apps/   data/   images/   narration/   scripts/   tools/   docs/ 
```

Folder roles:

-   `notes/`: longer explanatory course notes

-   `slides/`: lecture slides and slide-specific configuration

-   `tutorials/`: guided practicals or walkthroughs

-   `exercises/`: student exercises or assignments

-   `apps/`: Shiny apps or other interactive teaching tools

-   `data/`: documented example datasets; do not include private data

-   `images/`: figures, diagrams, and other image assets

-   `narration/`: audio files or narration-related material

-   `scripts/`: reproducible helper scripts

-   `tools/`: course development tools

-   `docs/`: rendered website output for GitHub Pages

## Create a new course from the template

On GitHub:

1.  Click **Use this template**.

2.  Create a new repository for your course.

3.  Clone the new repository to your computer.

4.  Open the `.Rproj` file in RStudio.

Alternatively, copy the repository manually and rename it.

## First edits after creating a course

After creating a new course repository:

1.  Rename the `.Rproj` file to match the course repository.

2.  Update the website title in `_quarto.yml`.

3.  Update the title and introduction in `index.qmd`.

4.  Update this `README.md` so it describes the new course.

5.  Replace the example files in `notes/` and `slides/` with real course material.

6.  Add or remove pages from `_quarto.yml` under `project.render`.

7.  Update the website navigation in `_quarto.yml`.

## Render the course website

From the repository root, run:

```         
quarto render 
```

The rendered website is written to:

```         
docs/ 
```

To render a single file while developing, use for example:

```         
quarto render notes/notes.qmd quarto render slides/introduction.qmd 
```

## Publish with GitHub Pages

This template is designed to publish from the `docs/` folder.

On GitHub:

1.  Go to **Settings**.

2.  Open **Pages**.

3.  Under **Build and deployment**, choose **Deploy from a branch**.

4.  Select:

    -   branch: `main`

    -   folder: `/docs`

5.  Save.

Before publishing, render locally and commit the updated `docs/` folder:

```         
quarto render git add docs/ git commit -m "Render course website" git push 
```

## Add course materials

Add material to the appropriate folders:

-   notes go in `notes/`

-   slides go in `slides/`

-   tutorials go in `tutorials/`

-   exercises go in `exercises/`

-   apps go in `apps/`

-   data go in `data/`

-   images go in `images/`

-   narration files go in `narration/`

-   helper scripts go in `scripts/`

-   development tools go in `tools/`

When adding a new Quarto page that should be part of the website, also update `_quarto.yml`.

For example, if you add:

```         
tutorials/tutorial-01.qmd 
```

then add it to:

```         
project:   render:     - tutorials/tutorial-01.qmd 
```

and add a navigation link if needed:

```         
website:   navbar:     left:       - text: "Tutorial 1"         href: tutorials/tutorial-01.qmd 
```

## Local agent guidance

`AGENTS.example.md` contains optional guidance for Codex or other coding agents.

To use it locally:

```         
cp AGENTS.example.md AGENTS.md 
```

On Windows PowerShell:

```         
Copy-Item AGENTS.example.md AGENTS.md 
```

`AGENTS.md` is ignored by Git and should not be committed. This keeps personal agent instructions local while still giving collaborators an example they can adapt.

## Files that should usually not be committed

The `.gitignore` file excludes common local files such as:

-   `.Rproj.user/`

-   `.Rhistory`

-   `.RData`

-   `.Ruserdata`

-   `.quarto/`

-   `AGENTS.md`

Do not commit private data, local credentials, API keys, or generated cache folders.

## Notes for collaborators

Keep changes small and reviewable. When editing course material:

-   preserve valid Quarto syntax

-   keep code examples reproducible

-   avoid private file paths

-   document required R packages

-   render changed files before publishing

-   commit rendered `docs/` output only when the website is ready to update
