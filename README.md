# Claude CLI Configuration

A comprehensive configuration repository for Claude Code CLI with custom commands, enhanced documentation, and streamlined development workflows.

## 🎯 Overview

This repository contains a complete Claude CLI configuration setup with:

- **9 Custom Commands**: Specialized slash commands for development workflows
- **Enhanced Documentation**: Comprehensive guides and command references  
- **Git Workflow Integration**: Conventional commits with emoji and clean formatting
- **Development Tools**: Automated fixing, testing, auditing, and refactoring capabilities

## 📁 Repository Structure

```
~/.claude/
├── CLAUDE.md                 # Claude Code guidance and architecture documentation
├── README.md                 # This comprehensive setup guide
├── .gitignore               # Git exclusions for sensitive data
├── commands/                # Custom slash command definitions
│   ├── audit.md            # Security and performance auditing
│   ├── docs.md             # Documentation generation
│   ├── explain.md          # Code explanation and analysis
│   ├── fix.md              # Automated bug detection and fixing
│   ├── gsave.md            # Git commit with conventional format
│   ├── refactor.md         # Smart code refactoring suggestions
│   ├── review_gh.md        # Comprehensive code review
│   ├── test.md             # Test execution and reporting
│   └── test_gen.md         # Intelligent test generation
├── ide/                    # IDE integration configurations
├── statsig/               # Analytics and feature flags
├── projects/              # Project session logs (gitignored)
├── todos/                 # Todo persistence files (gitignored)
└── .credentials.json      # Authentication tokens (gitignored)
```

## 🚀 Quick Setup

### 1. Prerequisites

Ensure you have Claude CLI installed:

```bash
# Install Claude CLI (if not already installed)
npm install -g @anthropic/claude-cli

# Verify installation
claude --version
```

### 2. Repository Setup

Clone and deploy this configuration:

```bash
# Clone the repository
git clone https://github.com/Gwang-Hyeok/claude-config.git
cd claude-config

# Backup existing configuration (if any)
mv ~/.claude ~/.claude.backup.$(date +%Y%m%d)

# Deploy configuration
cp -r . ~/.claude/
cd ~/.claude
```

### 3. Authentication

Authenticate with Claude CLI:

```bash
claude auth login
```

### 4. Verification

Test the setup:

```bash
# Verify Claude CLI recognizes the configuration
claude --help

# Test a custom command
claude /test --help
```

## 🛠️ Custom Commands

### Development & Quality Assurance

| Command | Purpose | Usage |
|---------|---------|-------|
| `/fix` | Automated bug detection and fixing with mypy/ruff | `/fix`, `/fix --mypy-only` |
| `/test` | Run all unit tests and report results | `/test` |
| `/audit` | Security and performance analysis | `/audit`, `/audit --security-only` |
| `/review_gh` | Comprehensive code review | `/review` |

### Documentation & Explanation

| Command | Purpose | Usage |
|---------|---------|-------|
| `/docs` | Auto-generate comprehensive documentation | `/docs`, `/docs --readme-only` |
| `/explain` | Deep code explanation and analysis | `/explain`, `/explain --function name` |

### Code Enhancement

| Command | Purpose | Usage |
|---------|---------|-------|
| `/refactor` | Smart code refactoring suggestions | `/refactor`, `/refactor --files src/` |
| `/test_gen` | Intelligent test generation | `/test-gen`, `/test-gen --unit-only` |

### Git Workflow

| Command | Purpose | Usage |
|---------|---------|-------|
| `/gsave` | Conventional commits with emoji formatting | `/gsave`, `/gsave --no-verify` |

## 💡 Usage Examples

### Quality Assurance Workflow

```bash
# 1. Fix code issues
claude /fix

# 2. Run comprehensive tests
claude /test

# 3. Security and performance audit
claude /audit

# 4. Code review
claude /review

# 5. Clean commit
claude /gsave
```

### Documentation Workflow

```bash
# Generate comprehensive documentation
claude /docs

# Explain complex code sections
claude /explain --function calculateMetrics

# Update README only
claude /docs --readme-only
```

### Refactoring Workflow

