VPATH = ../../../../../gdb/testsuite/gdb.hp/gdb.base-hp
srcdir = ../../../../../gdb/testsuite/gdb.hp/gdb.base-hp

EXECUTABLES = dollar hwwatchbus.bak pxdb reg reg-pa64 \
	so-thresh genso-thresh sized-enum

MISCELLANEOUS = so-thresh.c so-thresh.lopt so-thresh.make.out \
	lib*-so-thresh.*

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
	-rm -f $(MISCELLANEOUS)

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
