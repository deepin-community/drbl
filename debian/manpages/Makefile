TARGETS = $(shell for f in *.xml; do section=$$(grep "ENTITY dhsection" $$f| sed -n 's/[^0-9]*\([1-8]\).*/\1/ p'); g=$${f/.xml/}; echo $$g.$${section}; done)

XP     = xsltproc --nonet --param man.charmap.use.subset "0"
DB2MAN = /usr/share/sgml/docbook/stylesheet/xsl/docbook-xsl/manpages/docbook.xsl

all: $(TARGETS)

test: 
	@echo $(TARGETS)

%.1: %.xml
	$(XP) $(DB2MAN) $<

%.8: %.xml
	$(XP) $(DB2MAN) $<

