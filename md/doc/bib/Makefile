BIB2BIB = bib2bib \
	-c '$$key <> "R:Dalgaard:2002"' \
	-c '$$key <> "R:Ligges:2005"' \
	-c '$$key <> "R:Ligges:2007"' \
	-c '$$key <> "R:Pfaff:2006"' \
	-c '$$key <> "R:Albert:2007"' \
	-s 'year' -r -s 'author' \
	--no-comment

## Put in TMPDIR=. to avoid openout_any = p madness in current versions of
## TeXlive (see e.g. http://www.lri.fr/~filliatr/bibtex2html/).
BIBTEX2HTML = TMPDIR=. bibtex2html -u -noheader -nodoc \
	  --named-field publisherurl "Publisher Info" \
	  --doi-prefix https://doi.org/

.SUFFIXES:
.SUFFIXES: .html .bib

all: R-publications.html R-books.html R-other.html

R-publications.html: Makefile R.bib R-publications-head.html
	@$(BIB2BIB) R.bib > $(*F).bib
	@$(BIBTEX2HTML) $(*F).bib
	@mv $@ $@.in
	@cat $(*F)-head.html > $@
	@cat $@.in >> $@
	@echo "</body></html>" >> $@
	@rm $@.in

R-books.html: Makefile R.bib R-books-head.html
	@$(BIB2BIB) -c '$$type = "BOOK"' R.bib > $(*F).bib
	@$(BIBTEX2HTML) -rawurl -s Rweb \
	  --named-field orderinfo "Discount Info" \
	  $(*F).bib
	@mv $@ $@.in
	@cat $(*F)-head.html > $@
	@cat $@.in >> $@
	@echo "</body></html>" >> $@
	@rm $@.in

R-other.html: Makefile R.bib R-other-head.html
	@$(BIB2BIB) -c '$$type <> "BOOK"' R.bib > $(*F).bib
	@$(BIBTEX2HTML) -rawurl $(*F).bib
	@mv $@ $@.in
	@cat $(*F)-head.html > $@
	@cat $@.in >> $@
	@echo "</body></html>" >> $@
	@rm $@.in


R-jabref.html: R.bib jabref-pref.xml
##	jabref -n -p jabref-pref.xml -o R-jabref.html,tablerefsabsbib R.bib
	jabref -n -p jabref-pref.xml -o R-jabref.html,jr R.bib
##	jabref -n -p jabref-pref.xml -o $@,seminarhtml $<


clean:
	@rm -f R-bib.html \
          R-publications.bib R-books.bib R-other.bib \
	  R-publications.html R-publications_bib.html \
	  R-books.html R-books_bib.html \
	  R-other.html R-other_bib.html \
	  R_bib.html R.html
