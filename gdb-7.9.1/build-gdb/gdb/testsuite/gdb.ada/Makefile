VPATH = ../../../../gdb/testsuite/gdb.ada
srcdir = ../../../../gdb/testsuite/gdb.ada

EXECUTABLES = \
  array_bounds/bar \
  array_return/p \
  array_subscript_addr/p \
  arrayidx/p \
  arrayparam/foo \
  arrayptr/foo \
  atomic_enum/foo \
  catch_ex/foo \
  char_param/foo \
  complete/foo \
  exec_changed/common \
  exec_changed/first \
  exec_changed/second \
  exprs/p \
  fixed_cmp/fixed \
  fixed_points/fixed_points \
  formatted_ref/formatted_ref \
  frame_args/foo \
  fun_addr/foo \
  fun_in_declare/foo \
  funcall_param/foo \
  homonym/homonym_main \
  info_types \
  interface/foo \
  lang_switch/lang_switch \
  nested/hello \
  null_array/foo \
  null_record/null_record \
  packed_array/pa \
  packed_tagged/comp_bug \
  print_chars/foo \
  start/dummy \
  ptype_field/foo \
  ref_param/foo \
  str_ref_cmp/foo \
  sym_print_name/foo \
  taft_type/p \
  tagged/foo \
  type_coercion/assign \
  watch_arg/watch

MISCELLANEOUS =

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-find . -name '*.o' -print | xargs rm -f
	-find . -name '*.ali' -print | xargs rm -f
	-find . -name 'b~*.ad[sb]' -print | xargs rm -f
	-rm -f *~ a.out xgdb *.x *.ci *.tmp
	-rm -f *~ *.o a.out xgdb *.x *.ci *.tmp
	-find . -name '*.dwo' -print | xargs rm -f
	-find . -name '*.dwp' -print | xargs rm -f
	-rm -f core core.coremaker coremaker.core corefile $(EXECUTABLES)
	-rm -f $(MISCELLANEOUS) twice-tmp.c

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
