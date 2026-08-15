# Contributing to Clawed-Up

Thank you for your interest in contributing to Clawed-Up! This document provides guidelines for submitting
contributions to this repository.

## Code of Conduct

Be respectful, collaborative, and constructive in all interactions. We welcome diverse perspectives and expertise
from computing experts and Claude enthusiasts.

## How to Contribute

### 1. Start a Feature Branch

Branch from an updated main:

```bash
git checkout main && git pull origin main
git checkout -b your-feature-name
```

### 2. Make Your Changes

- Keep changes focused and well-organized
- Update documentation as needed
- Ensure all markdown files wrap at 120 columns
- Add explanatory comments to complex sections

### 3. Commit and Push

Commit in imperative mood with subject lines under 72 characters, then push and open a PR:

```bash
git push -u origin your-feature-name
gh pr create
```

### 4. Pull Request Review

- Provide a clear description of your changes in the PR
- Explain the motivation and any design decisions
- Be prepared to discuss and refine your implementation
- PRs will be reviewed and merged manually by maintainers

## Documentation Standards

Since this is a documentation-focused repository:

- Use clear, concise language
- Assume the audience includes both technical experts and learners
- Wrap markdown at 120 columns for consistency
- Include examples where helpful
- Link to relevant resources or related documentation

## Guidelines for Different Contribution Types

### New Skills or Utilities

- Add to the appropriate top-level directory (`skills/`, `guides/`, `guidelines/`, `examples/`)
- Include comprehensive documentation in comments
- Provide usage examples
- Update the relevant index or README file

### Documentation Improvements

- Ensure clarity and accuracy
- Maintain consistent formatting and tone
- Update dates or version information if applicable
- Fix typos and improve readability

### Bug Fixes or Improvements

- Describe the issue being fixed
- Explain your solution approach
- Test your changes if applicable
- Reference any related issues

## Questions or Discussion

If you have questions about contributing or want to discuss a potential contribution, feel free to open an issue
or reach out to the maintainers.

## License

By contributing to this repository, you agree that your contributions will be licensed under the same license as
the project (see [LICENSE](LICENSE)).
