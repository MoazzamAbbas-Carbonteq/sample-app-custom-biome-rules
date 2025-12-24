# GitHub Actions Workflows

This directory contains the GitHub Actions workflows for the CI/CD pipeline of this project.

## CI Pipeline (.github/workflows/ci.yml)

The CI pipeline runs on the following events:
- Push to `main`, `develop`, or `development` branches
- Pull requests targeting the `main` branch

### Checks Performed

1. **Code Formatting**: Checks if the code is properly formatted using Biome
2. **Linting**: Runs Biome linter with custom rules and reports issues with exact line numbers
3. **Tests**: Executes the test suite using Vitest
4. **Build**: Verifies that the project builds successfully

### Error Reporting

- The workflow uses custom problem matchers to format Biome's output into GitHub annotations
- For pull requests, a comment is added with a summary of all check results
- Failed checks will prevent the PR from being merged

### Custom Biome Rules

The project includes custom Biome rules located in the `grit-rules/` directory:
- `no-console.grit`: Disallows console.log statements
- `reportassign.grit`: Enforces object spread instead of Object.assign()

### Problem Matcher (.github/workflows/biome-problem-matcher.json)

The problem matcher formats Biome's output into GitHub annotations, making it easier to identify and fix issues directly in the PR interface.
