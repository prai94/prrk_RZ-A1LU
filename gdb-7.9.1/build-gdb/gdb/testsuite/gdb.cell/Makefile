VPATH = ../../../../gdb/testsuite/gdb.cell
srcdir = ../../../../gdb/testsuite/gdb.cell

EXECUTABLES = break bt coremaker data mem-access size

SPU_EXECUTABLES = break-spu bt-spu bt2-spu coremaker-spu data-spu \
		  ea-cache-spu ea-standalone ea-test mem-access-spu size-spu

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o a.out core corefile gcore.test
	-rm -f *.dwo *.dwp
	-rm -f $(EXECUTABLES) $(SPU_EXECUTABLES)

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
