VPATH = ../../../../gdb/testsuite/gdb.opencl
srcdir = ../../../../gdb/testsuite/gdb.opencl

EXECUTABLES = callfuncs datatypes vec_comps convs_casts operators

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o a.out core corefile gcore.test
	-rm -f *.dwo *.dwp
	-rm -f $(EXECUTABLES)

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
