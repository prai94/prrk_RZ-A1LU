VPATH = ../../../../../gdb/testsuite/gdb.hp/gdb.objdbg
srcdir = ../../../../../gdb/testsuite/gdb.hp/gdb.objdbg

EXECUTABLES = objdbg01/test0 objdbg01/test1 objdbg02/test \
	objdbg03/test objdbg04/test0 objdbg04/test1

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
	-rm -f *~ objdbg*/*.o objdbg*/*.ci
	-rm -f *.dwo *.dwp
	-rm -f core $(EXECUTABLES)

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
