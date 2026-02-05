# Contributing to Clawed-Up

Thank you for your interest in contributing to Clawed-Up! This document provides guidelines for submitting
contributions to this repository.

## Code of Conduct

Be respectful, collaborative, and constructive in all interactions. We welcome diverse perspectives and expertise
from computing experts and Claude enthusiasts.

## How to Contribute

### 1. Start a Feature Branch

Use the provided git workflow automation:

```bash
/git-start-feature your feature description
```

This will create a properly-named feature branch and update your local main branch.

### 2. Make Your Changes

- Keep changes focused and well-organized
- Update documentation as needed
- Ensure all markdown files wrap at 120 columns
- Add explanatory comments to complex sections

### 3. Commit and Push

Use the git workflow automation to complete your feature:

```bash
/git-finish-feature
```

This command will:
- Stage your relevant changes
- Draft a commit message in imperative mood
- Push to your remote branch
- Create a pull request

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

- Add to the appropriate directory in `claude/`
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
