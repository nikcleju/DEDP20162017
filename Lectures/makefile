
all: pdf html

pdf:
	jupyter nbconvert --to pdf *.ipynb
	mv *.pdf export_pdf

html:
	jupyter nbconvert --to slides *.ipynb
	mv *.html export_html

PANDOC = pandoc
IFORMAT = markdown

md0pdf: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -o 00_Introduction.pdf  00_Introduction.md 

md1pdf: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 01_ErrorControlCoding.pdf --slide-level 3 --include-in-header macros.md  01_ErrorControlCoding.md 

mdw2pdf:
	pweave -f pandoc 02_RandomSignals.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 02_RandomSignals.pdf --slide-level 3 --include-in-header macros.md  02_RandomSignals.md 
	gnome-open 02_RandomSignals.pdf
	
mdw3pdf:
	pweave -f pandoc 03_SignalDetectionTheory.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 03_SignalDetectionTheory.pdf --slide-level 3 --include-in-header macros.md  03_SignalDetectionTheory.md 
	gnome-open 03_SignalDetectionTheory.pdf

prep:
	$(PANDOC) -s -f markdown -o ../PreparationForExam.pdf ../PreparationForExam.md
