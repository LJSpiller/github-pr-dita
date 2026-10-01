![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)
![Made with VS Code](https://img.shields.io/badge/Made%20with-VS%20Code-blue?logo=visual-studio-code)

# Technical Writing Portfolio Sample: GitHub Pull Request Governance

> **Note:** This repository is a self-guided training project and technical writing portfolio sample created to explore structured authoring, single-sourcing concepts, and DITA 1.3 architecture in Visual Studio Code. It provides a focused workflow sample rather than an exhaustive documentation suite.

## Project & Architecture Highlights

* **Key Definitions (`ditamaps/keys.ditamap`):** Centralized variable management for platform names, repository references, and review SLAs using key definitions.
* **Content Reuse (`reusable/conrefs.dita`):** Single-sourced warning and important notes reused across task topics via `conref`.
* **Conditional Publishing (`filters/admin-filter.ditaval`):** Attribute-based filtering (`audience="admin"`) to demonstrate role-based content targets.
* **Topic-Based Authoring:** Structured separation of Concepts (`c-pr-lifecycle.dita`), Tasks (`t-review-pull-request.dita`), and References (`r-merge-strategies.dita`).

## Authoring Tooling
* Authored and validated using Visual DITA in Visual Studio Code.
* Portions of this documentation were drafted with assistance from AI tooling as part of a structured authoring training exercise.

## Repository Structure
```text
github-pr-dita/
├── ditamaps/
│   ├── github-pull-requests.ditamap    # Primary publication map
│   └── keys.ditamap                    # Key definition map for variables
├── concepts/
│   ├── c-pr-lifecycle.dita             # Pull request lifecycle concept
│   └── c-branch-strategy.dita          # Branching governance rules
├── tasks/
│   ├── t-create-pull-request.dita      # Task: Creating a pull request
│   ├── t-review-pull-request.dita      # Task: Reviewing a pull request
│   └── t-resolve-conflicts.dita       # Task: Resolving merge conflicts
├── references/
│   ├── r-merge-strategies.dita         # Reference: Merge options & descriptions
│   └── r-pr-statuses.dita              # Reference: CI status indicators & badges
├── reusable/
│   └── conrefs.dita                    # Centralized library for reusable notes
└── filters/
    └── admin-filter.ditaval            # Conditional processing filter
```
---

## License

This repo and its assets are licensed under the [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](https://creativecommons.org/licenses/by-nc-nd/4.0/).

You are welcome to view, share, and reference this repository as a learning sample with attribution. You may not use this material for commercial purposes or distribute modified versions as derivative works.