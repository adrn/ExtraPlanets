LATEX       = TEXINPUTS=..:${TEXINPUTS} pdflatex
BASH        = bash -c
ECHO        = echo
RM          = rm -rf

TMP_SUFFS   = aux bbl blg log dvi ps eps
RM_TMP      = ${RM} $(foreach suff, ${TMP_SUFFS}, *.${suff})

CHECK_RERUN = grep Rerun $*.log

ALL_FILES = proposal.pdf biosketch_hogg.pdf biosketch_dfm.pdf \
			biosketch_apw.pdf currentsupport_dfm.pdf

all: ${ALL_FILES}

%.pdf: %.tex
	${LATEX} $<
	( ${CHECK_RERUN} && ${LATEX} $< ) || echo "Done."
	( ${CHECK_RERUN} && ${LATEX} $< ) || echo "Done."

clean:
	${RM_TMP} ${ALL_FILES}
