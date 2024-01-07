# Super-Linter GitHub Actions Workflow

Automate code linting with the Super-Linter GitHub Actions workflow. This workflow checks for syntax errors, code style violations, and other issues across multiple programming languages.

## Overview

This GitHub Actions workflow is triggered on every push to the `main` branch, ensuring continuous linting of the codebase. The Super-Linter tool provides comprehensive linting using version `v4.9.5` and supports a wide range of programming languages.

## Workflow Steps

1. **Code Checkout**: The `actions/checkout` action fetches the repository's code into the workflow environment.

2. **Super-Linter Execution**: The `github/super-linter` action performs linting, checking for coding standards and potential issues.

3. **Environment Variables**: Customize the Super-Linter behavior using environment variables (`Default_Branch` and `Github_Token`).
   

<img width="1048" alt="Screenshot 2024-01-06 at 8 01 05 PM" src="https://github.com/sachinj56/Netflix-Homepage-Clone/assets/83384002/04f7dc5d-5f50-42ef-8a0f-bc06ca918da4">

## Getting Started

To use this workflow in your repository, create a `.github/workflows/super-linter.yml` file with the following content:
 
```yaml
name: Super-Linter

on:
  push:
    branches:
      - main

jobs:
  super-lint:
    name: Lint code base
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Super-Linter
        uses: github/super-linter@v4.9.5
        env:
          Default_Branch: main
          Github_Token: ${{ secrets.GITHUB_TOKEN }}



