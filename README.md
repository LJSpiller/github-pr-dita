![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)
![Made with VS Code](https://img.shields.io/badge/Made%20with-VS%20Code-blue?logo=visual-studio-code)

# DITA 1.3 documentation sample with conditional publishing

> **Note:** This repository is a self-guided training project and technical writing portfolio sample created to explore structured authoring, single-sourcing concepts, and DITA 1.3 architecture in Visual Studio Code. It provides a focused workflow sample rather than an exhaustive documentation suite.

## View the published guide

**[Open the published guide](https://ljspiller.github.io/github-pr-dita/)**

Three versions are available:
* **HTML5 version:** The complete guide with sidebar navigation. 
* **Admin version:** The same guide filtered for the admin audience.
* **PDF version:** A print-ready version of the guide.  

## Project and architecture highlights

* **Key definitions (`keys.ditamap`):** Centralized variable management for platform names, repository references, and review SLAs using key definitions.
* **Content reuse (`reusable/conrefs.dita`):** Single-sourced warning and important notes reused across task topics via `conref`.
* **Conditional publishing (`filters/admin-filter.ditaval`):** Attribute-based filtering (`audience="admin"`) to demonstrate role-based content targets.
* **Topic-based authoring:** Structured separation of Concepts (`c-pr-lifecycle.dita`), Tasks (`t-review-pull-request.dita`), and References (`r-merge-strategies.dita`).
* **Custom HTML5 styling (`css/custom.css`):** Overrides the default DITA-OT HTML5 presentation to improve navigation, readability, and GitHub Pages presentation.
* **Automated publishing (.github/workflows/build-dita.yml):** A manually triggered GitHub Actions workflow that runs DITA-OT in a container and produces HTML5, filtered HTML5, and PDF output without installing Java or DITA-OT locally.

## How it is built

1. Content is authored as DITA 1.3 topics and publication map (`github-pull-requests.ditamap`). 
2. The **Build DITA output** workflow is run manually from the Actions tab. It uses DITA-OT 4.4.1 to build three outputs into `docs/`: `html5/`, `html5-admin` (filtered by `admin-filter.ditaval`), and `pdf/`. 
3. The generated output is added to the `docs/` folder, which GitHub Pages serves as the published site. 

## Known limitations
* The PDF is generated from a standard DITA map rather than a bookmap, so topics flow continuously without chapter-level page breaks. Tables may also split across pages. Producing a chapter-per-page PDF would require a separate bookmap, which is outside the scope of this sample. 

## Authoring tooling
* Authored and validated using Visual DITA in Visual Studio Code.
* Portions of this documentation were drafted with assistance from AI tooling as part of a structured authoring training exercise using DITA.

## Repository structure

```text
github-pr-dita/
├── .github/
│   └── workflows/
│       └── build-dita.yml              # GitHub Actions workflow for HTML5 and PDF builds
├── github-pull-requests.ditamap        # Primary publication map
├── keys.ditamap                        # Key definition map for variables
├── concepts/
│   ├── c-branch-strategy.dita          # Branching governance rules
│   └── c-pr-lifecycle.dita             # Pull request lifecycle concept
├── tasks/
│   ├── t-create-pull-request.dita      # Task: Creating a pull request
│   ├── t-review-pull-request.dita      # Task: Reviewing a pull request
│   └── t-resolve-conflicts.dita        # Task: Resolving merge conflicts
├── references/
│   ├── r-merge-strategies.dita         # Reference: Merge options and descriptions
│   └── r-pr-statuses.dita              # Reference: CI status indicators and badges
├── reusable/
│   └── conrefs.dita                    # Centralized library for reusable notes
├── filters/
│   └── admin-filter.ditaval            # Conditional processing filter
├── css/
│   └── custom.css                      # Custom HTML5 stylesheet
├── docs/                               # GitHub Pages published output
│   ├── index.html                      # Documentation landing page
│   ├── html5/                          # Standard HTML5 output
│   ├── html5-admin/                    # Admin-filtered HTML5 output
│   └── pdf/                            # Generated PDF output
├── LICENSE
└── README.md
```

---

## License

This repo and its assets are licensed under the [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](https://creativecommons.org/licenses/by-nc-nd/4.0/).

You are welcome to view, share, and reference this repository as a learning sample with attribution. You may not use this material for commercial purposes or distribute modified versions as derivative works.
