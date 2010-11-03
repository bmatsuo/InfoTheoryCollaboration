FIGS=figs/
TARGET=hw2

# make pdf by default
all: ${TARGET}.pdf

# it doesn't really need the .dvi, but this way all the refs are right
%.pdf : %.dvi
	#epspdf ${FIGS}timeshift.eps
	pdflatex $*

#${TARGET}.bbl: $(TARGET).bib
#	latex  ${TARGET}.tex
#	bibtex ${TARGET}
#	@latex ${TARGET}.tex

#${TARGET}.dvi: ${TARGET}.bbl ${TARGET}.tex
${TARGET}.dvi: ${TARGET}.tex
	@latex ${TARGET}.tex

ps: ${TARGET}.ps

${TARGET}.ps: ${TARGET}.dvi
	@dvips -t a4 ${TARGET}.dvi

clean:
	rm -f ${TARGET}.{log,aux,ps,dvi,bbl,blg,log}
	rm -f ${FIGS}*.pdf

reallyclean: clean
	rm -f ${TARGET}.{ps,pdf}

.PHONY : ps all clean reallyclean
