# Version Controlling Your ~/.claude Directory

This guide explains how to version control your Claude Code configuration directory (`~/.claude`) using Git,
enabling you to track changes, sync across machines, and share configurations with collaborators.

## Why Version Control ~/.claude?

Version controlling your Claude configuration provides several benefits:

- **Track changes**: See how your Claude Code setup evolves over time
- **Sync across machines**: Keep your configuration consistent on multiple systems
- **Share configurations**: Collaborate with team members or share best practices
- **Disaster recovery**: Restore your configuration if something breaks
- **Experimentation**: Try changes safely with the ability to roll back

## What to Version Control

**Include in version control:**
- `CLAUDE.md` - Global instructions for Claude Code
- `rules/*.md` - Path-specific constraints and patterns
- `skills/` - Custom skills and automation
- `keybindings.json` - Keyboard shortcut customizations
- Project-specific configurations you want to share

**Exclude from version control:**
- `cache/` - Temporary cache files
- `sessions/` - Conversation history (may contain sensitive data)
- `*.log` - Log files
- Any files containing API keys, secrets, or personal data

## Quick Start: Private GitHub Repository

**TL;DR** - Fastest path to version control your ~/.claude with a private GitHub repository:

```bash
cd ~/.claude

# Get the production-tested .gitignore
curl -o .gitignore \
  https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/claude/examples/claude-directory/gitignore-example

# Initialize and commit
git init
git add .
git commit -m "Initial commit: Claude configuration"

# Create private GitHub repo and push (requires GitHub CLI)
gh repo create claude-config --private --source=. --push
```

**Why private?** Your Claude configuration may contain project-specific patterns, file paths, organizational
information, and personal workflows that shouldn't be public.

For detailed step-by-step instructions, see the scenarios below.

## Scenario 1: Version Controlling an Existing ~/.claude Directory

If you already have a `~/.claude` directory with configuration you want to preserve:

### Step 1: Create a .gitignore

Create a `.gitignore` file to exclude sensitive and temporary files.

**Option A: Use the tested example (recommended)**

```bash
# Copy the comprehensive example from this repository
curl -o ~/.claude/.gitignore \
  https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/claude/examples/claude-directory/gitignore-example
```

**Option B: Create a basic one manually**

```bash
cat > ~/.claude/.gitignore << 'EOF'
# Claude Code runtime directories
debug/
file-history/
ide/
session-env/
shell-snapshots/
statsig/
tasks/
todos/

# Project-specific data
projects/
plugins/

# Sensitive credentials
.credentials.json

# Session history
history.jsonl
stats-cache.json
cache/
paste-cache/

# Session artifacts
plans/
telemetry/
downloads/
EOF
```

See [`claude/examples/claude-directory/gitignore-example`](../examples/claude-directory/gitignore-example) for a
complete, production-tested version.

### Step 2: Initialize the Git Repository

```bash
cd ~/.claude
git init
git add .
git commit -m "Initial commit: existing Claude configuration

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
```

### Step 3: Review What Will Be Committed

Before pushing, review what's being tracked:

```bash
git status
git ls-files
```

**Important**: Check for any sensitive data before pushing to a remote repository:

```bash
# Search for potential secrets
grep -r "api.*key\|password\|token\|secret" ~/.claude --exclude-dir=.git
```

### Step 4: Create a Private GitHub Repository

If you want to back up or share your configuration, create a private GitHub repository.

#### Option A: Using GitHub Web Interface

