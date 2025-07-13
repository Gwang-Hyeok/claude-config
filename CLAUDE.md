# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Directory Structure

This is the Claude CLI configuration directory (`~/.claude`) containing:

- `projects/`: Session logs and project metadata for various repositories including NavCal, avikus-cpp-utility, cmems-data-sync, data-collect, draft-extractor, gfs-wave-tiledb, influx-to-s3-exporter, rpm-simulator, ship-performance-predictor, and vessel-forge
- `todos/`: Todo list persistence files for different Claude sessions
- `.credentials.json`: Authentication tokens and user subscription information
- `ide/`: IDE integration configurations
- `statsig/`: Analytics and feature flag configurations

## Working with Projects

The projects directory contains JSONL files that track Claude's interactions with different codebases. Each project directory is named after its filesystem path (with slashes replaced by dashes) and contains session files identified by UUIDs.

## Session Management

Todo lists are persisted per session in the `todos/` directory, allowing Claude to maintain context and track progress across multiple interactions within the same project session.

## Configuration Files

- `.credentials.json` contains OAuth tokens for Claude API access
- The directory structure supports multiple concurrent project sessions
- Session files are in JSONL format for incremental logging

## Custom Commands

This configuration includes custom slash commands in the `commands/` directory:

- `/test` - Run all unit tests and report results
- `/fix` - Automated bug detection and fixing with strict type checking (mypy, ruff)
- `/gsave` - Create well-formatted Git commits with conventional commit messages and emoji
- `/refactor` - Code refactoring assistance
- `/explain` - Code explanation and documentation
- `/audit` - Code auditing and security analysis
- `/docs` - Documentation generation
- `/test_gen` - Test generation utilities
- `/review_gh` - GitHub review workflows

## Git Workflow

The `/gsave` command enforces conventional commit format with emoji:
- Always runs pre-commit checks (linting, building, documentation generation)
- Uses conventional commit types (feat, fix, docs, style, refactor, perf, test, chore)
- Includes appropriate emoji for each commit type
- Automatically stages all modified files before committing

## Development Commands

Quality assurance commands available:
- `/fix` - Comprehensive error fixing with mypy type checking and ruff linting
- `/test` - Execute test suites
- `/audit` - Security and code quality auditing

## Notable Projects

Based on the project directories, this workspace appears to focus on:
- Maritime/shipping applications (NavCal, vessel-forge, ship-performance-predictor, rpm-simulator)
- Data processing and synchronization (cmems-data-sync, data-collect, influx-to-s3-exporter)
- Geospatial data (gfs-wave-tiledb)
- C++ utilities (avikus-cpp-utility)