TEXS = $(wildcard *.tex)
PDFS = $(TEXS:%.tex=%.pdf)

.PHONY: all clean

.DEFAULT_GOAL	:= all

ifndef VERBOSE
.SILENT:

QUIET	?= --quiet
endif

LATEXMK_FLAGS := -pdf -dvi-

all: $(PDFS)

$(PDFS): $(TEXS)

%.pdf: %.tex clean
	latexmk $(QUIET) $(LATEXMK_FLAGS) -f $<

clean:
	latexmk $(QUIET) $(LATEXMK_FLAGS) -c

distclean: clean
	rm -f $(PDFS) *.div