1. **Go to GitHub** and sign in to your account
2. **Create a new repository**:
   - Navigate to [github.com/new](https://github.com/new)
   - Repository name: `claude-config` (or your preferred name)
   - Description: "Personal Claude Code configuration"
   - **Visibility: Select "Private"** (recommended for personal configurations)
   - **Do NOT initialize** with README, .gitignore, or license (you already have these locally)
   - Click "Create repository"

3. **Connect your local repository**:

   GitHub will show you commands to push an existing repository. Use these:

   ```bash
   cd ~/.claude
   git remote add origin https://github.com/yourusername/claude-config.git
   git branch -M main
   git push -u origin main
   ```

   Replace `yourusername` with your actual GitHub username.

#### Option B: Using GitHub CLI (Faster)

If you have the GitHub CLI (`gh`) installed:

```bash
cd ~/.claude

# Create a private repository and push in one command
gh repo create claude-config --private --source=. --push

# Or if you want to be explicit about the remote name
gh repo create claude-config --private --remote=origin --source=. --push
```

The CLI will automatically:
- Create a private repository on GitHub
- Add it as the `origin` remote
- Push your main branch

#### Verify the Push

After pushing, verify everything worked:

```bash
# Check remote configuration
git remote -v

# View your repository on GitHub
gh repo view --web    # If using gh CLI
# Or visit: https://github.com/yourusername/claude-config
```

**Security consideration**: Always use a **private repository** for your Claude configuration because it may
contain:
- Project-specific patterns that reveal your work
- File paths and directory structures
- Coding preferences and workflows
- Potentially sensitive project names or organizational information

## Scenario 2: Starting Fresh with Version Control

If you don't have a `~/.claude` directory yet, or want to start clean:

### Step 1: Create and Initialize the Directory

```bash
mkdir -p ~/.claude
cd ~/.claude
git init
```

### Step 2: Create a .gitignore

**Option A: Use the tested example (recommended)**

```bash
# Download the comprehensive example
curl -o .gitignore \
  https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/claude/examples/claude-directory/gitignore-example
```

**Option B: Create a basic one manually**

```bash
cat > .gitignore << 'EOF'
# Claude Code runtime directories
debug/
file-history/
ide/
session-env/
shell-snapshots/
statsig/
tasks/
todos/

# Project-specific data
projects/
plugins/

# Sensitive credentials
.credentials.json

# Session history
history.jsonl
stats-cache.json
cache/
paste-cache/

# Session artifacts
plans/
telemetry/
downloads/
EOF
```

### Step 3: Create Basic Configuration Files

Create a basic `CLAUDE.md`:

```bash
cat > CLAUDE.md << 'EOF'
# Global CLAUDE.md

This file provides guidance to Claude Code when working across all projects.

## Code Style and Formatting

- **Line Length**: Wrap markdown, Bash, and Python files at 120 characters
- **Indentation**: Four spaces for indentation
- **Commit Messages**: Imperative mood, include co-author attribution

## User Profile

[Describe your expertise, preferences, and collaboration style here]

## Conventions Across Projects

[Document patterns and conventions you use across all projects]
EOF
```

Create directory structure:

```bash
mkdir -p rules skills projects
```

### Step 4: Initial Commit

```bash
git add .
git commit -m "Initial setup: Claude Code configuration

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
```

### Step 5: Create a Private GitHub Repository

Set up a remote repository to back up your configuration.

#### Option A: Using GitHub Web Interface

1. **Go to GitHub** and sign in to your account
2. **Create a new repository**:
   - Navigate to [github.com/new](https://github.com/new)
   - Repository name: `claude-config` (or your preferred name)
   - Description: "Personal Claude Code configuration"
   - **Visibility: Select "Private"** (recommended)
   - **Do NOT initialize** with README, .gitignore, or license
   - Click "Create repository"

3. **Push your local repository**:

   ```bash
   cd ~/.claude
   git remote add origin https://github.com/yourusername/claude-config.git
   git branch -M main
   git push -u origin main
   ```

   Replace `yourusername` with your actual GitHub username.

#### Option B: Using GitHub CLI (Faster)

```bash
cd ~/.claude
gh repo create claude-config --private --source=. --push
```

This automatically creates the private repository, adds the remote, and pushes your configuration.

## Workflow: Making Changes

As you work with Claude Code and refine your configuration:

### Track Individual Changes

```bash
cd ~/.claude

# After modifying files
git status
git diff

# Commit specific changes
git add CLAUDE.md
git commit -m "Update collaboration preferences for architecture discussions

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
```

### Sync Changes

```bash
# Pull changes from other machines
git pull

# Push your changes
git push
```

### Review History

```bash
# See what changed over time
git log --oneline

# Compare versions
git diff HEAD~1 CLAUDE.md
```

## Multi-Machine Setup

To sync your Claude configuration across multiple machines, you'll need a private GitHub repository. If you haven't
created one yet, follow the instructions in **Scenario 1, Step 4** or **Scenario 2, Step 5** above.

### On the First Machine

Once you have a private GitHub repository created:

```bash
cd ~/.claude
git remote add origin https://github.com/yourusername/claude-config.git
git push -u origin main
```

Or if you're using the GitHub CLI:

```bash
cd ~/.claude
gh repo create claude-config --private --source=. --push
```

### On Additional Machines

Clone your private repository to set up Claude configuration on another machine:

```bash
# Backup any existing configuration
mv ~/.claude ~/.claude.backup 2>/dev/null

# Clone your private configuration repository
git clone https://github.com/yourusername/claude-config.git ~/.claude
```

**Note**: GitHub will prompt for authentication when cloning a private repository. You can use:
- Personal Access Token (PAT) - recommended for HTTPS
- SSH key - if you have SSH set up with GitHub
- GitHub CLI (`gh auth login`) - simplest option

### Regular Sync Workflow

On any machine, after making changes:

```bash
cd ~/.claude
git pull              # Get changes from other machines
# ... make your changes ...
git add .
git commit -m "Description of changes"
git push              # Share with other machines
```

## Best Practices

### 1. Commit Frequently

Commit each meaningful change separately:
- "Add troubleshooting skill"
- "Update code formatting preferences"
- "Add rule for cryptographic operations"

### 2. Write Descriptive Commit Messages

Good:
```
Add Python formatting preferences to CLAUDE.md

Specify black formatting, type hints requirement, and docstring conventions
for Python projects.
```

Bad:
```
Update config
```

### 3. Use Branches for Experiments

```bash
# Try a new configuration approach
git checkout -b experiment/new-workflow-pattern
# ... make changes ...
git commit -m "Experiment: automated documentation workflow"

# If it works, merge it
git checkout main
git merge experiment/new-workflow-pattern

# If it doesn't, abandon it
git checkout main
git branch -D experiment/new-workflow-pattern
```

### 4. Separate Global and Project-Specific

- Keep `~/.claude/CLAUDE.md` for truly global preferences
- Use project-level `.claude/CLAUDE.md` (or `CLAUDE.md` in the project root) for project-specific guidance
- This allows projects to override global defaults

### 5. Document Why, Not Just What

In your CLAUDE.md files, explain the reasoning behind preferences:

```markdown
## Commit Messages

- **Format**: Imperative mood ("Add feature", not "Added feature")
- **Why**: Matches Git convention; reads as command to the codebase
- **Include**: Co-author attribution when Claude assisted
```

### 6. Regular Cleanup

Periodically review and clean up:
```bash
# Check repository size
du -sh ~/.claude/.git

# Remove obsolete configurations
git rm old-unused-file.md
git commit -m "Remove obsolete workflow configuration"
```

## Sharing Configurations

### Creating a Shareable Template

To share your configuration with others while keeping personal details private:

```bash
# Create a clean branch
git checkout -b template

# Remove personal information
git rm projects/*/CLAUDE.md  # Remove project-specific configs
# Edit CLAUDE.md to remove personal details

git commit -m "Create shareable template"
git push origin template
```

### Using Someone Else's Configuration

```bash
# Clone their configuration
git clone https://github.com/theirusername/claude-config.git temp-claude

# Review their setup
cd temp-claude
cat CLAUDE.md

# Copy relevant parts to your configuration
cp -r temp-claude/rules/*.md ~/.claude/rules/
cp -r temp-claude/skills/* ~/.claude/skills/

cd ~/.claude
git add .
git commit -m "Import rules and skills from [source]"
```

## Troubleshooting

### "I accidentally committed sensitive data"

If you committed sensitive data (API keys, passwords):

```bash
# Remove the file from history (WARNING: rewrites history)
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch path/to/sensitive-file" \
  --prune-empty --tag-name-filter cat -- --all

# Force push (if already pushed to remote)
git push origin --force --all
```

**Better approach**: Revoke/rotate any exposed credentials immediately, then clean the repository.

### "Git says files are modified but I didn't change them"

This can happen with line ending differences:

```bash
# Configure Git to handle line endings
git config core.autocrlf input   # On Linux/Mac
git config core.autocrlf true    # On Windows
```

### "Conflicts when pulling from another machine"

```bash
# Pull and see conflicts
git pull

# View conflicting files
git status

# Edit conflicting files to resolve
# Then mark as resolved
git add <conflicted-file>
git commit -m "Resolve merge conflict: sync configurations from laptop"
```

## Advanced: Automated Sync

Create a script to automatically pull and push changes:

```bash
cat > ~/.claude/sync.sh << 'EOF'
#!/bin/bash
cd ~/.claude
git pull --rebase
if [ -n "$(git status --porcelain)" ]; then
    git add .
    git commit -m "Auto-sync: $(date -Iseconds)"
    git push
fi
EOF
chmod +x ~/.claude/sync.sh
```

Add to your shell profile:
```bash
# Add to ~/.bashrc or ~/.zshrc
alias claude-sync='~/.claude/sync.sh'
```

## Integration with Claude Code

Claude Code automatically reads from `~/.claude/CLAUDE.md` and project-specific `CLAUDE.md` files. Version
controlling these files allows you to:

- Track how your collaboration with Claude evolves
- Share effective patterns with teammates
- Maintain consistency across projects

Claude can help you manage this repository:

```
User: "Update my global CLAUDE.md to prefer functional programming patterns"
Claude: [reads ~/.claude/CLAUDE.md, makes changes, commits them]

User: "What changed in my Claude configuration last week?"
Claude: [runs git log, summarizes recent changes]
```

## Example Repository Structure

A well-organized `~/.claude` repository might look like:

```
~/.claude/
├── .git/
├── .gitignore
├── CLAUDE.md                          # Global instructions
├── README.md                          # Optional: document your setup
├── rules/
│   ├── crypto-operations.md           # Hash/token safety
│   ├── file-creation.md               # Prefer heredocs
│   └── security-review.md             # Security checklist
├── skills/
│   ├── git-commit/
│   │   └── SKILL.md
│   ├── troubleshoot/
│   │   └── SKILL.md
│   └── verify-change/
│       └── SKILL.md
└── projects/
    └── my-project-id/
        └── memory/
            └── MEMORY.md              # Project-specific memory
```

## Next Steps

1. **Start small**: Version control just your `CLAUDE.md` first
2. **Build gradually**: Add rules and skills as you develop them
3. **Share selectively**: Contribute useful patterns back to the community
4. **Iterate**: Use Claude Code to help refine your configuration over time

For more Claude Code resources and shareable configurations, see:
- [Clawed-Up Repository](https://github.com/tonywalker1/Clawed-Up) - Shareable Claude Code resources
- [Collaboration Guidelines](../guidelines/collaboration.md) - Framework for working with Claude Code

## Contributing

If you develop useful patterns or configurations, consider contributing them to the
[Clawed-Up repository](https://github.com/tonywalker1/Clawed-Up) to help others improve their Claude Code
workflows.
