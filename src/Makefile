# -shell-escape est requis par minted (appel externe à Pygments)
LATEX = latexmk -pdf -shell-escape -interaction=nonstopmode

all: report

report: ; $(LATEX) main.tex

clean:
	latexmk -C main.tex

.PHONY: all report clean
