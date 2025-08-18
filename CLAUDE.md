# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is `sd` (script directory), a tool for organizing and accessing shell scripts in a hierarchical directory structure. It allows users to organize scripts in logical directories and access them with convenient syntax like `sd dir script` instead of `~/sd/dir/script`.

## Code Architecture

The project consists of three main files:

1. `sd` - The main executable bash script that implements all functionality
2. `_sd` - Zsh completion script that provides tab completion with descriptions
3. `sd.plugin.zsh` - Zsh plugin integration file

### Core Components

- `__sd()` - Main function that handles argument parsing and command dispatch
- Special flag handlers: `__sd_help()`, `__sd_new()`, `__sd_edit()`, `__sd_cat()`, `__sd_which()`
- Path traversal logic for finding scripts in the directory hierarchy
- Template system for new script creation with `--new` flag
- Help system that extracts comments from scripts or reads `.help` files

### Key Features

- Directory-based script organization with fallback resolution
- Special arguments: `--help`, `--new`, `--edit`, `--cat`, `--which`, `--really`
- Template-based script creation with per-directory template support
- Zsh completion with description support
- Environment variable support (`SD_ROOT`, `SD_EDITOR`, `SD_CAT`)
- Context variable `SD` set to script directory during execution

## Development Environment

This is a pure bash project with no external dependencies beyond standard Unix tools. The project does not include formal testing infrastructure or build processes.

## Common Development Tasks

1. Modifying core functionality in the `sd` script
2. Updating completion behavior in `_sd`
3. Adding new special flags or modifying argument parsing
4. Improving help text extraction or formatting
5. Enhancing template system for script creation

Note that this is a simple, single-script project without formal build, test, or lint processes.