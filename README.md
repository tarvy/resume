# Resume

Generate resume outputs (DOCX, HTML, MD, PDF) from a single YAML source file.

## Quick Start

```bash
just generate
```

This generates all resume formats from `resume.yaml`.

## Source of Truth

**`resume.yaml`** is the single source of truth for all resume content. Edit this file to update your resume - never edit the generated output files directly.

Generated files:
- `TravisGlassResume.docx`
- `TravisGlassResume.html`
- `TravisGlassResume.md`
- `TravisGlassResume.pdf`

## Workspace Setup

### Prerequisites

- [uv](https://docs.astral.sh/uv/) - Python package manager
- [just](https://github.com/casey/just) - Command runner

Install on macOS:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
brew install just
```

### Install Dependencies

```bash
uv sync
```

This creates a `.venv/` directory and installs all dependencies from `pyproject.toml`.

## Available Commands

```bash
just generate    # Generate all resume formats from resume.yaml
```

## Project Structure

```
resume.yaml              # Source of truth - edit this file
convert_resume.py        # Conversion script
templates/               # HTML templates
pyproject.toml           # Python dependencies
justfile                 # Command definitions
```
