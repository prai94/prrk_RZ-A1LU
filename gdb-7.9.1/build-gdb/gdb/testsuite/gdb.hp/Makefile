VPATH = ../../../../gdb/testsuite/gdb.hp
srcdir = ../../../../gdb/testsuite/gdb.hp

SUBDIRS = gdb.aCC gdb.base-hp gdb.compat gdb.defects gdb.objdbg

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
	-rm -f *~ core *.o
	-rm -f *.dwo *.dwp
	if [ x"${SUBDIRS}" != x ] ; then \
	    for dir in ${SUBDIRS}; \
	    do \
		    echo "$$dir:"; \
		    if [ -d $$dir ]; then \
			    (cd $$dir; $(MAKE) clean); \
		    fi; \
	    done ; \
	else true; fi

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
	if [ x"${SUBDIRS}" != x ] ; then \
	    for dir in ${SUBDIRS}; \
	    do \
		    echo "$$dir:"; \
		    if [ -d $$dir ]; then \
			    (cd $$dir; $(MAKE) distclean); \
		    fi; \
	    done ; \
	else true; fi
