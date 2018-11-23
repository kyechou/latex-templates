all: report.pdf

%.pdf: %.tex
	xelatex $<
	bibtex $(basename $<)
	xelatex $<
	xelatex $<

clean:
	-@rm -f *.aux *.log *.toc *.out *.bbl *.blg *.pdf

.PHONY: all clean
