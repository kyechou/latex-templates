#
# Makefile for acmart package
#
# This file is in public domain
#
# $Id: Makefile,v 1.10 2016/04/14 21:55:57 boris Exp $
#

PDF = main.pdf

all: ${PDF}

%.pdf: %.tex acmart.cls ACM-Reference-Format.bst
	pdflatex $(notdir $<)
	- bibtex $(notdir $(basename $<))
	pdflatex $(notdir $<)
	pdflatex $(notdir $<)
	while ( grep -q '^LaTeX Warning: Label(s) may have changed' $(basename $<).log) \
		do pdflatex $(notdir $<); done

%.cls: %.ins %.dtx
	pdflatex $<

.PRECIOUS: acmart.cfg acmart.cls

docclean:
	$(RM) *.log *.aux \
	*.cfg *.glo *.idx *.toc \
	*.ilg *.ind *.out *.lof \
	*.lot *.bbl *.blg *.gls *.cut *.hd \
	*.dvi *.ps *.thm *.tgz *.zip *.rpi

clean: docclean
	$(RM) acmart.cls

distclean: clean
	$(RM) ${PDF}

.PHONY: all docclean clean distclean
