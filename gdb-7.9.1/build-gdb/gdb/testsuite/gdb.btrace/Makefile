VPATH = ../../../../gdb/testsuite/gdb.btrace
srcdir = ../../../../gdb/testsuite/gdb.btrace

EXECUTABLES   = enable function_call_history instruction_history tailcall \
  exception unknown_functions record_goto delta finish next nexti step \
  stepi multi-thread-step rn-dl-bind data

MISCELLANEOUS =

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	rm -f *~ *.o *.x *.ci *.sl a.out core
	rm -f *.dwo *.dwp
	rm -f $(EXECUTABLES) $(MISCELLANEOUS)

distclean maintainer-clean realclean: clean
	rm -f Makefile config.status config.log site.* gdb.log gdb.sum
