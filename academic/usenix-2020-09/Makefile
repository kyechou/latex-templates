#
# Makefile
#

PDF = paper.pdf

all: ${PDF}

%.pdf: %.tex usenix.sty
	pdflatex $(notdir $<)
	- bibtex $(notdir $(basename $<))
	pdflatex $(notdir $<)
	pdflatex $(notdir $<)
	while ( grep -q '^LaTeX Warning: Label(s) may have changed' $(basename $<).log) \
		do pdflatex $(notdir $<); done

docclean:
	$(RM) *.log *.aux \
	*.cfg *.glo *.idx *.toc \
	*.ilg *.ind *.out *.lof \
	*.lot *.bbl *.blg *.gls *.cut *.hd \
	*.dvi *.ps *.thm *.tgz *.zip *.rpi \
	*.fdb_latexmk *.fls *.xdv *.bak *.tmp \
	*.synctex.gz

clean: docclean

distclean: clean
	$(RM) ${PDF}

.PHONY: all docclean clean distclean
