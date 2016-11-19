
all: pdf html

pdf:
	jupyter nbconvert --to pdf *.ipynb
	mv *.pdf export_pdf

html:
	jupyter nbconvert --to slides *.ipynb
	mv *.html export_html

PANDOC = pandoc
IFORMAT = markdown
mdpdf: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 01_ErrorControlCoding.pdf --slide-level 3 --include-in-header macros.md  01_ErrorControlCoding.md 

mdwpdf:
	pweave -f pandoc 02_RandomSignals.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 02_RandomSignals.pdf --slide-level 3 --include-in-header macros.md  02_RandomSignals.md 
	gnome-open 02_RandomSignals.pdf
