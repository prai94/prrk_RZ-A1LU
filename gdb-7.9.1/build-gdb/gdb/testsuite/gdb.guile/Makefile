VPATH = ../../../../gdb/testsuite/gdb.guile
srcdir = ../../../../gdb/testsuite/gdb.guile

EXECUTABLES =

MISCELLANEOUS =

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o *.ci
	-rm -f *.dwo *.dwp
	-rm -f core $(EXECUTABLES) $(MISCELLANEOUS)

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log gdb.log gdb.sum
