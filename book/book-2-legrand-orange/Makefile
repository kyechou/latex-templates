#
# Makefile
#

TARGETS = main

TEXFILES = $(wildcard *.tex)
PDFS = $(addsuffix .pdf,$(TARGETS))

all: $(PDFS)

%.pdf: %.tex $(TEXFILES) bibliography.bib
	pdflatex $<
	makeindex $< -s StyleInd.ist
	biber $*
	pdflatex $<
	pdflatex $<

clean:
	-@rm -f *.aux *.bbl *.bcf *.blg *.idx *.ilg *.ind *.log *.out *.pdf *.ptc *.run.xml *.toc

.PHONY: all clean
