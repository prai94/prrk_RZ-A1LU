VPATH = ../../../../gdb/testsuite/gdb.xml
srcdir = ../../../../gdb/testsuite/gdb.xml

PROGS =

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *.ci *.o $(OBJS) $(PROGS) *~ core
	-rm -f *.dwo *.dwp

distclean maintainer-clean realclean: clean
	-rm -f Makefile gdb.log gdb.sum
