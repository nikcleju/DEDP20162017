
all: pdf html

pdf:
	jupyter nbconvert --to pdf *.ipynb
	mv *.pdf export_pdf

html:
	jupyter nbconvert --to slides *.ipynb
	mv *.html export_html
