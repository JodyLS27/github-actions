# Info
This repo is used to house any GitHub Actions that can be used across multiple
repositories in the `Hyper Active Forge` Organization.

> _When using these in a GitHub action, you should not write a GH-Action from scratch unless its specific to the project 
you need, otherwise it should be placed here in this project._
---
# Folder Structure
```
HyperActiveForge/github-actions/
  └── .github/workflows/
      ├── test.yaml
      ├── lint.yaml
      └── type-check.yaml
```
- **Test**: This is to run all `PyTest` tests for each repository
- **Lint**: `Ruff` is used for Linting and Checking the Project fies
- **Type-Check**: `mypy` is used for Type Checking: <br/> *TODO: Implement TY from Astrol*

---
# Usage
you should have a `ci.yaml` file in your *`[project]/.github/workflows/`* file.
This file will serve as a catch-all for any common **`CI/CD`** workflows that NEED to run.

To use a workflow from this Repo, you will need to do the following in your *`/ci.yaml`* file jobs:
```yaml
jobs:
  tests:
    uses: org-name/github-actions/.github/workflows/test.yaml@main
```

As you can see, you are able to call each GH-Action as required, so if you need the `lint` checker, you can just add a 
new `jobs` that looks at the _`/lint.yaml`_ file 

---