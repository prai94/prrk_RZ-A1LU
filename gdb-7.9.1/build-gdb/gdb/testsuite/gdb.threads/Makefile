VPATH = ../../../../gdb/testsuite/gdb.threads
srcdir = ../../../../gdb/testsuite/gdb.threads

EXECUTABLES = attach-into-signal-nothr attach-into-signal-thr \
	attach-stopped attachstop-mt \
	bp_in_thread current-lwp-dead execl execl1 fork-child-threads \
	fork-thread-pending gcore-pthreads hand-call-in-threads \
	ia64-sigill interrupted-hand-call killed linux-dp \
	local-watch-wrong-thread manythreads multi-create pending-step \
	print-threads pthreads pthread_cond_wait schedlock sigthread \
	staticthreads switch-threads thread-execl thread-specific \
	thread_check thread_events threadapply threxit-hop-specific \
	tls tls-main tls-nodebug watchthreads watchthreads-reorder \
	watchthreads2

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o a.out xgdb *.x *.ci *.tmp core core.* $(EXECUTABLES) \
	 *.core gcore.test
	-rm -f *.dwo *.dwp

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log config.h gdb.log gdb.sum
