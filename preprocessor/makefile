
PACKAGE = ppx_package

INSTALL = META \
	_build/src/$(PACKAGE).native

OCB_FLAGS = -use-ocamlfind -I src -I test

OCB = ocamlbuild $(OCB_FLAGS)

all: ppx

.PHONY: ppx clean

ppx:
	$(OCB) $(PACKAGE).native

clean:
	$(OCB) -clean

# opam

.PHONY: install remove up down

install: all
	ocamlfind install $(PACKAGE) $(INSTALL)

remove:
	ocamlfind remove $(PACKAGE)

up: clean all
	opam pin add $(PACKAGE) . -n -y
	opam install $(PACKAGE) --verbose

down:
	opam remove $(PACKAGE)
	opam pin remove $(PACKAGE)
