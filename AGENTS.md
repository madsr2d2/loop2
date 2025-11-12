# AGENTS.md

## Build Commands
- **Python syntax check**: `python -m py_compile pdf2md.py`
- **LaTeX build**: `pdflatex tex/main.tex` or `latexmk -pdf tex/main.tex`
- **PDF to Markdown**: `python pdf2md.py input.pdf`

## Test Commands
- **Run script help**: `python pdf2md.py --help`
- **Basic functionality test**: `python pdf2md.py --backup test.md` (if test.md exists)

## Code Style Guidelines

### Imports
- Standard library imports first, then third-party
- Use `from __future__ import annotations` for type hints
- Group imports logically with blank lines between groups

### Naming Conventions
- Functions: `snake_case` (e.g., `normalize_headings`)
- Variables: `snake_case` (e.g., `out_chunks`, `is_fenced`)
- Constants: `UPPER_CASE` with underscores (e.g., `_BR_TOKEN`)
- Classes: `PascalCase` (not used in this codebase)

### Types and Type Hints
- Use type hints for function parameters and return values
- Use `Path` from pathlib for file paths
- Use `list[str]`, `tuple[bool, str]` for complex types

### Formatting
- 4-space indentation
- Line length: ~100 characters
- Use descriptive variable names
- Functions should have docstrings explaining purpose

### Error Handling
- Use try/except blocks for external operations (subprocess, file I/O)
- Raise `RuntimeError` for missing dependencies
- Use `sys.exit()` with appropriate codes in main()

### Code Structure
- Separate concerns into focused functions
- Use regex patterns as module-level constants
- Process text in pipelines with clear stages