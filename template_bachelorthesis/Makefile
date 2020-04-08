LATEX=latex
PDFLATEX=pdflatex
BIBTEX=bibtex

TARGET=bachelorthesis

.PHONY: all clean archive zip pdf fullpdf bibtex

all: fullpdf

bibtex:
	${BIBTEX} ${TARGET}

pdf:
	${PDFLATEX} ${TARGET}

fullpdf:
	make pdf
	make bibtex
	make pdf
	make pdf


zip archive:
	make distclean
	make fullpdf
	make clean
	zip -r  masterthesis.zip * -x "*/.svn*"

clean:
	ls | egrep "*.lot|.aux|*.toc|*.lof|*.out|*~|*.bbl|*.blg|*.log|*.zip|*.backup" | xargs rm -f

distclean:
	make clean
	ls | egrep "*.pdf|*.dvi|*.ps" | xargs rm -f	