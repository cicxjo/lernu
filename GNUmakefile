LANGUAGE ?= en

COURSES=$(wildcard courses/*.txt)
TSV=$(subst courses,tsv,$(COURSES))
CARDS=$(subst tsv,cards,$(TSV))

all: $(CARDS)

$(TSV): $(COURSES)
	mkdir -p tsv
	./scraper "$(LANGUAGE)" < $< > $@

$(CARDS): $(TSV)
	mkdir -p cards
	./filter < $< > $@

clean:
	rm -f -- $(TSV)
	rm -f -- $(CARDS)

.PHONY: all clean
