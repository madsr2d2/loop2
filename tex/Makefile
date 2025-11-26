.PHONY: all clean build

all: build clean

build:
	xelatex main.tex
	bibtex main
	xelatex main.tex
	xelatex main.tex

clean:
	rm -f *.aux *.log *.blg *.toc *.out *.fdb_latexmk *.fls main-blx.bib

help:
	@echo "Available targets:"
	@echo "  all    - Build and clean"
	@echo "  build  - Build document only"
	@echo "  clean  - Clean auxiliary files"
	@echo "  help   - Show this help"