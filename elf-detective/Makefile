BASENAME = elf-detective
PDF = $(addsuffix .pdf, $(BASENAME))
DVI = $(addsuffix .dvi, $(BASENAME))
TEX = $(addsuffix .tex, $(BASENAME))
BIB = $(addsuffix .bib, $(BASENAME))
LATEX = latex
PDFLATEX = pdflatex
BIBTEX = bibtex

.PHONY: all clean

all: $(PDF)

$(DVI): $(TEX) $(BIB) sections/
	$(LATEX) $<
	$(BIBTEX) $(BASENAME)
	# Twice, so TOC is also updated
	$(LATEX) $<
	$(LATEX) $<

$(PDF): $(TEX) $(BIB) sections/
	$(PDFLATEX) $<
	$(BIBTEX) $(BASENAME)
	# Twice, so TOC is also updated
	$(PDFLATEX) $<
	$(PDFLATEX) $<

clean:
	-rm -f *~ *.aux *.log *.blg *.bbl *.out
