# Markdown Linter Reusable Workflow

This repository provides a reusable GitHub Actions workflow for linting Markdown files using [markdownlint-cli](https://github.com/DavidAnson/markdownlint-cli).

## Features

- Lints Markdown files in your repository
- Supports automatic fixing of lint issues
- Easily reusable across multiple repositories

## Usage

To use this workflow in another repository, call it from your workflow file:

```yaml
name: Lint Markdown Files
on:
  pull_request:

jobs:
  markdown-lint:
    uses: victoriacheng15hub/platform-actions/markdown-linter/markdownlinter.yml@main
    with:
      md_paths: |
        README.md
        docs/**/*.md
```

### Inputs

- `md_paths` (required): Newline-separated list of markdown file paths or globs to lint.

## Example

```yaml
jobs:
  markdown-lint:
    uses: victoriacheng15hub/platform-actions/markdown-linter/markdownlinter.yml@main
    with:
      md_paths: |
        README.md
        docs/**/*.md
```

## Notes

- The workflow runs on `ubuntu-latest` and installs `markdownlint-cli` via npm.
- Make sure your repository contains the markdown files or globs you specify.
- The workflow will attempt to fix issues automatically using the `--fix` flag.
