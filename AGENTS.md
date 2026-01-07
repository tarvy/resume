# Repository Guidelines

## Project Structure & Module Organization
- `resume.yaml` is the single source of truth for content (JSON-compatible YAML). Edit this file only.
- `convert_resume.py` renders outputs from the manifest.
- `templates/` contains HTML templates (`resume.html.tmpl`, `resume.embed.tmpl`).
- Generated outputs live at repo root: `TravisGlassResume.docx`, `TravisGlassResume.html`, `TravisGlassResume.md`, `TravisGlassResume.pdf`.

## Build, Test, and Development Commands
- `uv sync` installs Python dependencies into `.venv/`.
- `just generate` runs the full conversion pipeline (DOCX/HTML/MD/PDF).
- `uv run python convert_resume.py` runs the generator directly (same as `just generate`).
- `uv run resume` uses the console script from `pyproject.toml` (optional).

## Coding Style & Naming Conventions
- Python uses 4-space indentation and PEP 8 naming (snake_case for functions, constants in ALL_CAPS).
- `resume.yaml` uses JSON-style syntax with 2-space indentation and double quotes; keep it JSON-compatible.
- Template filenames remain `resume.*.tmpl`; add new templates in `templates/` if needed.

## Testing Guidelines
- No automated test suite is configured.
- Validate changes by running `just generate` and inspecting the outputs for layout and content accuracy.

## Commit & Pull Request Guidelines
- Commit messages are short, capitalized, present tense sentences ending with a period (e.g., “Updates education schema to be an object.”).
- PRs should include: a brief summary, what changed in `resume.yaml`, and regenerated artifacts (or a note explaining why not).
- If visual changes are expected, include screenshots of the HTML output or attach the PDF.

## Notes for Contributors
- Do not edit generated files directly; always update `resume.yaml` and re-run generation.
- Keep dependencies aligned with `pyproject.toml`; use `uv sync` after changes.