```bash
# Analyze refactoring opportunities
claude /refactor

# Generate comprehensive tests
claude /test-gen

# Apply fixes and improvements
claude /fix

# Commit changes
claude /gsave
```

## ⚙️ Configuration Details

### Command Behavior

- **Pre-commit Checks**: `/gsave` automatically runs linting, builds, and documentation updates
- **Conventional Commits**: Enforces `type: description` format with appropriate emoji
- **Clean Attribution**: Removes AI-generated content attributions by default
- **Atomic Commits**: Encourages single-purpose, focused commits

### Git Workflow Integration

The `/gsave` command provides:

- Automatic staging of modified files
- Pre-commit quality checks
- Conventional commit message formatting
- Emoji categorization (🐛 fix, ✨ feat, 📝 docs, etc.)
- Clean attribution (no AI signatures unless needed)

### Security Features

- Excludes sensitive files (`.credentials.json`, session data)
- Includes security auditing via `/audit` command
- Implements secure development practices

## 🔧 Troubleshooting

### Configuration Issues

**Claude CLI doesn't recognize commands:**

```bash
# Check directory permissions
chmod 755 ~/.claude
chmod 644 ~/.claude/*.md ~/.claude/commands/*.md

# Verify Claude CLI version
claude --version

# Check configuration files
ls -la ~/.claude
```

**Commands not found:**

```bash
# Ensure commands directory exists
ls ~/.claude/commands/

# Verify command file format
claude /test --help
```

### Authentication Issues

**Login problems:**

```bash
# Clear existing authentication
claude auth logout

# Re-authenticate
claude auth login

# Verify authentication
claude auth status
```

**Permission errors:**

```bash
# Fix directory permissions
chmod -R 755 ~/.claude
chown -R $USER ~/.claude
```

### Performance Issues

**Slow command execution:**

```bash
# Clear session cache
rm -rf ~/.claude/projects/*
rm -rf ~/.claude/todos/*

# Restart Claude CLI
claude --version
```

## 🔄 Maintenance

### Updating Configuration

```bash
cd ~/.claude

# Pull latest changes
git pull origin main

# Backup current settings
cp .credentials.json .credentials.json.backup

# Apply updates (preserve credentials)
git reset --hard HEAD
cp .credentials.json.backup .credentials.json
```

### Syncing Changes

```bash
cd ~/.claude

# Stage configuration changes
git add commands/ *.md

# Commit with clean format
claude /gsave

# Push updates
git push origin main
```

### Backup Strategy

```bash
# Create complete backup
tar -czf claude-config-backup-$(date +%Y%m%d).tar.gz ~/.claude

# Exclude sensitive data for sharing
tar --exclude='.credentials.json' --exclude='projects/' --exclude='todos/' \
    -czf claude-config-share-$(date +%Y%m%d).tar.gz ~/.claude
```

## 📋 Best Practices

### Development Workflow

1. **Quality First**: Always run `/fix` and `/test` before committing
2. **Clean Commits**: Use `/gsave` for consistent, well-formatted commits
3. **Documentation**: Keep documentation updated with `/docs`
4. **Security**: Regular audits with `/audit`

### Command Usage

1. **Incremental Development**: Use commands iteratively for best results
2. **Focused Tasks**: Each command should address specific concerns
3. **Quality Gates**: Don't skip pre-commit checks
4. **Clean Attribution**: Maintain professional commit history

### Configuration Management

1. **Version Control**: Track configuration changes in git
2. **Environment Separation**: Use different configurations for different contexts
3. **Security**: Never commit sensitive authentication data
4. **Backup**: Regular backups of working configurations

## 🆘 Support

### Documentation

- [Claude CLI Official Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Command Reference](./commands/)
- [Architecture Guide](./CLAUDE.md)

### Community

- Create issues for bugs or feature requests
- Contribute improvements via pull requests
- Share configuration enhancements

### Professional Support

For enterprise or professional support needs, consult the [Claude CLI documentation](https://docs.anthropic.com/en/docs/claude-code) for official support channels.

---

**Last Updated**: 2025-07-13  
**Configuration Version**: 2.0  
**Compatible Claude CLI**: 1.0+
