# This is a full text containing all sheets
FINAL_TARGET=ufpa_tcc
OUT_DIR=../output
OUTPUT=$(OUT_DIR)/$(FINAL_TARGET).pdf
TEX_TARGET=$(FINAL_TARGET).tex

all: $(TEX_TARGET)
	TEXINPUTS="./config:../output/:$(TEXTINPUTS)" pdflatex -output-directory=$(OUT_DIR) $(FINAL_TARGET)
	cd $(OUT_DIR); BIBINPUTS="../src/bib/" BSTINPUTS="../src/bib/" bibtex $(FINAL_TARGET); cd -
	TEXINPUTS="./config:../output/:$(TEXTINPUTS)" pdflatex -output-directory=$(OUT_DIR) $(FINAL_TARGET)
	TEXINPUTS="./config:../output/:$(TEXTINPUTS)" pdflatex -output-directory=$(OUT_DIR) $(FINAL_TARGET)

view: $(OUTPUT)
	evince $(OUTPUT)

clean:
	cd $(OUT_DIR); rm -f *.aux *.log *.lot *.lof *.toc *.dvi *.bbl *.blg *.out; cd -
