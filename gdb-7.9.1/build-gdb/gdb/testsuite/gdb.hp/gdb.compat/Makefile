VPATH = ../../../../../gdb/testsuite/gdb.hp/gdb.compat
srcdir = ../../../../../gdb/testsuite/gdb.hp/gdb.compat

EXECUTABLES = xdb xdb-test

all:
	@echo "Nothing to be done for all..."

info:
install-info:
dvi:
install:
uninstall: force
installcheck:
check:

clean mostlyclean:
	-rm -f *~ *.o *.ci
	-rm -f *.dwo *.dwp
	-rm -f core $(EXECUTABLES)

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
