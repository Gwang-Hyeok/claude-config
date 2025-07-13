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

## Notable Projects

Based on the project directories, this workspace appears to focus on:
- Maritime/shipping applications (NavCal, vessel-forge, ship-performance-predictor, rpm-simulator)
- Data processing and synchronization (cmems-data-sync, data-collect, influx-to-s3-exporter)
- Geospatial data (gfs-wave-tiledb)
- C++ utilities (avikus-cpp-utility)