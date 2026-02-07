# Claude Code Examples

This directory contains real, production-tested examples of Claude Code configurations and files.

## Contents

### claude-directory/

Example files for setting up and managing your `~/.claude` directory:

- **`gitignore-example`** - Comprehensive `.gitignore` for version controlling `~/.claude`
  - Covers Claude Code runtime directories (debug, file-history, ide, session-env, etc.)
  - Excludes sensitive credentials and session history
  - Excludes project-specific data and plugins
  - Safe for version control while protecting sensitive information
  - Copy to `~/.claude/.gitignore` when setting up version control

## Usage

These are real configuration files extracted from working setups. You can:

1. **Copy directly**: Use these as starting points for your own configurations
2. **Reference**: Compare with your existing setup to identify gaps
3. **Customize**: Adapt these examples to your specific needs

## Contributing Examples

Have a useful configuration or pattern? Contributions are welcome! Examples should:

- Be tested in real use
- Include comments explaining non-obvious choices
- Follow the repository's documentation standards
- Protect sensitive information (no credentials, tokens, or personal data)

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for contribution guidelines.
