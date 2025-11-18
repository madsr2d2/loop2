# AGENTS.md

## Dependencies
- **Install marker-pdf**: `pip install 'marker-pdf[all]'`
- **Optional mdformat**: `pip install mdformat` (for pretty-printing)

## Build Commands
- **Python syntax check**: `python -m py_compile pdf2md.py`
- **LaTeX build**: `pdflatex tex/main.tex` or `latexmk -pdf tex/main.tex`
- **PDF to Markdown**: `python pdf2md.py input.pdf`

## Test Commands
- **Help**: `python pdf2md.py --help`
- **Process PDF**: `python pdf2md.py hardnut.pdf --outdir md_out`
- **Process existing MD**: `python pdf2md.py md_out/hardnut/hardnut.md --backup`
- **Lint**: `flake8 pdf2md.py` or `black --check pdf2md.py`
- **Type check**: `mypy pdf2md.py`

## Code Style Guidelines
- **Imports**: Standard library first, then third-party; use `from __future__ import annotations`
- **Naming**: `snake_case` for functions/variables, `UPPER_CASE` for constants, `PascalCase` for classes
- **Types**: Use type hints; `Path` for files; `list[str]`, `tuple[bool, str]` for complex types
- **Formatting**: 4-space indent, ~100 char lines, descriptive names, docstrings for functions
- **Error Handling**: try/except for external ops, `RuntimeError` for missing deps, `sys.exit()` in main
- **Structure**: Focused functions, module-level regex constants, pipeline processing