# Command Reference

This document provides a comprehensive reference for all available commands in our platform.

## Table of Contents

- [Basic Commands](#basic-commands)
- [Build Commands](#build-commands)
- [Deployment](#deployment)
- [Configuration](#configuration)
- [Utilities](#utilities)

## Basic Commands

### `serve`

Start the development server with live reloading.

```bash
mkdocs serve
```

**Options:**
- `-a`, `--dev-addr` - IP address and port to serve documentation from (default: localhost:8000)
- `-s`, `--strict` - Enable strict mode and abort on warnings
- `-q`, `--quiet` - Silence warnings

### `build`

Build the documentation site.

```bash
mkdocs build
```

**Options:**
- `-c`, `--clean` - Remove old files from the site directory before building
- `-s`, `--strict` - Enable strict mode and abort on warnings
- `-q`, `--quiet` - Silence warnings

## Build Commands

### `build --clean`

Clean the site directory before building.

```bash
mkdocs build --clean
```

### `build --strict`

Enable strict mode, causing the build to fail on warnings.

```bash
mkdocs build --strict
```

## Deployment

### `gh-deploy`

Deploy your documentation to GitHub Pages.

```bash
mkdocs gh-deploy
```

**Options:**
- `-c`, `--clean` - Remove old files from the site directory before building
- `-m`, `--message` - Commit message (default: "Deployed {sha} with MkDocs version: {version}")
- `-f`, `--force` - Force the push to the repository

## Configuration

### `new`

Create a new MkDocs project.

```bash
mkdocs new [project-name]
```

### `version`

Show the MkDocs version.

```bash
mkdocs --version
```

## Utilities

### `json`

Print project context in JSON format.

```bash
mkdocs json
```

### `config`

Print the loaded configuration.

```bash
mkdocs config
```

## Exit Codes

| Code | Description |
|------|-------------|
| 0    | Success     |
| 1    | Build Error |
| 2    | CLI Error   |
| 3    | Config Error|

## Examples

### Serve with Custom Port

```bash
mkdocs serve -a localhost:8080
```

### Build with Clean and Strict Mode

```bash
mkdocs build --clean --strict
```

## Next Steps

- [Getting Started](../getting-started/installation.md)
- [Configuration Guide](../getting-started/configuration.md)
- [Writing Documentation](../guide/writing.md)
